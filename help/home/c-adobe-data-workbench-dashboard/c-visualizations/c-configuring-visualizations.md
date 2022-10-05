---
description: Mostra como configurar Título, Perfil, Dimension, Métrica, Filtro, Exibir parte superior, Classificar por e Período.
title: Configurar visualizações
uuid: aca77188-8f28-4554-8913-412b252f688c
exl-id: 153adf94-5689-4917-9d71-625caef49903
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 1%

---

# Configurar visualizações{#configuring-visualizations}

{{eol}}

Mostra como configurar Título, Perfil, Dimension, Métrica, Filtro, Exibir parte superior, Classificar por e Período.

Cada visualização na tela do painel tem sua própria configuração. Quando uma visualização é adicionada pela primeira vez à tela do painel, sua janela de configuração é exibida automaticamente. Depois de configurada, a visualização pode ser modificada a qualquer momento clicando no ícone de engrenagem na parte superior direita da janela de visualização.

>[!NOTE]
>
>As opções de configuração variam um pouco, dependendo do tipo de visualização que está sendo exibida.

## Título da visualização {#section-0414844283d745ae912e85f8ea14a51d}

Este campo permite personalizar o título exibido na parte superior da visualização. Por padrão, o título é definido como **[!UICONTROL Automatic Title]**, que gerará automaticamente um título para a janela de visualização. Ao limpar o **[!UICONTROL Automatic Title]** , você pode colocar qualquer título nesse campo. (Esse campo se aplica a todas as visualizações.)

![](assets/title.png)

## Perfil {#section-16eb0def0a2d4eb289f5bb9200d14754}

Este campo permite selecionar de qual perfil você deseja visualizar dados. Clicar no menu suspenso fornecerá uma lista de perfis aos quais você tem acesso. (Esse campo não se aplica às visualizações de Rich Text.)

Perfis são conjuntos de dados definidos no Data Workbench que contêm dados sobre um determinado domínio, juntamente com as dimensões, métricas e filtros que acompanham os dados. Geralmente, um perfil é projetado para atender a uma finalidade específica (como marketing ou tráfego de site).

>[!NOTE]
>
>Você pode ver apenas os perfis para os quais recebeu acesso. Para obter mais informações, consulte Controles de acesso .

![](assets/profile.png)

## Dimensão {#section-4ebb8c4308a146c3a35c7ac7ab6b579f}

Permite selecionar a dimensão que deseja visualizar. A lista é preenchida na lista de dimensões disponíveis no perfil selecionado no campo Perfil . Clique na dimensão desejada e depois no botão Selecionar . (Esse campo não é aplicável para legendas de métricas e visualizações de Rich Text.)

Dimension são categorias de tipos de dados semelhantes. Por exemplo, a dimensão Dias da semana é composta pelos seguintes elementos de dados: Domingo, Segunda-feira, Terça-feira, Quarta-feira, Quinta-feira, Sexta-feira e Sábado. Dimension mostram o que está sendo medido.

![](assets/dimension.png)

## Métrica(s) {#section-7d46f2f1b9fe4e539b5eb0a0dc6e5ad3}

Permite selecionar as métricas a serem visualizadas. As métricas são objetos quantitativos e são definidas por algumas expressões quantificáveis. Por exemplo, Exibições de página por sessão são derivadas da expressão da contagem de Exibições de página divididas pela contagem de Sessões. Métricas respondem à pergunta &quot;quantos?&quot;

As visualizações de métrica única têm uma janela de seleção de métrica única:

![](assets/metrics2.png)

As visualizações de várias métricas têm uma janela de seleção de várias métricas:

![](assets/metrics.png)

A lista é preenchida na lista de métricas disponíveis no perfil selecionado no campo Perfil .

Clique nas métricas desejadas e, em seguida, clique em **[!UICONTROL Select]**. (Esse campo não se aplica às visualizações de Rich Text.)

## Filtros {#section-f8619ae2f8e54735a2c1b0fbb8bb1281}

Selecione os filtros que deseja aplicar à visualização. A janela de seleção de filtro permite selecionar vários filtros na lista de filtros. A lista é preenchida na lista de filtros disponíveis no perfil selecionado no campo Perfil . Clique no filtro desejado e, em seguida, clique em **[!UICONTROL Select]**.

>[!NOTE]
>
>Os filtros aplicados aqui são aplicados somente à visualização correspondente, não ao painel inteiro. Isso é útil para comparar os resultados de duas visualizações diferentes com filtros diferentes aplicados.

![](assets/filter.png)

## Exibir Tops {#section-7ce71cb0fa6446998b710b427e68b133}

As visualizações no painel não são projetadas para exibir a totalidade dos dados. Em vez disso, elas permitem especificar o número de registros de dimensão que você deseja exibir na visualização. Isso exibe o número superior de dimensões, dependendo do valor de classificação fornecido abaixo. (Esse campo não é aplicável para tabelas, legendas de métricas e visualizações de Rich Text.)

![](assets/display_top.png)

## Classificar por {#section-f686249e20444359bff87c00cc2ba29f}

Isso permite especificar como os dados devem ser classificados quando forem exibidos na visualização. (Esse campo não é aplicável para tabelas, legendas de métricas e visualizações de Rich Text.) Há várias opções de classificação:

* **[!UICONTROL Default]** - Retorna os dados não classificados com base na ordem de classificação armazenada no Data Workbench. Essa é a opção a ser usada para dados com base no tempo, como hora, dia, semana ou mês.
* **[!UICONTROL Dimension]** -Classifique os dados com base no valor da dimensão alfanumérica.
* **[!UICONTROL Metric]** - Classifique os dados com base no valor da métrica e é bom para visualizar rapidamente as principais dimensões.
* **[!UICONTROL Descending]** - Classifique os dados em ordem decrescente.
* **[!UICONTROL Ascending]** - Classifique os dados em ordem crescente.

![](assets/sort_by.png)

## Período {#section-6220368e9e524b46ac735add6ab9edb0}

Essa visualização permite especificar a data inicial e/ou final desejada dos dados a serem exibidos na visualização.

Selecionar **[!UICONTROL All Dates]**exibe o intervalo de datas inteiro disponível no perfil.

Selecionar **[!UICONTROL Range]** exibe apenas os dados que estão dentro de um intervalo especificado. Para inserir o intervalo de datas, você pode digitar a data de início e/ou de término ou usar uma entrada de calendário selecionando o ícone de calendário.

(Esse campo não se aplica às visualizações de Rich Text.)

>[!NOTE]
>
>Os intervalos de datas aplicados aqui são aplicados somente à visualização correspondente, não ao painel inteiro. Isso é útil para comparar os resultados de duas visualizações diferentes com intervalos de datas diferentes aplicados.

![](assets/time_period.png)
