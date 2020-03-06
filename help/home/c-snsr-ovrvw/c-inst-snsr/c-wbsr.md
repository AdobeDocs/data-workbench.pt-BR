---
description: Instruções detalhadas para instalar e configurar o Sensor para WebSphere 5.x em execução no AIX 5.1 ou posterior.
solution: Insight
title: WebSphere no AIX
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# WebSphere no AIX{#websphere-on-aix}

Instruções detalhadas para instalar e configurar o Sensor para WebSphere 5.x em execução no AIX 5.1 ou posterior.

Os arquivos de programa para [!DNL Sensor] são compactados em um arquivo de instalação que você obtém do site de download da Adobe. Se você ainda não tiver o arquivo de [!DNL Sensor] instalação do seu servidor Web específico, baixe-o (ou obtenha-o do seu representante da Adobe) antes de começar os procedimentos a seguir.

>[!NOTE]
>
>O [!DNL Sensor] para servidores WebSphere não suporta experimentação controlada. Para obter informações sobre experimentação controlada, consulte o Guia de Experimentos Controlados da *Análise de big data.*

## Instale os arquivos de programa {#section-86f69127278c41bc90b97b68bb40bc6e}

Procedimento para extrair e instalar os arquivos de programa do Sensor na máquina do servidor.

1. Faça logon como o usuário raiz ou como um usuário com autoridade raiz.
1. Descompacte e descompacte o arquivo de instalação usando o seguinte comando:

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. Copie os arquivos de programa descompactados para os diretórios identificados na tabela a seguir:

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Diretório de destino </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> O módulo de carregamento do coletor </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> As bibliotecas do módulo de carregamento do coletor </td> 
   <td colname="col3"> Diretório WebSphere /lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> O programa transmissor </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OU-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> O arquivo de configuração do sensor </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> O certificado usado para validar o certificado digital que o Insight Server apresenta durante o processo de conexão </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, copie o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extraia o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre a experimentação controlada, consulte o Guia de Experimentos Controlados Insight.

**Permissões nos arquivos de programas**

Permissões incorretas nos arquivos de programa causam a maioria dos problemas encontrados ao instalar o Sensor.

Certifique-se de definir as permissões exatamente como está indicado nesta seção.

Por padrão, os arquivos de programa no arquivo tar têm as seguintes permissões. Dependendo de como seu sistema está configurado, essas configurações podem ser alteradas (não mascaradas) ao extrair os arquivos.

Para redefinir as permissões para as configurações padrão recomendadas, use os comandos chmod abaixo.

>[!NOTE]
>
>Verifique se os diretórios nos quais você instalou os arquivos permitem pelo menos esse nível de acesso.

| Arquivo | Permissões padrão | comando chmod |
|---|---|---|
| libvisual_sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw- rw- r— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

Se você quiser usar permissões diferentes dos padrões recomendados, reveja as informações em Permissões de arquivo do Sensor UNIX, para ter certeza de que entende como esses arquivos são usados.

## Editar o arquivo de configuração do sensor {#section-283c8a92fa8841c1b6034e5f834ef4e7}

O arquivo txlogd.conf contém os parâmetros de configuração do Sensor.

Você deve editar o arquivo para especificar, entre outras coisas, o tamanho da fila de discos, o endereço do Insight Server e a ID que será anexada aos dados produzidos por esse sensor.

O arquivo de configuração contém parâmetros obrigatórios e opcionais.

* Parâmetros obrigatórios são configurações que você deve especificar ao instalar o Sensor. Sem essas configurações, o sensor não é executado com êxito.
* Parâmetros opcionais são configurações padrão para valores predefinidos (que podem ser modificados) ou habilitam recursos opcionais.

**Para editar o arquivo de configuração**

1. Abra o arquivo /etc/txlogd.conf em um editor de texto e defina os parâmetros necessários, bem como quaisquer parâmetros opcionais desejados.
1. Salve e feche o arquivo.

## Inicie o transmissor e crie a fila de discos {#section-63285a2328604f20a2cb31b3d5cb80e6}

Procedimento para criar a fila de discos, depois de configurar o arquivo txlogd.conf.

1. Se o diretório no qual a fila de discos reside ainda não existir, crie-o. Certifique-se de que o diretório fornece ao módulo coletor e ao programa transmissor acesso de leitura/gravação ao arquivo.

1. No computador em que o Sensor está instalado, execute o seguinte comando para iniciar o transmissor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * A opção &quot;i&quot; neste comando inicia o transmissor no modo interativo. Esse modo exibe mensagens do transmissor na tela e também permite que você interaja com o transmissor usando comandos do teclado.
   * A opção &quot;c&quot; direciona o transmissor para criar a fila de discos.
   * A opção &quot;f&quot; especifica o local do arquivo de configuração.

1. Verifique se o transmissor criou a fila de discos no local especificado no parâmetro QueueFile e no tamanho especificado no parâmetro QueueSize.
1. Se a fila não tiver sido criada corretamente, digite Ctrl+C para encerrar o transmissor e faça o seguinte:

   1. Examine o arquivo txtlogd.conf e verifique se os parâmetros QueueFile e QueueSize estão definidos corretamente.
   1. Verifique se o dispositivo ao qual a fila de discos está atribuída está operacional e tem espaço suficiente disponível para reter um arquivo do tamanho especificado no parâmetro QueueSize.
   1. Faça as correções necessárias e repita este procedimento.

## Adicionar o Coletor ao Aplicativo Web {#section-d17297b1193f4e3cb150fb41f754ef12}

Para servidores WebSphere, o coletor opera como um filtro no contêiner de servlet.

Para adicionar o coletor ao aplicativo da Web, adicione o filtro ao descritor de deployment web.xml do aplicativo da Web e reinicie o aplicativo da Web.

1. Usando um editor de texto, abra o arquivo web.xml para o servidor da Web cujos eventos o Sensor captura.
1. Adicione os seguintes elementos `<filter>` e `<filter-mapping>` ao arquivo do descritor. Se você não instalou txlogd.conf no diretório /etc, é necessário digitar o caminho correto para esse arquivo no `<param-value>` elemento .

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping>
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping>
   ```

   >[!NOTE]
   >
   >Essas linhas fazem distinção entre maiúsculas e minúsculas. Digite-os exatamente como aparecem acima.

1. Reinicie o aplicativo da Web. O coletor é carregado com o aplicativo e começará a coletar dados de eventos e gravá-los na fila de discos.

## Declarar o local do coletor e dos arquivos de objetos compartilhados {#section-e641f08999d34a648aaee2111b69ca25}

Procedimento para editar o script de inicialização Webphere para declarar o local dos arquivos J2EECollector.jar e libvisual_sciences.so.

1. Abra o arquivo setupCmdLine.sh no diretório Webphere /bin.
1. Após a linha que define a variável $WAS_CLASSPATH, adicione a seguinte linha:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Após o bloco de letras maiúsculas e minúsculas que define a variável $WAS_LIBPATH, adicione a seguinte linha:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Save the [!DNL setupCmdLine.sh] file.

## Teste o sensor {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

Procedimento para iniciar o transmissor e verificar se ele consegue se conectar com êxito ao Insight Server e transmitir dados do evento para ele.

>[!NOTE]
>
>Para verificar se o transmissor pode enviar dados de evento com êxito ao Insight Server, verifique se o Insight Server de destino está instalado e em execução antes de iniciar o seguinte teste.

1. Se o transmissor ainda não estiver em execução, reinicie-o usando o seguinte comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Abra um navegador (em qualquer máquina) e solicite uma página do servidor da Web no qual o Sensor está sendo executado (certifique-se de selecionar uma página que o Sensor esteja monitorando).
1. Depois de emitir a solicitação, verifique se há mensagens no console do transmissor indicando que ele está enviando dados do evento para o Insight Server de destino.
1. Se o sensor não estiver transmitindo os dados com êxito, verifique se:

   * O Servidor Insight de destino está em execução.
   * Os parâmetros ServerAddress e ServerPort estão definidos corretamente em txtlogd.conf. Se você especificou ServerAddress usando um nome de servidor, tente usar seu endereço IP numérico.
   * O valor do parâmetro CertName corresponde exatamente ao nome comum que aparece no certificado digital do Insight Server de destino.

## Adicione o transmissor ao script de inicialização do sistema {#section-23bb905100d04f018af93873dd4d5f68}

Informações para garantir que o transmissor seja carregado automaticamente quando a máquina do servidor da Web for reiniciada.

Adicione o seguinte comando (que inicia o transmissor) ao script de inicialização do sistema.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Esse comando inicia o transmissor como um daemon. As mensagens de erro e de operação geradas pelo transmissor são gravadas no syslog.

## Captura de dados adicionais {#section-d5ccf8ee50914a87938e0c17480757e6}

Os sensores para todas as plataformas podem coletar quaisquer dados disponíveis nos cabeçalhos de solicitação HTTP e resposta.

Os Sensores da Plataforma J2EE fornecem um mecanismo para coletar dados que não está disponível em outras plataformas. O coletor para a plataforma J2EE (coletor J2EE) fica na camada do aplicativo, o que permite coletar dados confidenciais que estão disponíveis apenas para o aplicativo e não devem ser expostos por meio da marcação de página ou nos cabeçalhos.

>[!NOTE]
>
>Embora as tags de página e a modificação de cabeçalho possam ocultar os dados, eles ainda estão disponíveis para aqueles que examinam o código fonte de uma página ou olham para os cabeçalhos usando as ferramentas de plug-in do navegador.

Por exemplo, o coletor J2EE pode ser usado para capturar dados de custo por clique (CPC) para links exibidos em uma página, informações confidenciais do parceiro em uma página e muitos outros pontos de dados. O ambiente J2EE facilita a modificação de seu aplicativo WEBAPP para capturar esses dados personalizados usando nossa classe de coletores.

Quando um Sensor para a Plataforma J2EE recebe uma solicitação, ele chama uma classe de coletor que importa a função appendToLog. A função appendToLog anexa à solicitação inicial os parâmetros da string de consulta especificados na função appendToLog. Isso resulta no URI da solicitação inicial contendo pares de nome-valor da string de consulta adicionais que correspondem aos nomes e valores dos dados que estão sendo capturados. Por exemplo, CPC=20 seria anexado à solicitação inicial quando o valor de uma disposição de anúncio específica ou link de click-through for 20 centavos. O Insight Server processa esses valores no conjunto de dados para análise. Um benefício adicional para essa metodologia de coleta é permitir a coleta de dados adicionais sem criar entradas extras de log, como pode ser criado usando metodologias de marcação de página.

Para obter mais informações sobre o processamento, consulte o Guia *de configuração de* conjuntos de dados.

1. Adicione o seguinte código à parte superior da página .jsp da qual você deseja capturar dados:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. Use o método appendToLog() do objeto coletor para anexar os pares de nome-valor desejados à string de consulta da página .jsp solicitada. O exemplo a seguir anexa &quot;A=1&quot; e &quot;B=2&quot; à string de consulta da página .jsp solicitada para a página /index.jsp:

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html>
   ```

   O URI de solicitação resultante é /index.jsp?A=1&amp;B=2.

1. Repita esse procedimento para cada página .jsp da qual deseja capturar dados adicionais.

