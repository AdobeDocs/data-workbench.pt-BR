---
description: Informações conceituais sobre subconjuntos.
title: Entender subconjuntos
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Entender subconjuntos{#understanding-subsets}

{{eol}}

Informações conceituais sobre subconjuntos.

Ao usar um subconjunto, lembre-se dos seguintes itens:

* Todos os seus benchmarks agora estão relacionados ao seu subconjunto, não ao conjunto de dados inteiro, o que é muito mais útil ao analisar um subconjunto específico. Consulte [Noções básicas sobre referências](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* O uso de um subconjunto afeta todos os espaços de trabalho, pois o subconjunto é aplicado globalmente ao Data Workbench.
* Subconjuntos afetam apenas métricas e dimensões desnormalizadas, não dimensões normais.
* Ao usar [!DNL Report], os subconjuntos não afetam os dados nos relatórios publicados para que outras pessoas visualizem.
* Depois de aplicado, seu subconjunto entrará em vigor para todo o trabalho subsequente no perfil, incluindo a próxima vez que você abrir essa instância do Data Workbench, até removê-la.
* O único local que indica que um subconjunto foi aplicado é o menu de contexto acessado ao clicar com o botão direito do mouse em um espaço de trabalho.

   ![](assets/mnu_Subset.png)

* Você deve estar trabalhando online para alterar ou remover um subconjunto. Se estiver trabalhando offline e tiver aplicado um subconjunto, não será possível visualizar os resultados de todo o conjunto de dados. Consulte [Trabalhar offline e online](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >O tamanho do subconjunto é limitado à quantidade de dados no filtro que reside em um único servidor do Data Workbench. Portanto, se o conjunto de dados abranger um cluster de servidores Data Workbench, os dados do subconjunto serão provenientes de apenas um servidor do Data Workbench no cluster.

Um usuário em um grande varejista deseja criar um subconjunto (cache local) de uma semana de trabalho específica de dados e, em seguida, executar consultas somente nessa semana de dados. Para fazer isso, o usuário cria um subconjunto para os dias de interesse.

O exemplo a seguir mostra um gráfico de barras de Visitantes ao longo do tempo e uma legenda de métrica de Tráfego. A primeira figura não contém seleções: todos os dados no conjunto de dados são representados. A segunda figura mostra os dados de um subconjunto de Dias = {..} por Visitantes, em que Dias é baseado em uma seleção de elementos de 1º de abril a 5º de abril na dimensão Dia .

![](assets/client-sub1.png)
