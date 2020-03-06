---
description: O Gerenciador de Arquivos do Servidor exibe todos os diretórios no diretório de instalação do servidor do Análise de big data, incluindo arquivos de configuração e pesquisa.
solution: Analytics
title: Criar um Gerenciador de Arquivos do Servidor
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Criar um Gerenciador de Arquivos do Servidor{#create-a-server-files-manager}

O Gerenciador de Arquivos do Servidor exibe todos os diretórios no diretório de instalação do servidor do Análise de big data, incluindo arquivos de configuração e pesquisa.

Talvez você queira acessar uma parte do diretório [!DNL Server Files Manager] sem precisar navegar em toda a estrutura do diretório ou exibir apenas alguns dos subdiretórios para atender a uma necessidade específica. Por exemplo, você pode querer criar um separado [!DNL Server Files Manager] que exiba apenas os subdiretórios Controle de acesso e Usuários, permitindo que você gerencie seus usuários e seus acessos.

Cada gerente criado deve ter um [!DNL .vw] arquivo. Você pode usar o [!DNL Server Files.vw] arquivo como modelo.

Para obter mais informações sobre o [!DNL Server Files Manager], consulte [O Gerenciador](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)de Arquivos do Servidor.

**Para criar um Gerenciador de Arquivos do Servidor**

1. No diretório [!DNL Profile Manager], clique no **[!UICONTROL Menu]** diretório e, em seguida, no **[!UICONTROL Admin]** . O [!DNL Server Files.vw] arquivo está localizado aqui.
1. Na coluna nome *do* perfil, clique com o botão direito do mouse na marca de seleção do [!DNL Server Files.vw] arquivo e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para o arquivo é exibida na [!DNL User] coluna.
1. Clique com o botão direito do mouse na marca de seleção do [!DNL Server Files.vw] arquivo na [!DNL User] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. O [!DNL Server Files.vw] arquivo é aberto.
1. Para remover um diretório, clique com o botão direito do mouse na borda superior do diretório [!DNL Server Files Manager] e clique em **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Para adicionar um diretório, clique com o botão direito do mouse na borda superior do diretório [!DNL Server Files Manager], clique em **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Digite o URI do diretório no campo URI e clique em **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Você pode designar vários diretórios no campo URI. Por exemplo, se você digitar [!DNL Profiles\Marketing\], o gerenciador de arquivos do servidor conterá o subdiretório Marketing, mas nenhum outro subdiretório dentro do diretório Perfis.

1. Clique com o botão direito do mouse na borda superior da borda [!DNL Server Files Manager] e clique em **[!UICONTROL Save]**.
1. Para criar um novo gerente, altere o nome do arquivo no [!DNL File Name] campo e clique em **[!UICONTROL Save]**. Para substituir o gerenciador existente, clique em **[!UICONTROL Save]**.
1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção do [!DNL .vw] arquivo na [!DNL User] coluna.

   Em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

