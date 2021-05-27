---
description: O Gerenciador de perfis exibe todos os diretórios associados ao seu perfil de trabalho.
title: Criar um gerenciador de perfis
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# Criar um gerenciador de perfis{#create-a-profile-manager}

O Gerenciador de perfis exibe todos os diretórios associados ao seu perfil de trabalho.

Talvez você queira acessar um subdiretório do [!DNL Profile Manager] sem precisar navegar por toda a estrutura de diretório. Por exemplo, as opções de menu [!DNL Metrics] e [!DNL Workspaces] disponíveis no menu [!DNL Manage] do menu da janela do espaço de trabalho permitem abrir as pastas Métricas e espaços de trabalho do Gerenciador de perfis , respectivamente.

Para obter mais informações sobre o [!DNL Profile Manager], consulte [O gerenciador de perfis](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Por padrão, você tem acesso aos seguintes gerentes:

* **[!DNL Metrics Manager]:** Exibe o conteúdo da pasta Métricas do Gerenciador de perfis. Você pode abrir, editar, remover ou copiar as métricas definidas em cada perfil.
* **[!DNL Reports Manager]:** Exibe o conteúdo da pasta Relatórios do Gerenciador de perfis. Você pode abrir, editar, remover ou copiar espaços de trabalho do relatório ou arquivos [!DNL report.cfg].

* **[!DNL Workspaces Manager]:** Exibe o conteúdo da pasta Espaços de trabalho do Gerenciador de perfis. Todos os arquivos para configurar as guias do [!DNL Worktop] estão localizados aqui. Consulte [Personalizando Guias da Área de Trabalho](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

O Data Workbench permite criar gerenciadores de perfil adicionais que exibem um subdiretório do [!DNL Profile Manager]. Cada gerenciador criado deve ter um arquivo [!DNL .vw] que especifique o diretório [!DNL Profile Manager] cujo conteúdo será exibido e as propriedades dessa janela. Você pode usar o arquivo [!DNL .vw] para qualquer um dos gerentes fornecidos como um modelo.

**Para criar um Gerenciador de perfis**

1. No [!DNL Profile Manager], clique no diretório **[!UICONTROL Menu]** para visualizar seu conteúdo.
1. No diretório Menu , clique no diretório **[!UICONTROL Admin]** e, em seguida, no diretório **[!UICONTROL Profile]**. Os arquivos [!DNL .vw] dos gerentes existentes estão localizados aqui.
1. Na coluna *nome do perfil*, clique com o botão direito do mouse na marca de seleção para um dos arquivos [!DNL .vw] (por exemplo, [!DNL Workspaces.vw]) e clique em **[!UICONTROL Make Local]**.

   Uma marca de seleção para o arquivo aparece na coluna [!DNL User].

1. Clique com o botão direito do mouse na marca de seleção do arquivo [!DNL .vw] na coluna [!DNL User] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. No campo [!DNL Profile Path], digite o diretório [!DNL Profile Manager] para o qual deseja criar um novo gerenciador. Certifique-se de incluir a barra (/) após o nome do diretório.

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

1. No Bloco de notas, clique em **[!UICONTROL File]** > **[!UICONTROL Save As]** para salvar o arquivo editado na *pasta de instalação do Data Workbench*\User\*nome do perfil de trabalho*\Menu\Admin\Profile Management.

   Certifique-se de alterar o nome do arquivo [!DNL .vw] para refletir o diretório no [!DNL Profile Manager] ao qual ele corresponde.

1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção do arquivo [!DNL .vw] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**.
