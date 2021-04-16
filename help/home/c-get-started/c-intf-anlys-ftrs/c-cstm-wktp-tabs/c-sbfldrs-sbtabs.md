---
description: Por padrão, as guias recém-criadas exibem as subpastas dentro do diretório associado como subdiretórios hierárquicos e suspensos em vez de subguias.
title: Exibir subpastas como subguias
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Exibir subpastas como subguias{#display-subfolders-as-subtabs}

Por padrão, as guias recém-criadas exibem as subpastas dentro do diretório associado como subdiretórios hierárquicos e suspensos em vez de subguias.

Você pode exibir subpastas como sub-guias (como mostrado no exemplo a seguir) ao colocar um arquivo [!DNL empty folder.useTabs] na pasta *nome do perfil de trabalho*\Workspaces\*nome da guia* no diretório de instalação do Data Workbench.

O exemplo a seguir mostra a guia [!DNL Custom] com subdiretórios suspensos.

![](assets/client-sub.png)

Se você colocar um arquivo [!DNL empty folder.useTabs] na pasta Espaços de trabalho\Personalizado , todas as subpastas dentro da pasta Personalizada serão exibidas nas [!DNL Worktop] como subguias, conforme mostrado no exemplo a seguir:

![](assets/client-sub2.png)

**Para exibir subpastas como subguias na[!DNL Worktop]**

>[!NOTE]
>
>Cada nível de diretório deve ter um arquivo [!DNL Tab Name.useTabs] para que o conteúdo da subpasta apareça como sub-guias em vez de subdiretórios hierárquicos e suspensos.

1. No [!DNL Profile Manager], clique em **[!UICONTROL Workspaces]** para visualizar seu conteúdo.
1. Na coluna *nome do perfil de trabalho*, clique com o botão direito do mouse na marca de seleção de um dos arquivos [!DNL folder.useTabs] e clique em **[!UICONTROL Copy]**.
1. Clique com o botão direito do mouse na coluna [!DNL User] da pasta Espaços de trabalho\*nome da guia* e clique em **[!UICONTROL Paste]**. As subpastas dentro dessa guia agora são exibidas como sub-guias.
1. (Opcional) Para disponibilizar essa alteração para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção branca do arquivo [!DNL new folder.useTabs] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**.
