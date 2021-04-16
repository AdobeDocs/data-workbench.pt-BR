---
description: Etapas para implantar o painel no IIS.
title: Implantar painel
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# Implantar painel{#deploying-the-dashboard}

Etapas para implantar o painel no IIS.

1. Crie uma pasta de instalação para instalar o painel, como [!DNL c:\inetpub\wwwroot\dashboard].
1. Crie o pool de aplicativos do painel no IIS.
1. Abra o Console do Gerenciador do IIS.
1. Vá para **[!UICONTROL Application Pools]**.
1. Selecione **[!UICONTROL Add Application Pool…]**no menu **[!UICONTROL Actions]** à direita.
1. No formulário **[!UICONTROL Add Application Pool]**, use o painel para o nome e selecione .NET Framework v.4.0.xxxxxx como sua versão do .NET Framework.
1. Deixe outros campos como padrão e clique em **[!UICONTROL OK]** para criar o pool de aplicativos.
1. Implante o aplicativo do painel.
1. Abra o Console do Gerenciador do IIS.
1. Expanda o **[!UICONTROL Default Web Site]**, você deve ver a pasta que criou em c:\inetpub\wwwroot\dashboard by default.
1. Clique com o botão direito do mouse na pasta e selecione **[!UICONTROL Convert to Application]**.
1. Selecione o **[!UICONTROL Application Pool]**criado na Etapa 2 (por exemplo, &quot;Painel&quot;).
1. Em **[!UICONTROL Sites]**, clique com o botão direito do mouse no site para o qual deseja implantar (por exemplo, &quot;Site padrão&quot;).
1. Selecionar **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Procure e selecione o arquivo de implantação do painel fornecido pelo Adobe.
1. Clique **[!UICONTROL Next]** duas vezes para prosseguir para a tela Inserir informações do aplicativo .
1. Nessa tela, você pode optar por personalizar a implantação do painel.
1. Para **[!UICONTROL Application Path]**, insira o nome da pasta selecionado anteriormente.
1. Em **[!UICONTROL Disable Automatic Database Upgrade]**, digite `False`, pois esta é uma nova instalação.
1. Personalize a string de conexão, se necessário. Por exemplo:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Clique em **[!UICONTROL Next]** e o IIS começará a instalar o aplicativo.
1. Depois que a instalação for concluída, você não verá erros no registro de instalação.
