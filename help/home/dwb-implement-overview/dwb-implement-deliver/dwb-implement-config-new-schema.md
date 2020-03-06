---
description: Este documento explica como alterar todas as configurações padrão do Análise de big data depois que o novo esquema estiver em vigor.
title: Alterações de configuração para novo esquema
uuid: 7d59fc28-ce56-49e2-b068-d5e286dcc057
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Alterações de configuração para novo esquema{#configuration-changes-for-new-schema}

Este documento explica como alterar todas as configurações padrão do Análise de big data depois que o novo esquema estiver em vigor.

## Noções Gerais do Esquema de Conjunto de Dados {#section-2ffac5170c894781bc943565af7ad479}

A base do esquema do conjunto de dados consiste em um conjunto-chave de relacionamentos que formam a espinha dorsal do esquema de análise da Web da Análise de big data. No exemplo a seguir, o esquema analítico da Web típico fornece uma ideia das relações entre um visitante, uma visita e uma exibição de página. ![](assets/dwb_impl_schema_change1.png)

* Qualquer visitante pode ter uma ou mais visitas.
* Qualquer visita é gerada por apenas um visitante.
* Qualquer visita específica pode incluir uma ou mais exibições de página.
* Qualquer exibição de página específica pertence a apenas uma visita. `<discoiqbr>`

À medida que a web e o mundo dos negócios evoluem ao longo dos anos, as necessidades de análise de dados e da web também mudaram. Sites começaram como lugares para se olhar para o conteúdo. Agora, podem ver o conteúdo. corresponder de forma interativa através de bate-papos, vídeos ou envios; comprar produtos; e muito mais. Além disso, as empresas agora querem integrar seus dados da Web com outros canais de dados em seus negócios para ter uma visão melhor de seus negócios como um todo. Por exemplo, uma empresa pode desejar integrar seus dados da Web, central de atendimento, email, social, armazenamento e cliente. Com essa integração de canais offline e online, os esquemas de conjunto de dados evoluíram ao longo dos anos, onde nenhum conjunto de dados tem dois esquemas iguais.

`<discoiqbr>`Quando você integra os dados online e offline, o termo &quot;visitante&quot; nem sempre parece apropriado. Como resultado, o termo &quot;cliente&quot; às vezes é usado em vez do visitante. ![](assets/dwb_impl_schema_change2.png) ![](assets/dwb_impl_schema_change3.png)

O nível de &quot;Envolvimento&quot; é usado para ativar uma única exibição de tempo, quando você tem dados de várias fontes de dados. Por exemplo, suponha que você tenha apenas uma única fonte de dados: dados de comércio eletrônico coletados por atividade do visitante em seu site. Nesse caso, o nível de Visita indica visitas ao site desses visitantes. Observe que as dimensões de tempo - &#39;Dia&#39;, &#39;Semana&#39;, &#39;Mês&#39; etc. - são normalmente capturados no nível de &quot;Visita&quot;.

Da mesma forma, o nível &quot;Evento&quot; traz todos os eventos (exibição de página, chamada feita para a central de atendimento etc.) que ocorreram durante um envolvimento. Ele combina todos os eventos online e offline para um cliente durante um contrato.

## Nova estrutura contável no DWB {#section-b77638ec04e4441cb51c56fd3d4abeb6}

A nova estrutura de esquema substitui Visitante por Cliente, Visita por Envolvimento e Ocorrência por Evento. ![](assets/dwb_impl_schema_change4.png)

## Alterações de configuração de acordo com o novo esquema de conjunto de dados {#section-27135515be5c471ba2ee879d1ef4771f}

Para alterar o esquema do conjunto de dados de visitante para cliente, é necessário alterar os seguintes arquivos de configuração:

1. Todos os arquivos de configuração na pasta Conjunto de dados, onde dimensões contáveis e estendidas são definidas. ![](assets/dwb_impl_schema_change5.png)

1. Arquivos de configuração na pasta Dimensão, onde &quot;visitante&quot;, &quot;visita&quot; ou &quot;evento&quot; são usados como Nível.

   Exemplo: Arquivo Campaign.cfg. No perfil do Adobe SC, o Campaign é definido no nível de Visita. ![](assets/dwb_impl_schema_change6.png)

   O exemplo a seguir fornece uma ideia da alteração do esquema pai de Visita para Envolvimento: ![](assets/dwb_impl_API10.png)

1. Como algumas das métricas são derivadas ou criadas a partir de contáveis, os arquivos de configuração na pasta Métricas precisam ser modificados ou criados.

   Por exemplo: crie uma nova métrica [!DNL Customers.metric with formula = sum(one,customer)] ou como Page Views.metric para *defini* -la no nível da ocorrência. Modifique a métrica e altere o nível para Evento em vez de Ocorrência.

   A métrica de exibições de página do Adobe SC definida no nível de Ocorrências: ![](assets/dwb_impl_API8.png)

   `<discoiqbr>` A `<discoiqbr>`seguir estará a métrica Exibições de página de acordo com o novo esquema: ![](assets/dwb_impl_API9.png)

1. Altere o *order.txt* na pasta de métricas para que reflita as métricas novas ou modificadas relacionadas ao Cliente, Envolvimento e Evento.

   Arquivo Adobe *SC order.txt* . ![](assets/dwb_impl_API11.png)

   *Arquivo Order.txt* com novas alterações de esquema: ![](assets/dwb_impl_API12.png)

1. Todos os arquivos de configuração (.vw) na pasta Visualization devem ser alterados para se referirem a novos níveis: Cliente, Envolvimento e Evento. Por exemplo: Mapa do processo 2D, Mapa do processo 3D etc.

   O URI.vw padrão do Adobe SC para o mapa de processo 2D é definido no nível da Ocorrência e no Grupo de visitas, como mostrado abaixo: ![](assets/dwb_impl_API14.png)

   Alterações a serem feitas no URI.vw para o novo esquema: ![](assets/dwb_impl_API15.png)

