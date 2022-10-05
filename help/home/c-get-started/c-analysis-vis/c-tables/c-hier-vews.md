---
description: As exibições de hierarquia estão disponíveis somente ao usar o aplicativo Site ou HBX.
title: Aplicar visualizações de hierarquia
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
exl-id: 27a69404-40d3-44ab-bf5c-b2a5d8d836c2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Aplicar visualizações de hierarquia{#apply-hierarchy-views}

{{eol}}

As exibições de hierarquia estão disponíveis somente ao usar o aplicativo Site ou HBX.

A exibição de hierarquia exibe as páginas em um site organizado hierarquicamente por nome de arquivo e classificado alfabeticamente. Embora útil para a análise propriamente dita, a exibição de hierarquia também pode ser usada para configurar visualizações avançadas como mapas de processos. Para obter mais informações sobre mapas de processos, consulte [Mapas de processos](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>Se o conjunto de dados foi configurado para ser executado em vários servidores em um cluster, para que esse recurso funcione corretamente, o administrador do sistema deve designar qual máquina funciona como o Servidor central de normalização. Para obter etapas para fazer isso, consulte o capítulo Arquivo de configuração de processamento de log do *Guia de configuração do conjunto de dados*.

![](assets/vis_Table_CompareHierarchy.png)

**Para ativar ou desativar a exibição de hierarquia**

* Em qualquer página ou visualização de URI, clique com o botão direito do mouse em um elemento ou no rótulo da dimensão da página e clique em **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   Um X é exibido ao lado da opção quando a variável [!DNL hierarchy view] está ativo.

   A hierarquia é organizada em seções de sites e páginas usando uma estrutura em árvore. Seções (nós) podem ser expandidas ou condensadas usando o símbolo + ou - ao lado do nome da seção. Páginas individuais não têm um símbolo + ou - ao lado.

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## Mascaramento de elementos de Dimension em uma exibição de hierarquia {#section-e477c469934846da8d807f92fc2f3ed1}

Mascaramento refere-se à seleção de um subconjunto de seus dados ou de um subconjunto dos elementos em uma dimensão. Você mascara ou oculta esses elementos que não deseja incluir na análise. Usar o [!DNL Mask] opções de menu para visualizações de hierarquia, você seleciona a porcentagem mínima de uma métrica que um elemento deve ter para ser exibido na visualização.

**Para mascarar dados usando o [!DNL Mask] opção de menu**

1. Clique com o botão direito do mouse em um elemento ou no rótulo da dimensão e clique em **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. Em Mais que, clique na porcentagem apropriada e, em seguida, clique na métrica que deseja mascarar.

Por exemplo, se você clicar em 0,1% e em Exibições de página, estará mascarando (ocultando) qualquer elemento que tenha menos de 0,1% do número total de exibições de páginas e exibindo qualquer elemento que tenha mais de 0,1% do número total de exibições de páginas. Se você clicar em 0%, estará mascarando todos os elementos com um valor de 0 (zero) para a métrica selecionada.
