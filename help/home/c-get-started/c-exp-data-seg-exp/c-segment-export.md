---
description: Crie cabeçalhos de exportação de coluna personalizados para seus arquivos de exportação de segmento para adicionar descrições facilmente compreendidas para segmentos exportados. Esse recurso de exportação também permite a saída como arquivos TSV e CSV.
title: Exportar segmentos com cabeçalhos personalizados
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---


# Exportar segmentos com cabeçalhos personalizados{#segment-export-with-custom-headers}

Crie cabeçalhos de exportação de coluna personalizados para seus arquivos de exportação de segmento para adicionar descrições facilmente compreendidas para segmentos exportados. Esse recurso de exportação também permite a saída como arquivos TSV e CSV.

Uma nova funcionalidade foi adicionada à Exportação de segmento, incluindo a capacidade de exportar com um cabeçalho ou nos formatos CSV e TSV.

Você pode criar cabeçalhos de coluna para seus arquivos de exportação.

## Criando uma nova exportação de segmento {#section-cffff55855f8467ea468b71393ab7676}

1. Abra um espaço de trabalho e clique com o botão direito do mouse em **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. Clique com o botão direito do mouse e selecione **[!UICONTROL Add Level > Extended]** > Escolher um item.
1. Clique com o botão direito do mouse no título e selecione **[!UICONTROL Add Attribute.]** Selecionar uma dimensão no menu.

1. Clique com o botão direito do mouse no título e selecione **[!UICONTROL Add Metric.]** Selecionar uma métrica no menu.

1. Clique com o botão direito do mouse no título e selecione **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** preenche automaticamente o Nome da coluna com o nome da métrica. **[!UICONTROL New Segment Export]** requer que você defina um nome personalizado. ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >O campo Nome da coluna não pode ser deixado em branco ou o cabeçalho não estará presente.

1. Clique com o botão direito do mouse e nomeie o segmento e clique em **[!UICONTROL Save Export File]**.

   Uma janela de exportação será aberta.

1. Clique com o botão direito do mouse no nome da exportação e clique em **Salvar como`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. Clique com o botão direito do mouse em [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. Localize o arquivo de exportação que você acabou de criar e salve-o em um perfil existente.

   ![](assets/segment_export_headers_8.png)

