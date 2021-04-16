---
description: Para criar uma dimensão de segmento, comece fazendo uma seleção em um espaço de trabalho e, em seguida, adicionando o segmento a uma visualização.
title: Criar dimensões de segmento
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 3%

---

# Criar dimensões de segmento{#create-a-segment-dimensions}

Para criar uma dimensão de segmento, comece fazendo uma seleção em um espaço de trabalho e, em seguida, adicionando o segmento a uma visualização.

**Para criar uma dimensão de segmento**

1. Adicione uma visualização de segmento ao espaço de trabalho. Por exemplo:

   ![](assets/vis_Segment.png)

1. Adicione visualizações ao seu espaço de trabalho que deseja usar para definir seu segmento, em seguida, faça as seleções desejadas para definir seu segmento.
1. Na visualização do segmento, clique com o botão direito do mouse no rótulo do segmento depois do qual deseja adicionar o novo segmento e clique em **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Para criar um novo primeiro segmento, clique com o botão direito do mouse no rótulo **[!UICONTROL Segments]** e clique em **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   Um novo segmento (chamado Novo segmento) é exibido na visualização. O Outro segmento representa todos os dados não incluídos nos segmentos definidos: é efetivamente a diferença entre os dados do conjunto de dados e os dados do segmento.

1. Clique com o botão direito do mouse no segmento recém-criado e clique em **[!UICONTROL Rename Segment]**.
1. Digite um nome descritivo para o novo segmento no campo de nome.

   >[!NOTE]
   >
   >Se um valor de métrica, como um visitante específico em [!DNL Site], atender aos critérios de vários segmentos, o valor de métrica será incluído somente no primeiro segmento listado que corresponder.

**Para salvar a dimensão do segmento**

1. Clique com o botão direito do mouse no rótulo Segmentos e clique em **[!UICONTROL Save Dimension]**. A janela [!DNL Save Dimension As] é exibida. O local de salvamento padrão é a pasta User\*profile name*\Dimension.
1. No campo [!DNL File name], digite um nome descritivo para os segmentos que você está salvando como uma dimensão e clique em **[!UICONTROL Save]**.

Você pode acessar a dimensão de segmento sempre que trabalhar com uma visualização. Também é possível exportar dados associados aos elementos na dimensão salva usando o recurso de exportação de segmento .

Para obter mais informações sobre o recurso de exportação de segmento e instruções para configurá-lo de acordo com suas necessidades, consulte [Configuração de segmentos para exportar](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
