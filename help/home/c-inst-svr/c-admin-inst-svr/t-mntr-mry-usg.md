---
description: Informações sobre a avaliação e o monitoramento da Carga do Espaço de Endereços.
solution: Analytics
title: Monitorar uso de memória
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---


# Monitorar uso de memória{#monitoring-memory-usage}

Informações sobre a avaliação e o monitoramento da Carga do Espaço de Endereços.

**Monitorando a carga do espaço de endereço**

**Frequência recomendada:** Diariamente

O carregamento do Espaço de endereço é uma medida da fração do Espaço de endereço máximo que um configurado corretamente [!DNL Insight Server] usa. Mesmo que os parâmetros de configuração sejam alterados para reduzir o uso da memória, geralmente não diminui até que o [!DNL Insight Server] serviço seja reiniciado.

Uma margem de segurança é incorporada no máximo de carga do Espaço de Endereços para levar em conta aumentos inesperados na utilização do Espaço de Endereços. Nunca se deve reduzir deliberadamente a esta margem de segurança. Ele existe para situações de emergência e não para suporte de funcionalidade adicionada ao seu aplicativo Adobe.

>[!NOTE]
>
>Para disponibilizar mais Espaço de endereço e evitar erros de exaustão de memória, verifique se o seu sistema operacional tem o Switch /3 GB ativado e se o Heap de baixa fragmentação está funcionando.

Os erros registrados no registro de dados do [!DNL Insight Server] evento podem fornecer uma pista de que os problemas estão se desenvolvendo com o carregamento do Espaço de endereço:

* Os erros &quot;Bloco de X bytes solicitado é muito grande&quot; indicam que algo pode ter um impacto excessivo na carga, no desempenho e na largura de banda da rede do Espaço de endereço. Esses blocos grandes podem contribuir muito para o uso do Espaço de endereço, tanto usando muita memória quanto exigindo grandes blocos contíguos de Espaço de endereço.

   Para resolver esse problema, você pode reduzir a cardinalidade das suas maiores dimensões, o que aumenta a carga do Espaço de endereços. Se não conseguir reduzir a cardinalidade das dimensões, tente manter o Espaço de endereço suficientemente pequeno para lidar com um aumento inesperado.
* Os erros &quot;O orçamento da memória excedeu&quot; indicam que talvez seja necessário aumentar o Limite de Memória do Query. A memória usada por query é proporcional à cardinalidade da dimensão e, em alguns casos, às durações dos nomes dos elementos. Se você aumentar o Limite de Memória do Query, aumentará a carga total do Espaço de Endereço e diminuirá as dimensões grandes.

>[!NOTE]
>
>Por padrão, o uso de páginas grandes é permitido e a pesquisa mapeada por memória é desativada. No DWB 6.7 e posterior, isso pode ser alterado na configuração do conjunto de dados. Qualquer alteração requer uma reinicialização do Servidor.

**Para avaliar a carga do Espaço de endereço**

Para avaliar com precisão a carga do Espaço de endereço do seu sistema, o Adobe recomenda o reprocessamento do conjunto de dados, a execução de alguns query normais sem reinicialização subsequente [!DNL Insight Server]e a visualização da carga medida do Espaço de endereço seguindo estas etapas.

Se um item não [!DNL Insight Server] tiver sido reprocessado e consultado significativamente desde que foi reiniciado pela última vez, você não deve tirar conclusões do carregamento do Espaço de endereços.

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Detailed Status]**.
1. Na interface de Status detalhado, clique **[!UICONTROL Memory Status]** para visualização de seu conteúdo. No parâmetro Carga do Espaço de Endereços, é possível ver a carga do Espaço de Endereços expressa como uma porcentagem e uma descrição entre parênteses indicando o status.

   A tabela a seguir apresenta intervalos e status para o carregamento do Espaço de endereço. Uma ação recomendada é listada para cada intervalo.

   | Carga do Espaço de Endereço (%) | Status | Ação recomendada |
   |---|---|---|
   | 0-15 | magro e médio | Nenhum. |
   | 15-33 | luz | Nenhum. |
   | 33-66 | moderado | Nenhum. |
   | 66-100 | pesada | Para evitar falhas de exaustão de memória, não adicione funcionalidade extra significativa ou tente processar mais dados. |
   | 100-125 | confiabilidade comprometida | Ajuste a configuração do conjunto de dados para reduzir o carregamento do Espaço de endereço. |
   | 125 ou maior | falha iminente | Ajuste a configuração do conjunto de dados para reduzir o carregamento do Espaço de endereço. Talvez você não veja o status iminente de falha antes que ocorra a falha. |

   Se você vir um carregamento de Espaço de endereço acima de 100%, deverá alterar a configuração o mais rápido possível para reduzir o uso do Espaço de endereço.

