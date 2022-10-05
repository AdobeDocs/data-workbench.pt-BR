---
description: O Gerenciador de perfis exibe todos os diretórios associados ao seu perfil de trabalho.
title: Criar um gerenciador de perfis
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# Criar um gerenciador de perfis{#create-a-profile-manager}

{{eol}}

O Gerenciador de perfis exibe todos os diretórios associados ao seu perfil de trabalho.

Talvez você queira acessar um subdiretório do [!DNL Profile Manager] sem precisar navegar em toda a estrutura de diretório. Por exemplo, a variável [!DNL Metrics] e [!DNL Workspaces] opções de menu disponíveis na [!DNL Manage] no menu da janela do espaço de trabalho, é possível abrir as pastas Métricas e espaços de trabalho do Gerenciador de perfis , respectivamente.

Para obter mais informações sobre o [!DNL Profile Manager], consulte [O Gerenciador de perfis](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Por padrão, você tem acesso aos seguintes gerentes:

* **[!DNL Metrics Manager]:** Exibe o conteúdo da pasta Métricas do Gerenciador de perfis . Você pode abrir, editar, remover ou copiar as métricas definidas em cada perfil.
* **[!DNL Reports Manager]:** Exibe o conteúdo da pasta Relatórios do Gerenciador de perfis. Você pode abrir, editar, remover ou copiar espaços de trabalho do relatório ou [!DNL report.cfg] arquivos.

* **[!DNL Workspaces Manager]:** Exibe o conteúdo da pasta Espaços de trabalho do Gerenciador de perfis. Todos os arquivos para configurar o [!DNL Worktop]As guias do estão localizadas aqui. Consulte [Personalização de guias de desktop](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

O Data Workbench permite criar gerenciadores de perfil adicionais que exibem um subdiretório do [!DNL Profile Manager]. Cada gerente criado deve ter um [!DNL .vw] que especifica a variável [!DNL Profile Manager] diretório cujo conteúdo é exibido e as propriedades dessa janela. Você pode usar o [!DNL .vw] para qualquer um dos gerentes fornecidos como um modelo.

**Para criar um Gerenciador de perfis**

1. No [!DNL Profile Manager], clique no botão **[!UICONTROL Menu]** para exibir seu conteúdo.
1. No diretório Menu, clique no botão **[!UICONTROL Admin]** e, em seguida, **[!UICONTROL Profile]** diretório. O [!DNL .vw] Os arquivos dos gerentes existentes estão localizados aqui.
1. No *nome do perfil* , clique com o botão direito do mouse na marca de seleção de uma das [!DNL .vw] arquivos (por exemplo, [!DNL Workspaces.vw]) e, em seguida, clique em **[!UICONTROL Make Local]**.

   Uma marca de seleção para o arquivo aparece no [!DNL User] coluna.

1. Clique com o botão direito do mouse na marca de seleção para a [!DNL .vw] no [!DNL User] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. No [!DNL Profile Path] digite o [!DNL Profile Manager] diretório para o qual você deseja criar um novo gerenciador. Certifique-se de incluir a barra (/) após o nome do diretório.

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. No Bloco de notas, clique em **[!UICONTROL File]** > **[!UICONTROL Save As]** para salvar o arquivo editado no *pasta de instalação do Data Workbench*\User\*nome do perfil de trabalho*\Menu\Admin\Profile Management.

   Certifique-se de alterar o nome da variável [!DNL .vw] para refletir o diretório no [!DNL Profile Manager] ao qual corresponde.

1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção do [!DNL .vw] no [!DNL User] e clique em **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
