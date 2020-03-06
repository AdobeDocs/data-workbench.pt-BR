---
description: Etapas para implantar o painel no IIS.
solution: Analytics
title: Implantação do painel
topic: Data workbench
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Implantação do painel{#deploying-the-dashboard}

Etapas para implantar o painel no IIS.

1. Crie uma pasta de instalação para instalar o painel, como [!DNL c:\inetpub\wwwroot\dashboard].
1. Crie o pool de aplicativos do painel no IIS.
1. Abra o Console do Gerenciador do IIS.
1. Vá para **[!UICONTROL Application Pools]**.
1. Selecione **[!UICONTROL Add Application Pool…]**no **[!UICONTROL Actions]** menu à direita.
1. No **[!UICONTROL Add Application Pool]** formulário, use o painel para o nome e selecione .NET Framework v.4.0.xxxxxx como sua versão do .NET Framework.
1. Deixe outros campos como padrão e clique em **[!UICONTROL OK]** para criar o pool de aplicativos.
1. Implante o aplicativo do painel.
1. Abra o Console do Gerenciador do IIS.
1. Expanda a pasta **[!UICONTROL Default Web Site]**, você deverá ver a pasta criada em c:\inetpub\wwwroot\dashboard by default.
1. Clique com o botão direito do mouse na pasta e selecione **[!UICONTROL Convert to Application]**.
1. Selecione o **[!UICONTROL Application Pool]**criado na Etapa 2 (por exemplo, &quot;Painel&quot;).
1. Em **[!UICONTROL Sites]**, clique com o botão direito do mouse no site para o qual deseja implantar (por exemplo, &quot;Site padrão&quot;).
1. Selecionar **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Navegue até o arquivo de implantação do painel fornecido pela Adobe e selecione-o.
1. Clique **[!UICONTROL Next]** duas vezes para continuar com a tela Inserir informações do aplicativo.
1. Nessa tela, você pode optar por personalizar a implantação do painel.
1. Para **[!UICONTROL Application Path]**, digite o nome da pasta selecionado anteriormente.
1. Em **[!UICONTROL Disable Automatic Database Upgrade]**, digite `False`, visto que esta é uma nova instalação.
1. Personalize sua cadeia de conexão, se necessário. Por exemplo:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Clique em **[!UICONTROL Next]** e o IIS começará a instalar o aplicativo.
1. Após a conclusão da instalação, você não deverá ver erros no registro de instalação.
