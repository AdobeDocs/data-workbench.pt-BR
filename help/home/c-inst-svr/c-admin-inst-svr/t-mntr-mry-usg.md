---
description: Informações sobre a avaliação e o monitoramento da carga do espaço de endereços.
title: Monitorar uso de memória
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
exl-id: b8c0b33b-dbec-4947-911b-11c8a83bbc9c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---

# Monitorar uso de memória{#monitoring-memory-usage}

Informações sobre a avaliação e o monitoramento da carga do espaço de endereços.

**Monitorando a carga do espaço de endereço**

**Frequência recomendada:** diariamente

A carga do Espaço de Endereço é uma medida da fração do Espaço de Endereço máximo que um [!DNL Insight Server] configurado corretamente usa. Mesmo que os parâmetros de configuração sejam alterados para reduzir o uso de memória, geralmente não diminui até que o serviço [!DNL Insight Server] seja reiniciado.

Uma margem de segurança é incorporada no máximo de carga do Espaço de Endereço para levar em conta aumentos inesperados na utilização do Espaço de Endereço. Nunca se deve reduzir deliberadamente a esta margem de segurança. Ele existe para situações de emergência e não para o suporte de funcionalidade adicionada ao seu aplicativo Adobe.

>[!NOTE]
>
>Para disponibilizar mais Espaço de endereço e evitar erros de esgotamento de memória, verifique se o seu sistema operacional tem o Switch /3GB ativado e se o Heap de baixa fragmentação está funcionando.

Erros registrados no log de dados do evento [!DNL Insight Server] podem fornecer uma pista de que os problemas estão sendo desenvolvidos com o carregamento do Espaço de endereço:

* Os erros &quot;O bloco de bytes X solicitado é muito grande&quot; indicam que algo pode estar tendo um impacto excessivo na carga do Espaço de Endereços, no desempenho e na largura de banda da rede. Esses blocos grandes podem contribuir muito para o uso do Espaço de Endereços, usando muita memória e exigindo grandes blocos contíguos de Espaço de Endereços.

   Para resolver esse problema, você pode reduzir a cardinalidade das suas maiores dimensões, o que aumenta a carga do Espaço de Endereço. Se não conseguir reduzir a cardinalidade das dimensões, você deve tentar manter o Espaço de Endereços suficientemente pequeno para poder lidar com um aumento inesperado.
* Os erros de &quot;orçamento de memória excedido&quot; indicam que talvez seja necessário aumentar o Limite de Memória de Consulta. A memória usada por queries é proporcional à cardinalidade da dimensão e, em alguns casos, aos comprimentos dos nomes dos elementos. Se você aumentar o Limite de Memória de Consulta, você aumentará a carga total do Espaço de Endereço e reduzirá as grandes dimensões.

>[!NOTE]
>
>Por padrão, o uso de páginas grandes é permitido e a pesquisa mapeada para memória é desativada. No DWB 6.7 e posterior, isso pode ser alterado na configuração do conjunto de dados. Qualquer alteração requer uma reinicialização do Servidor.

**Para avaliar a carga do espaço de endereço**

Para avaliar com precisão a carga do Espaço de Endereço do seu sistema, o Adobe recomenda o reprocessamento do conjunto de dados, realizando algumas consultas normais sem reiniciar [!DNL Insight Server] posteriormente e visualizando a carga medida do Espaço de Endereço seguindo essas etapas.

Se um [!DNL Insight Server] não tiver sido reprocessado e consultado significativamente desde a última reinicialização, você não deve tirar conclusões do carregamento do Espaço de endereço.

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Detailed Status]**.
1. Na interface de Status detalhado, clique em **[!UICONTROL Memory Status]** para exibir seu conteúdo. No parâmetro Carregamento do Espaço de Endereços, você pode ver a carga do Espaço de Endereços expressa como uma porcentagem e uma descrição parênteses indicando o status.

   A tabela a seguir apresenta intervalos e status para a carga do Espaço de Endereço. Uma ação recomendada é listada para cada intervalo.

   | Carga do Espaço de Endereços (%) | Status | Ação recomendada |
   |---|---|---|
   | 0-15 | magra e média | Nenhum. |
   | 15-33 | luz | Nenhum. |
   | 33-66 | moderar | Nenhum. |
   | 66-100 | pesada | Para evitar falhas de esgotamento de memória, não adicione funcionalidades extras significativas ou tente processar mais dados. |
   | 100-125 | fiabilidade comprometida | Ajuste a configuração do conjunto de dados para reduzir a carga do Espaço de endereço. |
   | 125 ou maior | falha iminente | Ajuste a configuração do conjunto de dados para reduzir a carga do Espaço de endereço. Você pode não ver o status de falha iminente antes de ocorrer a falha. |

   Se você vir uma carga do Espaço de Endereço acima de 100%, deverá alterar a configuração o mais rápido possível para reduzir o uso do Espaço de Endereço.
