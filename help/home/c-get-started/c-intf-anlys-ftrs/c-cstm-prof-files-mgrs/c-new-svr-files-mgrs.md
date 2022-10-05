---
description: O Gerenciador de Arquivos do Servidor exibe todos os diretórios no diretório de instalação do servidor do Data Workbench, incluindo arquivos de configuração e pesquisa.
title: Criar um gerenciador de arquivos do servidor
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Criar um gerenciador de arquivos do servidor{#create-a-server-files-manager}

{{eol}}

O Gerenciador de Arquivos do Servidor exibe todos os diretórios no diretório de instalação do servidor do Data Workbench, incluindo arquivos de configuração e pesquisa.

Talvez você queira acessar uma parte do [!DNL Server Files Manager] sem precisar navegar em toda a estrutura de diretório ou exibir apenas alguns dos subdiretórios para atender a uma necessidade específica. Por exemplo, talvez você queira criar um [!DNL Server Files Manager] que exibe somente os subdiretórios Controle de acesso e Usuários, permitindo gerenciar seus usuários e seu acesso.

Cada gerente criado deve ter um [!DNL .vw] arquivo. Você pode usar o [!DNL Server Files.vw] como um modelo.

Para obter mais informações sobre o [!DNL Server Files Manager], consulte [O Gerenciador de Arquivos do Servidor](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Para criar um Gerenciador de Arquivos do Servidor**

1. No [!DNL Profile Manager], clique no botão **[!UICONTROL Menu]** , em seguida, o **[!UICONTROL Admin]** diretório. O [!DNL Server Files.vw] O arquivo está localizado aqui.
1. No *nome do perfil* , clique com o botão direito do mouse na marca de seleção do [!DNL Server Files.vw] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para o arquivo aparece no [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção para a [!DNL Server Files.vw] no [!DNL User] e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. O [!DNL Server Files.vw] é aberto.
1. Para remover um diretório, clique com o botão direito do mouse na borda superior do [!DNL Server Files Manager] e clique em **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Para adicionar um diretório, clique com o botão direito do mouse na borda superior do [!DNL Server Files Manager], clique em **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Digite o URI do diretório no campo URI e clique em **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Você pode designar vários diretórios no campo URI. Por exemplo, se você digitar [!DNL Profiles\Marketing\], o gerenciador de arquivos do servidor contém o subdiretório Marketing , mas nenhum outro subdiretório dentro do diretório Perfis .

1. Clique com o botão direito do mouse na parte superior da borda superior do [!DNL Server Files Manager] e clique em **[!UICONTROL Save]**.
1. Para criar um novo gerenciador, altere o nome do arquivo no [!DNL File Name] e clique em **[!UICONTROL Save]**. Para substituir o gerenciador existente, clique em **[!UICONTROL Save]**.
1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção do [!DNL .vw] no [!DNL User] coluna.

   Em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
