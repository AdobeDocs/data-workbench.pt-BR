---
description: Use o perfil histórico do Data Workbench para ver como a configuração, o hardware e outras alterações afetam o desempenho, a estabilidade e a capacidade do servidor ao longo do tempo.
title: Espaço de trabalho Histórico do Data Workbench
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Espaço de trabalho Histórico do Data Workbench{#data-workbench-historic-workspace}

Use o perfil histórico do Data Workbench para ver como a configuração, o hardware e outras alterações afetam o desempenho, a estabilidade e a capacidade do servidor ao longo do tempo.

O perfil Histórico inclui um conjunto de dados [Desempenho do perfil](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) baseado em perfil e o conjunto de dados [Desempenho do servidor](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) baseado em servidor, na guia **[!UICONTROL Performance]**. Esses são os conjuntos de dados mais usados, visualizados para uma perspectiva anterior do desempenho do servidor do Data Workbench. Além disso, é possível visualizar os [Componentes](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) e [Modo de processamento](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) selecionando a guia **[!UICONTROL Up Time]**.

![](assets/Historic_Performance.png)

Além disso, é possível visualizar os [Componentes](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) e [Modo de processamento](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) selecionando a guia **[!UICONTROL Up Time]**.

Para obter informações de referência adicionais sobre as dimensões usadas no perfil Histórico do Data Workbench, consulte [Dimension no perfil Histórico do Insight.](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## Espaço de trabalho Desempenho do perfil {#section-184a86f9de054970bf68515bb9dea85d}

Esse conjunto de dados inclui as seguintes métricas relevantes para monitoramento do Data Workbench.

* MegaBytes de Entrada Rápida por Minuto — métricas que exibem entrada de dados pesados durante o processamento inicial de log.
* MegaBytes de Mesclagem Rápida por Minuto — métricas que exibem transformação.

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>Para fazer uma avaliação de desempenho real do seu perfil, verifique a taxa em vez do tempo decorrido do calendário. A taxa é medida como os valores alterados entre a pesquisa a cada dez minutos.

## Espaço de trabalho Desempenho do Servidor {#section-5dad5870384b40e094d50173fcd90a09}

Esse conjunto de dados monitora métricas do servidor além do escopo dos perfis incluídos e inclui as seguintes métricas de servidor relevantes para o monitoramento do Data Workbench.

* Estimated Sweep Minutes — Tempo estimado de resolução de consulta.
* Milissegundos de latência de pesquisa — Indicador de como o software está ocupado medindo quanto tempo leva para passar por um ciclo completo de manutenção de cada componente.

![](assets/Historic_Server_Performance.png)

## Espaço de trabalho Componentes {#section-5be7223abb384784bafe7b37c764ea66}

Esse conjunto de dados está localizado na guia Tempo ativo.

![](assets/Up_Time.png)

O conjunto de dados Componentes inclui dois aspectos para a integridade do componente:

* Métrica de comunicações — O processo do servidor do Data Workbench respondeu?
* Métrica Todos os componentes — Na parte superior da página Status detalhado, há uma lista de componentes que o host está atendendo nos processos do servidor do Data Workbench. Se algum componente estiver em um estado de erro, ele será listado na tabela Componentes em Erro .

![](assets/Up_Time_components.png)

## Espaço de trabalho Modo de processamento {#section-3e1dedb9474e4b4ba513240943e76817}

Esse espaço de trabalho está localizado na guia Tempo Ativo. Esse espaço de trabalho permite observar quanto tempo é gasto em modos de entrada rápida, mesclagem rápida e em tempo real.

![](assets/Up_Time_Processing_mode.png)

Esse conjunto de dados fornece características importantes de carga do servidor, como a identificação da carga de dados para

* Dia da semana (por exemplo, uma Taxa de Entrada Rápida na terça e quarta-feira),
* Hora do dia (que porcentagem do dia está no modo Entrada rápida?)
