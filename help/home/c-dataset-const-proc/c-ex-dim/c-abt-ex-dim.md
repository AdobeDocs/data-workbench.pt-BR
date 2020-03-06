---
description: O Insight Server (InsightServer64.exe) permite que você defina dimensões personalizadas a partir de dados de eventos ou dados de pesquisa.
solution: Analytics
title: Sobre dimensões estendidas
topic: Data workbench
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sobre dimensões estendidas{#about-extended-dimensions}

O Insight Server (InsightServer64.exe) permite que você defina dimensões personalizadas a partir de dados de eventos ou dados de pesquisa.

Todas as dimensões personalizadas que você definir são chamadas de dimensões estendidas. Você pode usá-los para criar visualizações, criar métricas estendidas ou executar análises para entender as operações e os problemas associados ao seu canal de negócios. É possível definir vários tipos de dimensões estendidas no [!DNL Transformation.cfg] arquivo ou em [!DNL Transformation Dataset Include] arquivos.

Uma dimensão estendida representa uma relação entre valores de campo de log e uma dimensão pai. Uma dimensão pai pode ser qualquer dimensão contável definida pelo usuário. Consulte Dimensões [contáveis](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Especifique o pai ao definir a dimensão no [!DNL Transformation.cfg] arquivo ou em um [!DNL Transformation Dataset Include] arquivo. O pai de uma dimensão é o mesmo que seu nível. Por exemplo, se você definir uma dimensão com um pai de Sessão, essa dimensão será uma dimensão em nível de sessão.

>[!NOTE]
>
>Os valores do campo de log podem vir dos valores inerentes disponíveis nos arquivos de log ( [!DNL .vsl]) ou em outras fontes de dados de eventos ou de campos de log estendidos criados pelo uso de transformações.

Para adicionar uma dimensão estendida a uma visualização, acesse-a da lista Estendida no [!DNL Select Dimension] menu. Por exemplo, para adicionar uma dimensão estendida a uma visualização de gráfico, clique com o botão direito do mouse na área de trabalho e clique em **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Se você deseja organizar a lista de suas dimensões estendidas na interface da análise de big data, é possível mover as dimensões estendidas para subpastas criadas. Consulte o capítulo Interfaces administrativas do Guia ** do usuário da Análise de big data. Se você fizer isso, os nomes das subpastas também aparecerão no menu, como em Adicionar visualização > Gráfico > Estendido > &lt;nome *da* subpasta> > &lt;nome *da* dimensão>.

Para ver todas as dimensões que foram definidas para seu perfil de conjunto de dados e o tamanho do buffer para cada uma, abra a [!DNL Detailed Status] interface na análise de big data e clique em **[!UICONTROL Performance]**, em seguida, **[!UICONTROL Dimensions]** para expandir os nós. O tamanho do buffer, que controla os tempos de consulta, é expresso em MB. Para obter mais informações sobre a [!DNL Detailed Status] interface, consulte o guia Administração e instalação do servidor.
