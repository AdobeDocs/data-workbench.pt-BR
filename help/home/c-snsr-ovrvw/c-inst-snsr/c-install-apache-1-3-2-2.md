---
description: Instruções para instalação e configuração do Sensor para o Apache Server 1.3, Apache Server 2.0.42 ou posterior ou Apache Server 2.2 em execução no Microsoft Windows Server 2000 ou posterior.
title: Apache Server 1.3, 2, 2.2 ou 2.4 no Windows Server 2000 ou posterior
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 1.3, 2, 2.2 ou 2.4 no Windows Server 2000 ou posterior{#apache-server-or-on-windows-server-or-later}

Instruções para instalação e configuração do Sensor para o Apache Server 1.3, Apache Server 2.0.42 ou posterior ou Apache Server 2.2 em execução no Microsoft Windows Server 2000 ou posterior.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação que você obtém do site de download da Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor Web específico, baixe-o (ou obtenha-o do seu representante da Adobe) antes de começar os procedimentos a seguir.

* Apache Server 1.3
* Apache Server 2.0.42 ou posterior
* Apache Server 2.2 em execução no Microsoft Windows Server 2000 ou posterior

## Instale os arquivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Antes de instalar os arquivos do programa, você deve determinar onde deseja manter a fila de discos, pois também é onde você deve instalar os arquivos do programa.Procedimento para extrair e instalar os arquivos do programa para o Sensor.

Para instalar e configurar o Sensor, execute as seguintes etapas:

1. No computador Windows, crie um diretório no qual os arquivos de programa Sensor serão instalados. Lembre-se de que sua fila de discos também reside neste diretório, portanto, verifique se o dispositivo escolhido tem espaço suficiente para manter uma fila do tamanho necessário.

   ```
   C:\VisualSensor
   ```

1. Extraia o conteúdo do arquivo de instalação para o diretório que você acabou de criar. Durante esta etapa, o Sensor instala os seguintes arquivos:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Mensagens do Visualizador de eventos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> O módulo do coletor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Um arquivo de planilha do Excel que os arquitetos podem usar para configurar um experimento controlado. O sensor não usa este arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> O certificado usado para validar o certificado digital que o Insight Server apresenta durante o processo de conexão. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> O programa transmissor </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> O arquivo de configuração do sensor </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, copie o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extraia o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre a experimentação controlada, consulte o Guia de Experimentos Controlados Insight.

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
1. Adicione as duas linhas a seguir ao final do arquivo:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Essas linhas fazem distinção entre maiúsculas e minúsculas. Digite-os exatamente como aparecem acima.

1. Reinicie o processo do servidor da Web (você não precisa reinicializar o computador inteiro do servidor, simplesmente reinicie o processo do servidor da Web). O coletor é carregado com o servidor da Web e começa a coletar dados de eventos e gravá-los na fila de discos.

