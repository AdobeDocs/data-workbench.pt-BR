---
description: Essas etapas se aplicam apenas à criação de submenus e itens de menu para o menu Janela da Workspace.
solution: Analytics
title: Criar um menu de espaço de trabalho e um item de menu
topic: Data workbench
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Criar um menu de espaço de trabalho e um item de menu{#create-a-workspace-menu-and-menu-item}

Essas etapas se aplicam apenas à criação de submenus e itens de menu para o menu Janela da Workspace.

Você pode personalizar os menus de métrica e dimensão criando novas pastas e novas métricas e dimensões derivadas. Para obter mais informações, consulte [Criação e edição de métricas](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) derivadas e [Criação e edição de dimensões](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)derivadas.

**Para criar um novo menu da janela do espaço de trabalho**

1. No [!DNL Profile Manager], clique no **[!UICONTROL Menu]** diretório para exibir seu conteúdo.
1. Na [!DNL User] coluna do diretório Menu, clique em **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Uma pasta chamada Nova pasta é exibida na [!DNL File] coluna para [!DNL Menu].

   >[!NOTE]
   >
   >Você também pode criar uma nova pasta para qualquer subdiretório no diretório Menu.

1. Renomeie a nova pasta clicando com o botão direito do mouse na [!DNL User] coluna da pasta e digitando o novo nome no parâmetro Dir.
1. Adicione os arquivos desejados à nova pasta.
1. (Opcional) Na [!DNL User] coluna da nova pasta, clique em **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Um [!DNL order.txt] arquivo é exibido na [!DNL File] coluna da nova pasta, e uma marca de seleção para o novo arquivo é exibida na [!DNL User] coluna.

1. (Opcional) Edite o [!DNL order.txt] arquivo conforme necessário. Consulte [Personalização de menus usando arquivos](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.
1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção branca da pasta na [!DNL User] coluna e clique em **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Para adicionar um novo item de menu a um menu existente**

1. Conclua uma das seguintes etapas:

   * Crie um novo item (visualização, anotação e assim por diante) para adicionar a um menu:

      1. Abra um espaço de trabalho na Análise de big data e crie o item desejado.
      1. Salve o item no seguinte diretório:

         *Diretório* de instalação da análise de big data \User\*nome do perfil de trabalho*\Work

      1. No [!DNL Profile Manager], clique no **[!UICONTROL Work]** diretório para exibir seu conteúdo.
      1. Na [!DNL User] coluna, clique com o botão direito do mouse na marca de seleção do arquivo desejado e clique em **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**.

         Uma cópia do arquivo é exibida na [!DNL File] coluna da nova pasta e uma marca de seleção para o novo arquivo é exibida na [!DNL User] coluna.
   * Copie e cole um item existente de um menu (pasta) para outro:

      1. No [!DNL Profile Manager], clique no **[!UICONTROL Menu]** diretório para exibir seu conteúdo.
      1. Na coluna nome *do perfil de* trabalho, clique com o botão direito do mouse na marca de seleção do arquivo desejado e clique em **[!UICONTROL Make Local]**.
      1. Clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna e clique em **[!UICONTROL Copy]**.
      1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**. Uma cópia do arquivo é exibida na [!DNL File] coluna da nova pasta e uma marca de seleção para o novo arquivo é exibida na [!DNL User] coluna.


1. (Opcional) Edite o [!DNL order.txt] arquivo conforme necessário. Consulte [Personalização de menus usando arquivos](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.
1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção branca de cada arquivo na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Opcional) Para evitar que um item de menu apareça em vários menus, você deve excluir o arquivo correspondente de sua pasta original clicando com o botão direito do mouse na marca de seleção do arquivo na coluna de nome *do perfil de* trabalho e clicando em **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Repita essa etapa para a marca de seleção do arquivo na [!DNL User] coluna.

