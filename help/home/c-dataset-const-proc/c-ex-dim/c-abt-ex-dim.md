---
description: O Insight Server (InsightServer64.exe) permite definir dimensões personalizadas a partir de dados de evento ou dados de pesquisa.
title: Sobre dimensões estendidas
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Sobre dimensões estendidas{#about-extended-dimensions}

{{eol}}

O Insight Server (InsightServer64.exe) permite definir dimensões personalizadas a partir de dados de evento ou dados de pesquisa.

Qualquer dimensão personalizada que você definir será chamada de dimensões estendidas. Você pode usá-las para criar visualizações, criar métricas estendidas ou executar análises para entender as operações e os problemas associados ao seu canal de negócios. Você pode definir vários tipos de dimensões estendidas na variável [!DNL Transformation.cfg] ou em [!DNL Transformation Dataset Include] arquivos.

Uma dimensão estendida representa uma relação entre valores de campo de log e uma dimensão pai. Uma dimensão pai pode ser qualquer dimensão contável definida pelo usuário. Consulte [Dimension contáveis](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Você especifica o pai ao definir a dimensão no [!DNL Transformation.cfg] ou um [!DNL Transformation Dataset Include] arquivo. O pai de uma dimensão é o mesmo que seu nível. Por exemplo, se você definir uma dimensão com um pai de Sessão, essa dimensão será uma dimensão em nível de sessão.

>[!NOTE]
>
>Os valores do campo de log podem vir dos valores inerentes disponíveis no log ( [!DNL .vsl]) arquivos ou outras fontes de dados do evento ou de campos de log estendidos criados por meio do uso de transformações.

Para adicionar uma dimensão estendida a uma visualização, acesse-a da lista Estendida na variável [!DNL Select Dimension] menu. Por exemplo, para adicionar uma dimensão estendida a uma visualização de gráfico, clique com o botão direito do mouse no espaço de trabalho e clique em **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Se quiser organizar a lista das dimensões estendidas na interface do Data Workbench, é possível mover as dimensões estendidas para subpastas que você cria. Consulte o capítulo Interfaces administrativas do *Guia do usuário do Data Workbench*. Nesse caso, os nomes das subpastas também aparecerão no menu, como em Adicionar visualização > Gráfico > Estendido > &lt;*nome da subpasta*> > &lt;*nome da dimensão*>.

Para ver todas as dimensões que foram definidas para o perfil do conjunto de dados e o tamanho do buffer de cada uma, abra o [!DNL Detailed Status] interface no Data Workbench e clique em **[!UICONTROL Performance]**, em seguida **[!UICONTROL Dimensions]** para expandir os nós. O tamanho do buffer, que controla os tempos de consulta, é expresso em MB. Para obter mais informações sobre o [!DNL Detailed Status] consulte o guia Administração e instalação do servidor.
