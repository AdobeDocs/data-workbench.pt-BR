---
description: Por padrão, as guias recém-criadas exibem as subpastas dentro do diretório associado como subdiretórios hierárquicos e suspensos em vez de subguias.
title: Exibir subpastas como subguias
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Exibir subpastas como subguias{#display-subfolders-as-subtabs}

{{eol}}

Por padrão, as guias recém-criadas exibem as subpastas dentro do diretório associado como subdiretórios hierárquicos e suspensos em vez de subguias.

É possível exibir subpastas como sub-guias (como mostrado no exemplo a seguir) ao colocar uma [!DNL empty folder.useTabs] no *nome do perfil de trabalho*\Espaços de trabalho\*pasta do nome da guia* no diretório de instalação do Data Workbench.

O exemplo a seguir mostra o [!DNL Custom] com subdiretórios suspensos.

![](assets/client-sub.png)

Se você colocar um [!DNL empty folder.useTabs] na pasta Espaços de Trabalho\Personalizados, todas as subpastas dentro da pasta Personalizada são exibidas na [!DNL Worktop] como subguias, conforme mostrado no exemplo a seguir:

![](assets/client-sub2.png)

**Para exibir subpastas como subguias na[!DNL Worktop]**

>[!NOTE]
>
>Cada nível de diretório deve ter uma [!DNL Tab Name.useTabs] para que o conteúdo da subpasta apareça como sub-guias em vez de subdiretórios hierárquicos e suspensos.

1. No [!DNL Profile Manager], clique em **[!UICONTROL Workspaces]** para visualizar seu conteúdo.
1. No *nome do perfil de trabalho* , clique com o botão direito do mouse na marca de seleção de uma das [!DNL folder.useTabs] e clique em **[!UICONTROL Copy]**.
1. Clique com o botão direito do mouse no [!DNL User] coluna para a pasta Espaços de trabalho\*nome da guia* e clique em **[!UICONTROL Paste]**. As subpastas dentro dessa guia agora são exibidas como sub-guias.
1. (Opcional) Para disponibilizar essa alteração para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção branca da variável [!DNL new folder.useTabs] no [!DNL User] e clique em **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
