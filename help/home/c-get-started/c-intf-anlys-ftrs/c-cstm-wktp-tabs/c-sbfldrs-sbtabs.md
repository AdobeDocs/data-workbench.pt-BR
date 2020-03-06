---
description: Por padrão, as guias recém-criadas exibem as subpastas dentro do diretório associado como subdiretórios hierárquicos e suspensos em vez de como subguias.
solution: Analytics
title: Exibir subpastas como subguias
topic: Data workbench
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exibir subpastas como subguias{#display-subfolders-as-subtabs}

Por padrão, as guias recém-criadas exibem as subpastas dentro do diretório associado como subdiretórios hierárquicos e suspensos em vez de como subguias.

É possível exibir subpastas como subguias (como mostrado no exemplo a seguir) inserindo um [!DNL empty folder.useTabs] arquivo no nome **\Workspaces\*pasta do nome da guia* no diretório de instalação do Análise de big data.

O exemplo a seguir mostra a [!DNL Custom] guia com subdiretórios suspensos.

![](assets/client-sub.png)

Se você colocar um [!DNL empty folder.useTabs] arquivo na pasta Espaços de trabalho\Personalizado, todas as subpastas dentro da pasta Personalizado serão exibidas na [!DNL Worktop] guia como subguias, como mostrado no exemplo a seguir:

![](assets/client-sub2.png)

**Para exibir subpastas como subguias na variável[!DNL Worktop]**

>[!NOTE]
>
>Cada nível de diretório deve ter um [!DNL Tab Name.useTabs] arquivo para que o conteúdo da subpasta apareça como subguias, em vez de subdiretórios hierárquicos e suspensos.

1. No [!DNL Profile Manager], clique em **[!UICONTROL Workspaces]** para exibir o conteúdo.
1. Na coluna nome *do perfil de* trabalho, clique com o botão direito do mouse na marca de seleção de um dos [!DNL folder.useTabs] arquivos e clique em **[!UICONTROL Copy]**.
1. Clique com o botão direito do mouse na [!DNL User] coluna da pasta Espaços de trabalho\*nome da guia* e clique em **[!UICONTROL Paste]**. As subpastas dentro dessa guia agora são exibidas como subguias.
1. (Opcional) Para disponibilizar essa alteração para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção branca do [!DNL new folder.useTabs] arquivo na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

