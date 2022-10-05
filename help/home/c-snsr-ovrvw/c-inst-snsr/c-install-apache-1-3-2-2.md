---
description: Instruções para instalação e configuração do Sensor para o Apache Server 1.3, Apache Server 2.0.42 ou posterior ou Apache Server 2.2 em execução no Microsoft Windows Server 2000 ou posterior.
title: Apache Server 1.3, 2, 2.2 ou 2.4 no Windows Server 2000 ou posterior
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
exl-id: d1bd0fc1-da5b-4183-8270-73c46195f724
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 1%

---

# Apache Server 1.3, 2, 2.2 ou 2.4 no Windows Server 2000 ou posterior{#apache-server-or-on-windows-server-or-later}

{{eol}}

Instruções para instalação e configuração do Sensor para o Apache Server 1.3, Apache Server 2.0.42 ou posterior ou Apache Server 2.2 em execução no Microsoft Windows Server 2000 ou posterior.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação obtido do site de download do Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor da Web específico, baixe-o (ou obtenha-o do representante do Adobe) antes de começar os seguintes procedimentos.

* Apache Server 1.3
* Apache Server 2.0.42 ou posterior
* Apache Server 2.2 em execução no Microsoft Windows Server 2000 ou posterior

## Instalar os arquivos do programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Antes de instalar os arquivos do programa, você deve determinar onde deseja manter a fila do disco, pois é também onde você deve instalar os arquivos do programa.Procedimento para extrair e instalar os arquivos do programa para o Sensor.

Para instalar e configurar o Sensor, execute as seguintes etapas:

1. Na máquina Windows, crie um diretório no qual os arquivos de programa Sensor serão instalados. Lembre-se de que sua fila de discos também reside nesse diretório, portanto, verifique se o dispositivo escolhido tem espaço suficiente para manter uma fila do tamanho necessário.

   ```
   C:\VisualSensor
   ```

1. Extraia o conteúdo do arquivo de instalação para o diretório que acabou de criar. Durante essa etapa, o Sensor instala os seguintes arquivos:

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
   <td colname="col2"> Mensagens do Visualizador de Eventos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> O módulo coletor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Um arquivo de planilha do Excel que os arquitetos podem usar para configurar um experimento controlado. O sensor não usa esse arquivo. </p> </td> 
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
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, você pode querer copiar o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extrair o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre experimentação controlada, consulte o Guia de experimentos controlados do Insight.

## Editar o arquivo de configuração do sensor {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

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

## Adicionar o Coletor ao Servidor Web {#section-c5b83ae4ebce430aa764f951e849b333}

Para servidores Apache, o coletor é um objeto compartilhado dinâmico que você carrega no processo do servidor da Web.

Para adicionar o coletor ao seu servidor da Web, você deve editar o [!DNL httpd.conf] conforme descrito abaixo e reinicie o servidor da Web.

>[!NOTE]
>
>Se o Sensor estiver capturando dados de vários servidores da Web no computador servidor, você deverá executar o seguinte procedimento para cada servidor da Web.

1. Usando um editor de texto, abra o [!DNL httpd.conf]arquivo para o servidor da Web cujos eventos o Sensor captura.
1. Adicione as duas linhas a seguir ao final do arquivo :

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Essas linhas diferenciam maiúsculas de minúsculas. Digite-os exatamente como aparecem acima.

1. Reinicie o processo do servidor da Web (não é necessário reiniciar o computador do servidor inteiro, simplesmente reiniciar o processo do servidor da Web). O coletor é carregado com o servidor da Web e começa a coletar dados do evento e gravá-los na fila do disco.
