---
description: Você pode usar o Gerenciador de perfis para baixar arquivos que deseja modificar.
title: Modificar arquivos locais no perfil do usuário
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Modificar arquivos locais no perfil do usuário{#modify-local-files-in-the-user-profile}

{{eol}}

Você pode usar o Gerenciador de perfis para baixar arquivos que deseja modificar.

Talvez você queira baixar um arquivo para substituir seu arquivo local existente pela versão original do arquivo ou abrir, exibir e modificar arquivos que não podem ser acessados nos menus do espaço de trabalho.

**Para baixar um arquivo**

1. No [!DNL Profile Manager], abra as pastas e subpastas necessárias para localizar o arquivo que deseja baixar.
1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo e clique em **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Configuração ( [!DNL .cfg]), dimensão ( [!DNL .dim]) e métrica ( [!DNL .metric]) os arquivos podem ser editados diretamente em uma pasta de perfil e salvos no servidor sem torná-los locais e salvá-los separadamente no servidor. Basta clicar com o botão direito do mouse na marca de seleção ao lado do nome do arquivo e clicar em **[!UICONTROL Open]** > **na estação de trabalho**.

Após o download do arquivo para o computador local, uma marca de seleção aparece no [!DNL User] indica que uma cópia local do arquivo reside na pasta User\*profile name* do seu computador. Observe que a marca de seleção tem a mesma cor que a marca de seleção no *nome do perfil* coluna. Isso indica que o arquivo local tem a mesma data e hora de Modificação que o arquivo na *nome do perfil* pasta.

**Como modificar o arquivo**

1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo na [!DNL User] coluna.
1. Clique em uma das seguintes opções de menu, dependendo de como você deseja editar o arquivo:

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** se você estiver editando um [!DNL .vw] ou um [!DNL .cfg] em um espaço de trabalho.

   * **Abrir** > **em vw Editor **se você estiver editando um arquivo .vw para adicionar novos parâmetros.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** se você estiver abrindo um arquivo de texto ou precisar adicionar novos parâmetros a um [!DNL .cfg] arquivo.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** se quiser abrir a pasta na qual o arquivo está localizado em seu computador

1. Edite o arquivo conforme desejado e salve-o.

No [!DNL Profile Manager], observe que a marca de seleção no [!DNL User] a coluna do arquivo editado mudou de cor. Isso indica que o arquivo local agora é diferente da versão no *nome do perfil* pasta. Se necessário, você pode publicar a versão revisada do arquivo no perfil para uso por outros usuários que trabalham com esse perfil.
