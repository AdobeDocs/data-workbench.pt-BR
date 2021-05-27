---
description: O Gerenciador de Arquivos do Servidor exibe todos os diretórios no diretório de instalação do servidor do Data Workbench, incluindo arquivos de configuração e pesquisa.
title: Criar um gerenciador de arquivos do servidor
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Criar um gerenciador de arquivos do servidor{#create-a-server-files-manager}

O Gerenciador de Arquivos do Servidor exibe todos os diretórios no diretório de instalação do servidor do Data Workbench, incluindo arquivos de configuração e pesquisa.

Talvez você queira acessar uma parte do [!DNL Server Files Manager] sem precisar navegar em toda a estrutura de diretório ou exibir apenas alguns dos subdiretórios para atender a uma necessidade específica. Por exemplo, você pode criar um [!DNL Server Files Manager] separado que exibe somente os subdiretórios Controle de Acesso e Usuários, permitindo gerenciar seus usuários e seu acesso.

Cada gerente criado deve ter um arquivo [!DNL .vw]. Você pode usar o arquivo [!DNL Server Files.vw] como um modelo.

Para obter mais informações sobre o [!DNL Server Files Manager], consulte [O Gerenciador de Arquivos do Servidor](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Para criar um Gerenciador de Arquivos do Servidor**

1. No [!DNL Profile Manager], clique no diretório **[!UICONTROL Menu]** e, em seguida, no diretório **[!UICONTROL Admin]**. O arquivo [!DNL Server Files.vw] está localizado aqui.
1. Na coluna *nome do perfil*, clique com o botão direito do mouse na marca de seleção do arquivo [!DNL Server Files.vw] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para o arquivo aparece na coluna [!DNL User].
1. Clique com o botão direito do mouse na marca de seleção do arquivo [!DNL Server Files.vw] na coluna [!DNL User] e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. O arquivo [!DNL Server Files.vw] é aberto.
1. Para remover um diretório, clique com o botão direito do mouse na borda superior do [!DNL Server Files Manager] e clique em **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]***.
1. Para adicionar um diretório, clique com o botão direito do mouse na borda superior do [!DNL Server Files Manager], clique em **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Digite o URI do diretório no campo URI e clique em **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Você pode designar vários diretórios no campo URI. Por exemplo, se você digitar [!DNL Profiles\Marketing\], o gerenciador de arquivos do servidor conterá o subdiretório Marketing , mas nenhum outro subdiretório dentro do diretório Perfis .

1. Clique com o botão direito do mouse na borda superior do [!DNL Server Files Manager] e clique em **[!UICONTROL Save]**.
1. Para criar um novo gerenciador, altere o nome do arquivo no campo [!DNL File Name] e clique em **[!UICONTROL Save]**. Para substituir o gerenciador existente, clique em **[!UICONTROL Save]**.
1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção do arquivo [!DNL .vw] na coluna [!DNL User].

   Em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
