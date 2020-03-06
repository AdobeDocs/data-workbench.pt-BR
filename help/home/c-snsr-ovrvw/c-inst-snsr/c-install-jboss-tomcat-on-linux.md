---
description: Instruções detalhadas para instalação e configuração de Sensor para implementações J2EE em execução no RedHat Linux 7.x ou posterior, Sun Solaris SPARC 2.6 ou posterior ou Sun Solaris x86 9 ou posterior.
title: Servidores JBoss, Tomcat e WebLogic em RedHat Linux ou Sun Solaris
uuid: 7977fb9b-1737-4e1d-80c6-aabf968974dd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Servidores JBoss, Tomcat e WebLogic em RedHat Linux ou Sun Solaris{#jboss-tomcat-and-weblogic-servers-on-redhat-linux-or-sun-solaris}

Instruções detalhadas para instalação e configuração de Sensor para implementações J2EE em execução no RedHat Linux 7.x ou posterior, Sun Solaris SPARC 2.6 ou posterior ou Sun Solaris x86 9 ou posterior.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação que você obtém do site de download da Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor Web específico, baixe-o (ou obtenha-o do seu representante da Adobe) antes de começar os procedimentos a seguir.

As implementações J2EE suportadas incluem:

* JBoss Server 3.2.x ou posterior
* Apache Jakarta Tomcat Server 4.1 ou posterior
* WebLogic Server 6.x ou posterior

Para instalar e configurar o Sensor, execute as seguintes etapas:

## Instale os arquivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedimento para extrair e instalar os arquivos de programa do Sensor.

1. Faça logon como o usuário raiz ou como um usuário com autoridade raiz.
1. Descompacte e descompacte o arquivo de instalação usando o seguinte comando:

   * No Linux:

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * No Solaris:

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
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
   <td colname="col2"> O programa do transmissor. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OU--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> O arquivo de configuração do sensor. </td> 
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
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, copie o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extraia o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre a experimentação controlada, consulte o Guia de Experimentos Controlados Insight.

**Permissões nos arquivos de programas**

>[!NOTE]
>
>Permissões incorretas nos arquivos de programa causam a maioria dos problemas encontrados ao instalar o Sensor. Certifique-se de definir as permissões exatamente como está indicado nesta seção.
>
>Por padrão, os arquivos de programa no arquivo tar têm as seguintes permissões. Dependendo de como seu sistema está configurado, essas configurações podem ser alteradas (não mascaradas) ao extrair os arquivos. Para redefinir as permissões para as configurações padrão recomendadas, use os comandos chmod abaixo. Verifique se os diretórios nos quais você instalou os arquivos permitem pelo menos esse nível de acesso.

| Arquivo | Permissões padrão | comando chmod |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-r— r— | chmod 664 |
| trust_ca_cert.pem | rw-r— r— | chmod 664 |

## Edite o arquivo de configuração do sensor {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

O [!DNL txlogd.conf] arquivo contém os parâmetros de configuração do Sensor.

É necessário editar esse arquivo para especificar, entre outras coisas, o tamanho e o local do arquivo de fila de disco, o endereço do Insight Server e a ID que será anexada aos dados de evento produzidos por esse sensor.

O arquivo de configuração contém parâmetros obrigatórios e opcionais.

* **Parâmetros** obrigatórios são configurações que você deve especificar ao instalar o Sensor. Sem essas configurações, o sensor não é executado com êxito.
* **Parâmetros** opcionais são configurações padrão para valores predefinidos (que podem ser modificados) ou habilitam recursos opcionais.

**Para editar o arquivo de configuração do sensor**

* Abra o [!DNL /etc/txlogd.conf] arquivo em um editor de texto e defina os parâmetros necessários, bem como quaisquer parâmetros opcionais desejados.
* Salve e feche o arquivo.

**Para editar o arquivo de configuração do sensor**

1. Abra o [!DNL /etc/txlogd.conf] arquivo em um editor de texto e defina os parâmetros necessários, bem como quaisquer parâmetros opcionais desejados.
1. Salve e feche o arquivo.

## Inicie o transmissor e crie a fila de discos {#section-55630de65f264274aefd771da2002852}

Depois de configurar o arquivo txlogd.conf, você pode iniciar o programa transmissor, registrá-lo como um serviço do Windows e criar a fila de discos.

1. Se o diretório no qual a fila de discos reside ainda não existir, crie-o. Certifique-se de que o diretório fornece ao módulo coletor e ao programa transmissor acesso de leitura/gravação ao arquivo.

   Para obter mais informações sobre as permissões exigidas pelos arquivos de fila de disco, consulte Permissões de arquivo UNIX do sensor.
1. No computador em que o Sensor está instalado, execute o seguinte comando para iniciar o transmissor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * A opção &quot;i&quot; neste comando inicia o transmissor no &quot;modo interativo&quot;. Esse modo exibe mensagens do transmissor na tela e também permite que você interaja com o transmissor usando comandos do teclado.
   * A opção &quot;c&quot; direciona o transmissor para criar a fila de discos.
   * A opção &quot;f&quot; especifica o local do arquivo de configuração.
   Para obter informações adicionais sobre as opções que podem ser usadas ao iniciar o transmissor, consulte Opções de linha de comando do transmissor de sensor.

1. Verifique se o transmissor criou a fila de discos no local especificado no parâmetro QueueFile e no tamanho especificado no parâmetro QueueSize.
1. Se a fila não tiver sido criada corretamente, digite Ctrl+C para encerrar o transmissor e faça o seguinte:

   1. Examine o arquivo txtlogd.conf e verifique se os parâmetros QueueFile e QueueSize estão definidos corretamente.
   1. Verifique se o dispositivo ao qual a fila de discos está atribuída está operacional e tem espaço suficiente disponível para reter um arquivo do tamanho especificado no parâmetro QueueSize.
   1. Faça as correções necessárias e repita este procedimento.

## Adicionar o Coletor ao Servidor Web {#section-c5b83ae4ebce430aa764f951e849b333}

Para servidores Apache, o coletor é um objeto compartilhado dinâmico que você carrega no processo do servidor Web.

Para adicionar o coletor ao servidor da Web, edite o [!DNL httpd.conf] arquivo conforme descrito abaixo e reinicie o servidor da Web.

>[!NOTE]
>
>Se o Sensor estiver capturando dados para vários servidores da Web no computador servidor, você deverá executar o seguinte procedimento para cada servidor da Web.

1. Usando um editor de texto, abra o [!DNL httpd.conf]arquivo para o servidor da Web cujos eventos o Sensor captura.
1. Adicione os seguintes elementos `<filter>` e `<filter-mapping>` ao arquivo do descritor. Se você não instalou txlogd.conf no diretório /etc, é necessário digitar o caminho correto para esse arquivo no `<param-value>` elemento:

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>/etc/txlogd.conf</param-value> 
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

1. Reinicie o processo do servidor da Web (você não precisa reinicializar o computador inteiro do servidor, simplesmente reinicie o processo do servidor da Web). O coletor é carregado com o servidor da Web e começa a coletar dados de eventos e gravá-los na fila de discos.

## Teste o sensor {#section-0dae181ef8884f10a57f6cfda8500969}

Verifique se o coletor está coletando dados de eventos e se o transmissor está transmitindo para o servidor Insight de destino.

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

## Adicione o transmissor ao script de inicialização do sistema {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informações sobre como carregar automaticamente o transmissor para o script de inicialização do sistema.

Para garantir que o transmissor seja carregado automaticamente quando a máquina do servidor Web for reiniciada, adicione o seguinte comando (que inicia o transmissor) ao script de inicialização do sistema:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Esse comando inicia o transmissor como um daemon. As mensagens de erro e de funcionamento geradas pelo transmissor são gravadas [!DNL syslog].

A configuração padrão do Solaris é 60. Com base nos testes realizados com o Sensor, que utiliza três semáforos para cada instância, a Adobe recomenda usar o 1024 como configuração. Esse número é alto o suficiente para que o Sensor funcione junto com quaisquer outros aplicativos no servidor que possam exigir pontos-e-vírgulas, mas não afeta o desempenho. Para apoiar esta recomendação, observe que Adrian Cockcroft declarou o seguinte em seu livro Sun Performance and Tuning (Prentice Hall, outubro de 1994): &quot;Os bancos de dados tendem a usar muita memória compartilhada e configurações de semáforo. Estes não afetam o desempenho; enquanto forem suficientemente grandes, os programas serão executados.&quot;

## Captura de dados adicionais {#section-9483b663cbd0432daaca50c1089c7fca}

Os sensores para todas as plataformas podem coletar quaisquer dados disponíveis nos cabeçalhos de solicitação HTTP e resposta.

Os Sensores da Plataforma J2EE fornecem um mecanismo para coletar dados que não está disponível em outras plataformas. O coletor para a plataforma J2EE (coletor J2EE) fica na camada do aplicativo, o que permite coletar dados confidenciais que estão disponíveis apenas para o aplicativo e não devem ser expostos por meio da marcação de página ou nos cabeçalhos.

>[!NOTE]
>
>Embora as tags de página e a modificação de cabeçalho possam ocultar os dados, eles ainda estão disponíveis para aqueles que examinam o código fonte de uma página ou olham para os cabeçalhos usando as ferramentas de plug-in do navegador.

Por exemplo, o coletor J2EE pode ser usado para capturar dados de custo por clique (CPC) para links exibidos em uma página, informações confidenciais do parceiro em uma página e muitos outros pontos de dados. O ambiente J2EE facilita a modificação de seu aplicativo WEBAPP para capturar esses dados personalizados usando nossa classe de coletores.

Quando um Sensor para a Plataforma J2EE recebe uma solicitação, ele chama uma classe de coletor que importa a função appendToLog. A função appendToLog anexa à solicitação inicial os parâmetros da string de consulta especificados na função appendToLog. Isso resulta no URI da solicitação inicial contendo pares de nome-valor da string de consulta adicionais que correspondem aos nomes e valores dos dados que estão sendo capturados. Por exemplo, CPC=20 seria anexado à solicitação inicial quando o valor de uma disposição de anúncio específica ou link de click-through for 20 centavos. O Insight Server processa esses valores no conjunto de dados para análise. Um benefício adicional para essa metodologia de coleta é permitir a coleta de dados adicionais sem criar entradas extras de log, como pode ser criado usando metodologias de marcação de página.

Para obter mais informações sobre o processamento, consulte o Guia de Configuração de Conjunto de Dados.

**Para capturar dados adicionais de uma página**

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

