---
description: Instruções sobre como instalar e configurar o IBM HTTP Server no IBM AIX 5.1 ou posterior em execução no Microsoft Windows Server 2000 ou posterior.
title: IBM HTTP Server no AIX 5.1 ou posterior
uuid: d4a37ab2-514a-4afb-905b-420159c4ef0a
exl-id: 1d0c3aa9-de2d-45c0-b52d-b6e3fd4fd453
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1764'
ht-degree: 1%

---

# IBM HTTP Server no AIX 5.1 ou posterior{#ibm-http-server-on-aix-or-later}

{{eol}}

Instruções sobre como instalar e configurar o IBM HTTP Server no IBM AIX 5.1 ou posterior em execução no Microsoft Windows Server 2000 ou posterior.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação obtido do site de download do Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor da Web específico, baixe-o (ou obtenha-o do representante do Adobe) antes de começar os seguintes procedimentos.

Para instalar e configurar o Sensor, você deve executar as seguintes etapas de alto nível:

## Instalar os arquivos do programa {#section-2f3e85083b4f4aa989a85997330e86ae}

No servidor IBM AIX, crie um diretório no qual instale os arquivos de programa do Sensor. Lembre-se de que sua fila de discos também reside nesse diretório, portanto, verifique se o dispositivo escolhido tem espaço suficiente para manter uma fila do tamanho necessário.

1. Faça logon como o usuário raiz ou como um usuário com autoridade raiz.
1. Descomprima e descompacte o arquivo de instalação usando o seguinte comando:

   ```
   tar -zxf installationFilename
   ```

1. Copie os arquivos de programa descompactados para os diretórios identificados na tabela a seguir:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Diretório de destino </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> O módulo de carregamento do coletor. </td> 
   <td colname="col3"> <i> IBMHttpServer/modules</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> O programa transmissor. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> O arquivo de configuração do Sensor. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> O certificado usado para validar o certificado digital que o Insight Server apresenta durante o processo de conexão </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, você pode querer copiar o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extrair o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre experimentação controlada, consulte o Guia de experimentos controlados do Insight.

**Permissões nos arquivos do programa**

>[!NOTE]
>
>Permissões incorretas nos arquivos do programa causam a maioria dos problemas encontrados ao instalar o Sensor. Certifique-se de definir as permissões exatamente como declarado nesta seção.
>
>Por padrão, os arquivos de programa no arquivo tar têm as seguintes permissões. Dependendo de como seu sistema está configurado, essas configurações podem ser alteradas (não mascaradas) ao extrair os arquivos. Para redefinir as permissões para as configurações padrão recomendadas, use os comandos chmod abaixo. Verifique se os diretórios nos quais você instalou os arquivos permitem pelo menos esse nível de acesso.

<table id="table_F4A46DBDE0874133B616235C32B6D9F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Arquivo </th> 
   <th colname="col2" class="entry"> Permissões padrão </th> 
   <th colname="col3" class="entry"> comando chmod </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> <p>chmod 711 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> rw- rw- r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> chmod 711 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> rw- rw- r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> rw- rw- r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
 </tbody> 
</table>

## Editar o arquivo de configuração do sensor {#section-de0eb4a646394b61abb6cd5a2b706de0}

O [!DNL txlogd.conf] contém os parâmetros de configuração do Sensor.

É necessário editar esse arquivo para especificar, entre outras coisas, o tamanho e o local do arquivo da fila de discos, o endereço do servidor Insight e a ID que será anexada aos dados do evento produzidos por esse sensor.

O arquivo de configuração contém parâmetros obrigatórios e parâmetros opcionais.

* **Parâmetros obrigatórios** são configurações que você deve especificar ao instalar o Sensor. Sem essas configurações, o Sensor não é executado com êxito.
* **Parâmetros opcionais** são configurações que assumem o padrão de valores predefinidos (que podem ser modificados) ou ativam recursos opcionais.

**Para editar o arquivo de configuração do Sensor**

* Abra o [!DNL /etc/txlogd.conf] em um editor de texto e defina os parâmetros obrigatórios, bem como quaisquer parâmetros opcionais desejados.
* Salve e feche o arquivo.

**Para editar o arquivo de configuração do Sensor**

1. Abra o [!DNL /etc/txlogd.conf] em um editor de texto e defina os parâmetros obrigatórios, bem como quaisquer parâmetros opcionais desejados.
1. Salve e feche o arquivo.

## Inicie o transmissor e crie a fila de discos {#section-55630de65f264274aefd771da2002852}

Após configurar o arquivo txlogd.conf, você pode iniciar o programa transmissor, registrá-lo como um serviço do Windows e criar a fila de disco.

1. Se o diretório em que está a fila de discos ainda não existir, crie-o. Certifique-se de que o diretório forneça o módulo coletor e o programa transmissor com acesso de leitura/gravação ao arquivo.

   Para obter mais informações sobre as permissões necessárias para os arquivos de fila de disco, consulte Permissões de arquivo UNIX do sensor.
1. No computador em que o Sensor está instalado, execute o seguinte comando para iniciar o transmissor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * A opção &quot;i&quot; neste comando inicia o transmissor no &quot;modo interativo&quot;. Esse modo exibe mensagens do transmissor na tela e também permite que você interaja com o transmissor usando comandos do teclado.
   * A opção &quot;c&quot; direciona o transmissor para criar a fila de discos.
   * A opção &quot;f&quot; especifica o local do arquivo de configuração.

   Para obter informações adicionais sobre as opções que podem ser usadas ao iniciar o transmissor, consulte Opções de linha de comando do transmissor do sensor.

1. Verifique se o transmissor criou a fila de discos no local especificado no parâmetro QueueFile e do tamanho especificado no parâmetro QueueSize.
1. Se a fila não tiver sido criada corretamente, digite Ctrl+C para encerrar o transmissor e faça o seguinte:

   1. Examine o arquivo txtlogd.conf e verifique se os parâmetros QueueFile e QueueSize estão definidos corretamente.
   1. Verifique se o dispositivo ao qual a fila de discos está atribuída é operacional e tem espaço suficiente disponível para armazenar um arquivo do tamanho especificado no parâmetro QueueSize .
   1. Faça as correções necessárias e repita este procedimento.

## Adicionar o Coletor à Aplicação Web {#section-c5b83ae4ebce430aa764f951e849b333}

Para servidores WebSphere, o coletor opera como um filtro no contêiner de servlet.

Para adicionar o coletor ao seu aplicativo da Web, abra o arquivo web.xml para o servidor da Web cujos eventos o Sensor captura.

Se o Sensor estiver capturando dados de vários servidores da Web no computador servidor, você deverá executar o seguinte procedimento para cada servidor da Web.

1. Usando um editor de texto, abra o arquivo httpd.conf para o servidor da Web cujos eventos o Sensor captura.
1. Adicione o seguinte `<filter>` e `<filter-mapping>` elementos para o arquivo descritor. Se você não instalou o txlogd.conf no diretório /etc, é necessário inserir o caminho correto para esse arquivo no `<param-value>` elemento.

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
   >Essas linhas diferenciam maiúsculas de minúsculas. Digite-os exatamente como aparecem acima.

1. Reinicie o aplicativo Web. O coletor é carregado com o aplicativo e começará a coletar dados do evento e gravá-los na fila do disco.

## Declarar o local do coletor e dos arquivos de objeto compartilhados {#section-b9c298fa645f4670b2503647d967846f}

Edite o script de inicialização do Websphere para declarar o local dos arquivos J2EECollector.jar e libvisual_sciences.so.

1. Abra o arquivo setupCmdLine.sh no diretório Websphere /bin.
1. Após a linha que define a variável $WAS_CLASSPATH, adicione a seguinte linha:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Após o bloco de caso que define a variável $WAS_LIBPATH, adicione a seguinte linha:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Salve o arquivo setupCmdLine.sh.

## Teste o sensor {#section-0dae181ef8884f10a57f6cfda8500969}

Verifique se o coletor está coletando dados do evento e se o transmissor os está transmitindo ao servidor Insight de destino.

>[!NOTE]
>
>Para verificar se o transmissor pode enviar dados de evento com êxito para o servidor Insight, verifique se o servidor Insight de destino está instalado e em execução antes de iniciar o teste a seguir.

1. Se o transmissor ainda não estiver em execução, reinicie-o usando o seguinte comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Abra um navegador (em qualquer máquina) e solicite uma página do servidor da Web em que o Sensor está sendo executado (certifique-se de selecionar uma página que o Sensor esteja monitorando).
1. Depois de emitir a solicitação, verifique o console do transmissor quanto a mensagens indicando que ele está enviando dados do evento para o servidor Insight de destino.
1. Se o sensor não estiver transmitindo os dados com êxito, verifique se:

   * O Servidor Insight de destino está em execução.
   * Os parâmetros ServerAddress e ServerPort são definidos corretamente em txtlogd.conf. Se você especificou ServerAddress usando um nome de servidor, tente usar seu endereço IP numérico.
   * O valor do parâmetro CertName corresponde exatamente ao nome comum que aparece no certificado digital do servidor Insight de destino.

## Adicionar o transmissor ao script de inicialização do sistema {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informações sobre como carregar automaticamente o transmissor para o script de inicialização do sistema.

Para garantir que o transmissor carregue automaticamente quando a máquina do servidor da Web for reiniciada, adicione o seguinte comando (que inicia o transmissor) ao script de inicialização do sistema:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Esse comando inicia o transmissor como um daemon. Mensagens de erro e operacionais geradas pelo transmissor são gravadas no syslog.

## Capturando dados adicionais {#section-bb1c2bccba9b4bc0b52abdbb4f9d42d7}

Os sensores para todas as plataformas podem coletar qualquer um dos dados disponíveis nos cabeçalhos de solicitação e resposta HTTP.

Os Sensores da Plataforma J2EE fornecem um mecanismo de coleta de dados que não está disponível em outras plataformas. O coletor da plataforma J2EE (coletor J2EE) fica na camada do aplicativo, o que permite coletar dados confidenciais que estão disponíveis apenas para o aplicativo e não devem ser expostos por meio de marcação de página ou nos cabeçalhos.

>[!NOTE]
>
>Embora as tags de página e a modificação de cabeçalho possam ocultar os dados, eles ainda estão disponíveis para aqueles que examinam o código-fonte de uma página ou olham os cabeçalhos usando as ferramentas de plug-in do navegador.

Por exemplo, o coletor J2EE pode ser usado para capturar dados de custo por clique (CPC) para links exibidos em uma página, informações confidenciais do parceiro em uma página e muitos outros pontos de dados. O ambiente J2EE facilita a modificação de seu WEBAPP para capturar esses dados personalizados usando nossa classe de coletores.

Quando um Sensor da Plataforma J2EE recebe uma solicitação, ele chama uma classe de coletor que importa a função appendToLog . A função appendToLog anexa à solicitação inicial os parâmetros da string de consulta especificados na função appendToLog . Isso resulta no URI da solicitação inicial contendo pares de nome-valor de sequência de consulta adicionais que correspondem aos nomes e valores dos dados que estão sendo capturados. Por exemplo, CPC=20 seria anexado à solicitação inicial quando o valor de um determinado posicionamento de anúncio ou link de click-through é 20 centavos. O Insight Server processa esses valores no conjunto de dados para análise. Um benefício adicional para essa metodologia de coleta é que ela permite a coleta de dados adicionais sem criar entradas de log extras, como pode ser criado usando metodologias de marcação de página.

Para obter mais informações sobre o processamento, consulte o Guia de configuração do conjunto de dados.

Para capturar dados adicionais de uma página:

1. Adicione o seguinte código à parte superior da página .jsp da qual deseja capturar dados:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. Use o método appendToLog() do objeto coletor para anexar os pares de nome-valor desejados à sequência de consulta da página .jsp solicitada. O exemplo a seguir anexa &quot;A=1&quot; e &quot;B=2&quot; à sequência de consulta da página .jsp solicitada para a página /index.jsp:

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

   O URI da solicitação resultante é /index.jsp?A=1&amp;B=2.

1. Repita esse procedimento para cada página .jsp da qual deseja capturar dados adicionais.
