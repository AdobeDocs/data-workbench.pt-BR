---
description: Instruções sobre como instalar e configurar o Sensor para o Lotus Domino Server 6 para Windows 3.1 ou posterior em execução no Microsoft Windows Server 2000 ou posterior.
title: Lotus Domino Server no Windows Server 2000 ou posterior
uuid: e3fb1478-92d1-4488-a4b8-244d258cc00a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lotus Domino Server no Windows Server 2000 ou posterior{#lotus-domino-server-on-windows-server-or-later}

Instruções sobre como instalar e configurar o Sensor para o Lotus Domino Server 6 para Windows 3.1 ou posterior em execução no Microsoft Windows Server 2000 ou posterior.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação que você obtém do site de download da Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor Web específico, baixe-o (ou obtenha-o do seu representante da Adobe) antes de começar os procedimentos a seguir.

Para instalar e configurar o Sensor, execute as seguintes etapas:

## Instale os arquivos de programa {#section-2f3e85083b4f4aa989a85997330e86ae}

1. Na máquina do Lotus Domino, crie um diretório para instalar os arquivos de programa do Sensor. Lembre-se de que sua fila de discos também reside neste diretório, portanto, verifique se o dispositivo escolhido tem espaço suficiente para manter uma fila do tamanho necessário.

   ```
   C:\VisualSensor
   ```

1. Extraia o conteúdo do arquivo de instalação para o diretório Lotus Domino. Durante esta etapa, o Sensor instala os seguintes arquivos:

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
   <td colname="col2"> Mensagens do Visualizador de eventos </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stchatlog.dll </td> 
   <td colname="col2"> O módulo do coletor </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Um arquivo de planilha do Excel que os arquitetos podem usar para configurar um experimento controlado </p> <p>O sensor não usa este arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> O certificado usado para validar o certificado digital que o Insight Server apresenta durante o processo de conexão </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> O programa transmissor </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.conf </p> </td> 
   <td colname="col2"> O arquivo de configuração do sensor </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, copie o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extraia o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre a experimentação controlada, consulte o Guia de Experimentos Controlados Insight.

## Configure o Lotus Domino Server {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Etapas para configurar o Lotus Domino Server.

1. Faça logon no Lotus Domino Administrator e clique em **[!UICONTROL Domain]**.

   ![](assets/dom_svr1.png)

1. No Lotus Domino Administrator, clique em **[!UICONTROL Configuration]**.

   ![](assets/dom_svr2.png)

1. Expanda o nó Servidor e clique em **[!UICONTROL Current Server Document]**.

   ![](assets/dom_svr3.png)

1. Click **[!UICONTROL Current Server Document]**, then click **[!UICONTROL Internet Protocols]**.

   ![](assets/dom_svr4.png)

1. Na guia HTTP, na seção DSAPI, clique duas vezes depois da palavra [!DNL ndolextn].

   ![](assets/dom_svr5.png)

1. Pressione **[!UICONTROL Enter]** e digite o caminho para o [!DNL dominosensor.dll] arquivo.

   ![](assets/dom_svr6.png)

1. Clique em **[!UICONTROL Save & Close]**.

   ![](assets/dom_svr7.png)

## Edite o arquivo de configuração do sensor {#section-de0eb4a646394b61abb6cd5a2b706de0}

O arquivo txlogd.conf contém os parâmetros de configuração do Sensor.

É necessário editar esse arquivo para especificar, entre outras coisas, o tamanho e o local do arquivo de fila de disco, o endereço do Insight Server e a ID que será anexada aos dados de evento produzidos por esse sensor.

O arquivo de configuração contém parâmetros obrigatórios e opcionais.

* **Parâmetros** obrigatórios são configurações que você deve especificar ao instalar o Sensor. Sem essas configurações, o sensor não é executado com êxito.
* **Parâmetros** opcionais são configurações padrão para valores predefinidos (que podem ser modificados) ou habilitam recursos opcionais.

**Para editar o arquivo de configuração do sensor**

* Abra o `<Sensor directory>/txlogd.conf` arquivo em um editor de texto e defina os parâmetros necessários, bem como quaisquer parâmetros opcionais desejados.
* Salve e feche o arquivo.

## Inicie o transmissor e crie a fila de discos {#section-55630de65f264274aefd771da2002852}

Depois de configurar o arquivo txlogd.conf, você pode iniciar o programa transmissor, registrá-lo como um serviço do Windows e criar a fila de discos.

1. No menu Iniciar do Windows, selecione **Acessórios** > Prompt **de comando**.

1. Na janela da tela de comandos, navegue até o diretório no qual você instalou o Sensor e execute o seguinte comando:

   ```
   txlog /regserver
   ```

   Esse comando inicia o transmissor, cria a fila de discos e registra o Sensor como um serviço do Windows.

1. Para confirmar se o transmissor está sendo executado corretamente, clique em **Iniciar > Painel de controle > Ferramentas administrativas > Serviços**.

   >[!NOTE]
   >
   >Essa sequência de comando pode variar dependendo da versão do Windows que você está usando.

   1. Na lista de serviços, localize a entrada Sensor e confirme se seu status é Iniciado e seu tipo de inicialização é Automático.
   1. Feche o painel de controle Serviços.

1. Para verificar se o transmissor apresentou erros durante a inicialização, clique em Iniciar > Painel de controle > Ferramentas administrativas > Visualizador de eventos para abrir o Visualizador de eventos.

   >[!NOTE]
   >
   >Essa sequência de comando pode variar dependendo da versão do Windows que você está usando.

   1. No painel esquerdo da janela Visualizador de eventos, selecione o registro Aplicativos.
   1. No painel direito, procure eventos com &quot;Adobe&quot; na coluna Origem.
   1. Se encontrar um erro em &quot;Adobe&quot;, clique duas vezes no erro para exibir a janela Propriedades do evento. Esta janela fornece informações detalhadas sobre o erro.

1. Quando terminar de examinar o log de Aplicativos, feche o Visualizador de Eventos.
1. Verifique se o transmissor criou a fila de disco ( [!DNL Diskq2000.log]) no diretório onde você instalou os arquivos de programa do Sensor e se é do tamanho especificado no [!DNL QueueSize] parâmetro no [!DNL txlogd.conf] arquivo.

   Se a fila não tiver sido criada corretamente:

   1. Examine o arquivo txtlogd.conf e verifique se o parâmetro QueueSize está definido corretamente.
   1. Verifique se o dispositivo no qual você instalou o Sensor tem espaço suficiente disponível para manter um arquivo do tamanho especificado no parâmetro QueueSize.
   1. Usando o painel de controle de serviços no Windows, pare o transmissor.
   1. Exclua o arquivo da fila.
   1. Registre novamente o Sensor como um serviço do Windows: no menu Iniciar do Windows, selecione Acessórios > Prompt de comando. Na janela da tela de comandos, navegue até o diretório no qual você instalou o Sensor e execute o seguinte comando:

      ```
      txlog /regserver
      ```

      O transmissor foi projetado para funcionar continuamente. Se você reiniciar a máquina, o transmissor será reiniciado automaticamente. Se você precisar iniciar e parar o transmissor manualmente, poderá fazê-lo usando o painel de controle Serviços no Windows.

