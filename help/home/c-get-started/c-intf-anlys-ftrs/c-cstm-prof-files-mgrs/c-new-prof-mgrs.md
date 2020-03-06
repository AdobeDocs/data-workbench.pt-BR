---
description: O Gerenciador de perfis exibe todos os diretórios associados ao seu perfil de trabalho.
solution: Analytics
title: Criar um gerenciador de perfis
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Criar um gerenciador de perfis{#create-a-profile-manager}

O Gerenciador de perfis exibe todos os diretórios associados ao seu perfil de trabalho.

Talvez você queira acessar um subdiretório do [!DNL Profile Manager] sem precisar navegar por toda a estrutura do diretório. Por exemplo, as opções de menu [!DNL Metrics] e de menu disponíveis no [!DNL Workspaces] [!DNL Manage] menu da janela da área de trabalho permitem abrir as pastas Métricas e Espaços de Trabalho do Gerenciador de Perfis, respectivamente.

Para obter mais informações sobre o [!DNL Profile Manager], consulte [O gerenciador](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)de perfis.

Por padrão, você tem acesso aos seguintes gerentes:

* **[!DNL Metrics Manager]:**Exibe o conteúdo da pasta Métricas do Gerenciador de perfis. Você pode abrir, editar, remover ou copiar as métricas definidas em cada perfil.
* **[!DNL Reports Manager]:**Exibe o conteúdo da pasta Relatórios do Gerenciador de perfis. Você pode abrir, editar, remover ou copiar espaços de trabalho ou[!DNL report.cfg]arquivos de relatório.

* **[!DNL Workspaces Manager]:**Exibe o conteúdo da pasta de espaços de trabalho do Gerenciador de perfis. Todos os arquivos para configurar as guias[!DNL Worktop]do estão localizados aqui. Consulte[Personalizar guias](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)de desktop.

A Análise de big data permite criar gerenciadores de perfil adicionais que exibem um subdiretório do [!DNL Profile Manager]. Cada gerente criado deve ter um [!DNL .vw] arquivo que especifique o [!DNL Profile Manager] diretório cujo conteúdo ele mostra e as propriedades dessa janela. Você pode usar o [!DNL .vw] arquivo para qualquer um dos gerentes fornecidos como modelo.

**Para criar um Gerenciador de perfis**

1. No [!DNL Profile Manager], clique no **[!UICONTROL Menu]** diretório para exibir seu conteúdo.
1. No diretório Menu, clique no **[!UICONTROL Admin]** diretório e, em seguida, no **[!UICONTROL Profile]** diretório. Os [!DNL .vw] arquivos dos gerentes existentes estão localizados aqui.
1. Na coluna nome *do* perfil, clique com o botão direito do mouse na marca de seleção de um dos [!DNL .vw] arquivos (por exemplo, [!DNL Workspaces.vw]) e clique em **[!UICONTROL Make Local]**.

   Uma marca de seleção para o arquivo é exibida na [!DNL User] coluna.

1. Clique com o botão direito do mouse na marca de seleção do [!DNL .vw] arquivo na [!DNL User] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. No [!DNL Profile Path] campo, digite o [!DNL Profile Manager] diretório para o qual deseja criar um novo gerente. Certifique-se de incluir a barra (/) após o nome do diretório.

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

1. No Bloco de notas, clique em **[!UICONTROL File]** > **[!UICONTROL Save As]** para salvar o arquivo editado na pasta **\User\*nome do perfil de trabalho*\Menu\Admin\Profile Management.

   Certifique-se de alterar o nome do [!DNL .vw] arquivo para refletir o diretório no [!DNL Profile Manager] qual ele corresponde.

1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção do [!DNL .vw] arquivo na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

