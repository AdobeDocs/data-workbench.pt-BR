---
description: Os mapas de processo permitem analisar o fluxo de atividade entre elementos de uma dimensão.
solution: Analytics
title: Mapa de processos
topic: Data workbench
uuid: f1db41a9-400e-467a-ba59-39831fb166af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mapa de processos{#process-map}

Os mapas de processo permitem analisar o fluxo de atividade entre elementos de uma dimensão.

Você cria mapas de processo arrastando e soltando os elementos de uma dimensão em um mapa em branco bidimensional (2D) ou tridimensional (3D). Os elementos se tornam nós no mapa. Nós são círculos em mapas de processo 2D e barras em mapas de processo 3D.

![](assets/vis_2DProcessMap.png)

![](assets/vis_3DProcessMap.png)

>[!NOTE]
>
>Um mapa de processos obtém seu nome de seu uso na análise do fluxo de atividade entre as etapas em um processo. Nesse tipo de análise, cada elemento no mapa representa uma etapa no processo.

Diferentemente dos navegadores de caminho, os mapas de processo podem mostrar quantos elementos ou quantos forem necessários para sua análise. Você escolhe os elementos de interesse e arrasta e solta-os no mapa. Diferentemente dos navegadores de caminho, os mapas de processo representam o fluxo de atividade em ambas as direções entre um elemento e um ou mais outros elementos.

>[!NOTE]
>
>Para que esses mapas funcionem mais eficientemente, você deve abrir uma legenda colorida na área de trabalho. Para obter informações sobre como usar legendas coloridas com mapas de processo, consulte [Ativando links](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-act-color-lnks.md#concept-2c9b9f67f2bd4cd7a5431fa21c094edc)de cores. Para obter mais informações sobre legendas de cores, consulte Legendas [de](../../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)cores.

Cada mapa de processos tem uma dimensão básica associada, dimensão de grupo, dimensão de nível e métrica, que fornece chaves para interpretar os dados mostrados no mapa de processos.

As configurações padrão para as dimensões e métricas de um mapa de processo dependem do aplicativo Análise de big data que você está usando. Para obter informações sobre as dimensões e métricas disponíveis para os mapas de processo, consulte o guia de aplicativo para o aplicativo Análise de big data.

* **Dimensão básica:** Ao arrastar e soltar um elemento em um mapa de processo, você está arrastando e soltando um elemento da dimensão base.
* **Dimensão de nível:** Cada dimensão em seu conjunto de dados tem uma dimensão de nível associada (também chamada de pai). A dimensão de nível do mapa de processos deve ser a mesma dimensão de nível (ou pai) para a dimensão básica do mapa de processos. Por exemplo, se você arrastar uma página (um elemento da dimensão Página) para o mapa, a dimensão de nível correspondente seria Exibição de página.
* **Dimensão do grupo:** A dimensão de grupo determina como os elementos da dimensão de nível são agrupados para formar as conexões entre nós. Para mapas de processo, a dimensão de grupo é importante por três motivos principais:

   * Uma conexão entre dois nós não pode abranger mais de um elemento de uma dimensão de grupo. Para entender isso, considere um exemplo usando dados da Web. Suponha que as dimensões base, de nível e de grupo do mapa de processo sejam Página, Exibição de página e Sessão, respectivamente. Uma conexão da página A para a página B informa que, durante qualquer sessão única, uma exibição da página A ocorreu antes de uma exibição da página B sem nenhuma exibição de página de separação de outras páginas (nós) no mapa. Observe que as exibições de página de outras páginas do site podem ter ocorrido entre exibições de página para as páginas A e B durante a mesma sessão, mas essas páginas não são mostradas neste mapa.
   * Uma conexão entre dois nós pode representar vários elementos da dimensão de grupo. Por exemplo, pode haver várias sessões nas quais uma exibição de página da página A ocorreu antes de uma exibição de página da página B. Portanto, a conexão entre a página A e a página B representa todas as sessões individuais nas quais uma exibição de página da página A ocorreu antes de uma exibição de página da página B sem nenhuma exibição de página de separação de outras páginas (nós) no mapa.
   * Quando você faz uma seleção com base em um nó dentro de um mapa de processo, está selecionando todos os elementos da dimensão de grupo que envolveram esse nó. Consulte [Fazer seleções em visualizações](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746). Para obter informações sobre seleções, consulte [Fazer seleções em visualizações](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

* **Métrica:** O tamanho do nó para um determinado elemento é proporcional ao valor da métrica para esse elemento. Nós maiores indicam valores de métrica maiores que nós menores.

Por exemplo, se você estiver usando o aplicativo [!DNL Site] ou HBX, poderá arrastar, por padrão, elementos da dimensão Página para o mapa de processo. O tamanho de cada nó está relacionado à quantidade de sessões (definida pela métrica Sessões) em que a página foi visualizada.

>[!NOTE]
>
>É possível alterar as dimensões ou métricas padrão de um mapa de processos. Para obter etapas para configurar um mapa de processos, consulte [Configuração de mapas](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6)de processos.

