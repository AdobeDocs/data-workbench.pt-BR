---
description: As visualizações da tabela de latência são tabelas que incluem uma dimensão de latência, que é um tipo de dimensão derivada que mede o tempo decorrido desde que um evento específico ocorreu.
title: Tabelas de latência
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
exl-id: 22f6d52f-e1c2-430a-9e69-3440be0ecdea
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 1%

---

# Tabelas de latência{#latency-tables}

{{eol}}

As visualizações da tabela de latência são tabelas que incluem uma dimensão de latência, que é um tipo de dimensão derivada que mede o tempo decorrido desde que um evento específico ocorreu.

Você define o evento fazendo seleções em uma ou mais visualizações e definindo essas seleções como o evento usando a opção de menu Definir contexto do evento . As tabelas de latência são especialmente úteis para rastrear atividades relacionadas a uma campanha ou a um pedido de cliente específico no qual você está procurando uma correlação de tempo.

Em [!DNL Site], as tabelas de latência fornecem informações sobre as sessões do visitante que ocorreram até sete dias antes ou depois do evento, mas você pode configurar as tabelas de latência para fornecer informações sobre diferentes dimensões contáveis e de tempo. Consulte [Configuração de tabelas de latência](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

Os elementos da dimensão pai, como uma sessão, que fazem parte do evento específico selecionado, têm uma latência de zero. Todos os outros elementos recebem latências que refletem a distância (na dimensão de tempo apropriada) do evento.

O exemplo a seguir ilustra como você pode usar a tabela de latência.

**Identificar eventos de valor em relação a uma campanha**

Digamos que você queira rastrear a atividade dos clientes durante os sete dias antes e depois de responderem a uma campanha publicitária específica. Para visualizar a latência de uma campanha publicitária específica, você define a campanha de interesse como o evento para a tabela de latência.

A latência no espaço de trabalho abaixo é baseada na seleção do Campaign 11566 (as sessões em resposta a esta campanha).

![](assets/vis_Latency.png)

Uma latência de &quot;+0 dias&quot; identifica as sessões em resposta ao Campaign 11566, bem como todas as outras sessões para os mesmos clientes que ocorreram no mesmo dia.

Uma latência de &quot;-2 dias&quot; identifica as sessões para os mesmos clientes que ocorreram dois dias antes de os clientes responderem à campanha.

Uma latência de &quot;+7 dias&quot; identifica as sessões para os mesmos clientes que ocorreram sete dias após terem respondido à campanha.

Além dos procedimentos listados nas seções a seguir, é possível executar todas as mesmas tarefas que você pode executar em uma tabela, como elementos de classificação, elementos de máscara, adicionar uma legenda de série, exportar dados etc. Para obter mais informações, consulte [Tabelas](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## Criar uma tabela de latência {#section-31a03031d9854ef7acc2462d4f37678d}

Para criar uma tabela de latência, comece fazendo uma seleção e depois definindo essa seleção como o evento para o qual você deseja rastrear a latência.

1. Clique com o botão direito do mouse em um espaço de trabalho e abra as visualizações desejadas, que devem ser baseadas na dimensão contável usada para configurar a tabela de latência.

   Por exemplo, em [!DNL Site] a(s) visualização(ões) precisaria(m) ser baseada(s) em sessões.

1. Abra uma tabela de latência em branco.
1. Faça uma seleção no seu espaço de trabalho.
1. Clique com o botão direito do mouse na tabela de latência e clique em **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>Os eventos selecionados não persistem, a menos que você salve as seleções como uma dimensão de latência. Para ver as etapas, consulte [Reutilização de um Dimension de latência](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46).

## Reutilizar uma tabela de latência {#section-05f741169d204213b6537dce553e4f73}

Se quiser usar a mesma tabela de latência novamente, salve a tabela de latência localmente ou se tiver as permissões apropriadas, poderá salvá-la no servidor para que todos os usuários de um perfil específico acessem.

**Para salvar a tabela de latência para uso em outros espaços de trabalho**

1. Clique com o botão direito do mouse na borda superior da visualização e clique em **[!UICONTROL Save]**. O [!DNL Save] será exibida. O local de salvamento padrão é a pasta Usuário\*nome do perfil*\Trabalho.
1. No [!DNL File name] , digite um nome descritivo para a visualização e clique em **[!UICONTROL Save]**.

**Para recuperar a tabela de latência salva**

1. Clique com o botão direito do mouse no espaço de trabalho e clique em **[!UICONTROL Open]** > **[!UICONTROL File]**. O [!DNL Open Visualization] será exibida.
1. Navegue até a tabela de latência que você salvou.
1. Selecione o arquivo de visualização da tabela de latência ( [!DNL *.vw]) e clique em **[!UICONTROL Open]**.

## Reutilizar uma dimensão de latência {#section-29c6483bf9ba476fb1c24ad1df253f46}

Se quiser usar a mesma dimensão de latência novamente, poderá salvar a dimensão de latência localmente ou se tiver as permissões apropriadas, poderá salvá-la no servidor para que todos os usuários de um perfil específico possam acessá-la.

Todas as dimensões de latência criadas são salvas no diretório Dimension do perfil e estão disponíveis no [!DNL Change Dimension] lista suspensa no Data Workbench.

**Para salvar a dimensão de latência para uso em outros espaços de trabalho**

1. Clique com o botão direito do mouse no [!DNL Latency] rótulo da coluna ou um de seus elementos e clique em **[!UICONTROL Save Dimension]**. O [!DNL Save Dimension As] será exibida.
1. Selecione ou crie o subdiretório apropriado no diretório Dimension.
1. No [!DNL File name] , digite um nome descritivo para a dimensão (por exemplo, [!DNL Latency for Campaign 11565.dim]) e clique em **[!UICONTROL Save]**.

**Para recuperar a dimensão de latência salva**

1. Clique com o botão direito do mouse no espaço de trabalho e clique em **[!UICONTROL Open]** > **[!UICONTROL File]**. O [!DNL Open Visualization] será exibida.
1. Navegue até a visualização de latência salva na pasta Usuário\*nome do perfil*\Dimension.
1. Selecione o arquivo de dimensão de latência ( [!DNL *.dim]) e clique em **[!UICONTROL Open]**.

## Exportar para o Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

Para obter informações sobre como exportar janelas, consulte [Exportar dados da janela](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).

## Exportar para um arquivo TSV {#section-fd921f351c994ed0a94f63d3bd5b5a87}

Para obter informações sobre como exportar janelas, consulte [Exportar dados da janela](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
