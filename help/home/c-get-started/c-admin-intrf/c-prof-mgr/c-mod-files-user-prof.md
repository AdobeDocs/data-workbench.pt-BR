---
description: Você pode usar o Gerenciador de perfis para baixar arquivos que deseja modificar.
solution: Analytics
title: Modificar arquivos locais no perfil do usuário
topic: Data workbench
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificar arquivos locais no perfil do usuário{#modify-local-files-in-the-user-profile}

Você pode usar o Gerenciador de perfis para baixar arquivos que deseja modificar.

Você pode desejar baixar um arquivo para substituir o arquivo existente e local pela versão original do arquivo ou abrir, exibir e modificar arquivos que não podem ser acessados nos menus da área de trabalho.

**Para baixar um arquivo**

1. No [!DNL Profile Manager], abra as pastas e subpastas necessárias para localizar o arquivo que deseja baixar.
1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo e clique em **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Os arquivos de configuração ( [!DNL .cfg]), dimensão ( [!DNL .dim]) e métrica ( [!DNL .metric]) podem ser editados diretamente em uma pasta de perfil e salvos no servidor sem torná-los locais e salvos separadamente no servidor. Basta clicar com o botão direito do mouse na marca de seleção ao lado do nome do arquivo e clicar em **[!UICONTROL Open]** > **na estação de trabalho**.

Depois que o arquivo for baixado para o computador local, uma marca de seleção aparecerá na [!DNL User] coluna, indicando que uma cópia local do arquivo reside na pasta User\*profile name* do seu computador. Observe que a marca de seleção tem a mesma cor que a marca de seleção na coluna de nome *do* perfil. Isso indica que o arquivo local tem a mesma data e hora Modificadas que o arquivo na pasta do nome *do* perfil.

**Para modificar o arquivo**

1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo na [!DNL User] coluna.
1. Clique em uma das seguintes opções de menu, dependendo de como deseja editar o arquivo:

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** se você estiver editando um [!DNL .vw] arquivo ou um [!DNL .cfg] arquivo em um espaço de trabalho.

   * **Abrir** > **em vw. Editor **se você estiver editando um arquivo .vw para adicionar novos parâmetros.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** se você estiver abrindo um arquivo de texto ou precisar adicionar novos parâmetros a um [!DNL .cfg] arquivo.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** se quiser abrir a pasta na qual o arquivo está localizado no computador

1. Edite o arquivo conforme desejado e salve-o.

Na página [!DNL Profile Manager], observe que a marca de seleção na [!DNL User] coluna do arquivo editado mudou de cor. Isso indica que o arquivo local agora é diferente da versão na pasta de nome *do* perfil. Se necessário, você pode publicar a versão revisada do arquivo no perfil para uso por outros usuários que trabalham com esse perfil.
