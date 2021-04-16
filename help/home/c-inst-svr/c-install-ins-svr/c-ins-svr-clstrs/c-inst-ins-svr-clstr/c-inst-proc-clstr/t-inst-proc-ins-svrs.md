---
description: Um Servidor Insight de processamento é idêntico a um Servidor Insight principal, exceto pelo conteúdo do diretório Componentes.
title: Instalar e configurar servidores Insight de processamento
uuid: 186675f7-8b63-4675-89ec-51b0837a64d8
exl-id: 21f7e31b-a2fb-4257-972e-5228bb1efa01
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Instalar e configurar servidores Insight de processamento{#installing-and-configuring-the-processing-insight-servers}

Um Servidor Insight de processamento é idêntico a um Servidor Insight principal, exceto pelo conteúdo do diretório Componentes.

O diretório Componentes em um [!DNL Insight Server] de processamento contém um conjunto especial de arquivos que são configurados especificamente para processamento [!DNL Insight Servers]. Esses arquivos são derivados do diretório Componentes para Servidores de Processamento no [!DNL Insight Server] principal.

Ao instalar um processamento [!DNL Insight Server], faça o seguinte para configurar o diretório Componentes:

1. Exclua o diretório original Componentes no processamento [!DNL Insight Server].
1. Renomeie o diretório Componentes para Servidores de Processamento para Componentes.
1. Modifique o [!DNL Synchronize.cfg] no diretório Componentes para apontar para o [!DNL Insight Server] principal.

**Para instalar e configurar um processamento[!DNL Insight Server]**

1. Instale os arquivos do programa [!DNL Insight Server] conforme descrito em [Instalando os arquivos do programa do servidor Insight](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088). Certifique-se de duplicar a estrutura de diretório que foi usada no [!DNL Insight Server] principal. Por exemplo, se [!DNL Insight Server] estiver instalado em [!DNL C:\Adobe\Server] no principal [!DNL Insight Server], você também deverá instalá-lo em [!DNL C:\Adobe\Server] no processamento [!DNL Insight Servers].
1. Instale o certificado digital emitido pelo Adobe para este processamento específico [!DNL Insight Server]. Consulte [Download e instalação de certificados digitais](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17) para obter instruções.
1. Usando o Windows Explorer, faça o seguinte no processamento [!DNL Insight Server]:

   1. Exclua a pasta **[!UICONTROL Components]**.
   1. Renomeie a pasta [!DNL Components for Processing Servers] como Componentes.

1. Usando um editor de texto como o Bloco de notas, abra o arquivo [!DNL Synchronize.cfg] no diretório Componentes no processamento [!DNL Insight Server].
1. Adicione o endereço IP do principal (primário) [!DNL Insight Server] à segunda linha desse arquivo, conforme mostrado no fragmento de arquivo a seguir. Não edite mais nada neste arquivo.

   ```
   component = SynchronizeComponent:
     Cluster Primary Server Address = string: PrimaryIPAddress
     Directories = vector: 7 items
       0 = SynchronizeDir:
         Local Path = string: Profiles\\
         Remote URI = string: /Profiles/
       1 = SynchronizeDir:
         Local Path = string: Lookups\\
         Remote URI = string: /Lookups/
       . . .
   ```

1. Salve o arquivo.
1. Inicie o [!DNL Insight Server] conforme descrito em [Registrar o Insight Server como um Windows Service](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

   Você concluiu a instalação do cluster [!DNL Insight Server]. Em seguida, configure o perfil do conjunto de dados a ser executado no cluster, conforme descrito na seção a seguir.
