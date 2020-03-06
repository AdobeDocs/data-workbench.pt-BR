---
description: Para criar uma dimensão de segmento, comece fazendo uma seleção dentro de um espaço de trabalho e depois adicionando o segmento a uma visualização.
solution: Analytics
title: Criar dimensões de segmento
topic: Data workbench
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Criar dimensões de segmento{#create-a-segment-dimensions}

Para criar uma dimensão de segmento, comece fazendo uma seleção dentro de um espaço de trabalho e depois adicionando o segmento a uma visualização.

**Para criar uma dimensão de segmento**

1. Adicione uma visualização de segmento ao espaço de trabalho. Por exemplo:

   ![](assets/vis_Segment.png)

1. Adicione visualizações ao seu espaço de trabalho que você deseja usar para definir seu segmento e faça as seleções desejadas para definir seu segmento.
1. Na visualização do segmento, clique com o botão direito do mouse no rótulo do segmento após o qual deseja que o novo segmento seja adicionado e clique em **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Para criar um novo primeiro segmento, clique com o botão direito do mouse no **[!UICONTROL Segments]** rótulo e clique em **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   Um novo segmento (chamado Novo segmento) é exibido na visualização. O outro segmento representa todos os dados não incluídos nos segmentos definidos: é efetivamente a diferença entre os dados do conjunto de dados e os dados do segmento.

1. Clique com o botão direito do mouse no segmento recém-criado e clique em **[!UICONTROL Rename Segment]**.
1. Digite um nome descritivo para o novo segmento no campo de nome.

   >[!NOTE]
   >
   >Se um valor de métrica, como um visitante em particular, [!DNL Site]atender aos critérios de vários segmentos, o valor de métrica será incluído somente no primeiro segmento listado correspondente.

**Para salvar a dimensão do segmento**

1. Clique com o botão direito do mouse no rótulo Segmentos e clique em **[!UICONTROL Save Dimension]**. A [!DNL Save Dimension As] janela é exibida. O local de salvamento padrão é a pasta User\*profile name*\Dimensions.
1. No [!DNL File name] campo, digite um nome descritivo para os segmentos que você está salvando como uma dimensão e clique em **[!UICONTROL Save]**.

Você pode acessar a dimensão do segmento sempre que estiver trabalhando com uma visualização. Também é possível exportar dados associados aos elementos em sua dimensão salva usando o recurso de exportação de segmento.

Para obter mais informações sobre o recurso de exportação de segmento e instruções para configurá-lo de acordo com suas necessidades, consulte [Configuração de segmentos para exportação](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
