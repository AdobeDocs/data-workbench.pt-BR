---
description: Essas etapas se aplicam apenas à criação de submenus e itens de menu para o menu Janela do Workspace.
title: Criar um menu de espaço de trabalho e um item de menu
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# Criar um menu de espaço de trabalho e um item de menu{#create-a-workspace-menu-and-menu-item}

{{eol}}

Essas etapas se aplicam apenas à criação de submenus e itens de menu para o menu Janela do Workspace.

Você pode personalizar os menus de métrica e dimensão criando novas pastas e novas métricas e dimensões derivadas. Para obter mais informações, consulte [Criação e edição de métricas derivadas](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) e [Criação e edição de Dimension derivadas](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**Para criar um novo menu de janela do espaço de trabalho**

1. No [!DNL Profile Manager], clique no botão **[!UICONTROL Menu]** para exibir seu conteúdo.
1. No [!DNL User] para o diretório Menu, clique em **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Uma pasta chamada Nova pasta aparecerá no [!DNL File] coluna para [!DNL Menu].

   >[!NOTE]
   >
   >Você também pode criar uma nova pasta para qualquer subdiretório dentro do diretório Menu .

1. Renomeie a nova pasta clicando com o botão direito do mouse no [!DNL User] para a pasta e digitando o novo nome no parâmetro Dir.
1. Adicione os arquivos desejados à nova pasta.
1. (Opcional) Na seção [!DNL User] para a nova pasta, clique em **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Um [!DNL order.txt] o arquivo aparece no [!DNL File] para a nova pasta, e uma marca de seleção para o novo arquivo aparece no [!DNL User] coluna.

1. (Opcional) Edite o [!DNL order.txt] conforme necessário. Consulte [Personalização de menus usando arquivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção branca da pasta no [!DNL User] e clique em **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Para adicionar um novo item de menu a um menu existente**

1. Conclua uma das seguintes etapas:

   * Crie um novo item (visualização, anotação e assim por diante) para adicionar a um menu:

      1. Abra um espaço de trabalho no Data Workbench e crie o item desejado.
      1. Salve o item no seguinte diretório:

         *Diretório de instalação do Data Workbench*\Usuário\*nome do perfil de trabalho*\Trabalho

      1. No [!DNL Profile Manager], clique no botão **[!UICONTROL Work]** para exibir seu conteúdo.
      1. No [!DNL User] , clique com o botão direito do mouse na marca de seleção do arquivo desejado e clique em **[!UICONTROL Copy]**.
      1. No [!DNL User] para a pasta desejada, clique em **[!UICONTROL Paste]**.

         Uma cópia do arquivo é exibida no [!DNL File] para a nova pasta, e uma marca de seleção para o novo arquivo aparece no [!DNL User] coluna.
   * Copie e cole um item existente de um menu (pasta) para outro:

      1. No [!DNL Profile Manager], clique no botão **[!UICONTROL Menu]** para exibir seu conteúdo.
      1. No *nome do perfil de trabalho* , clique com o botão direito do mouse na marca de seleção do arquivo desejado e clique em **[!UICONTROL Make Local]**.
      1. Clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] e clique em **[!UICONTROL Copy]**.
      1. No [!DNL User] para a pasta desejada, clique em **[!UICONTROL Paste]**. Uma cópia do arquivo é exibida no [!DNL File] para a nova pasta, e uma marca de seleção para o novo arquivo aparece no [!DNL User] coluna.


1. (Opcional) Edite o [!DNL order.txt] conforme necessário. Consulte [Personalização de menus usando arquivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção branca para cada arquivo na [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Opcional) Para evitar que um item de menu apareça em vários menus, você deve excluir o arquivo correspondente da pasta original clicando com o botão direito do mouse na marca de seleção do arquivo na *nome do perfil de trabalho* e clicando em **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Repita esta etapa para a marca de seleção do arquivo no [!DNL User] coluna.
