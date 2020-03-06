---
description: Informações conceituais sobre subconjuntos.
solution: Analytics
title: Como entender subconjuntos
topic: Data workbench
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como entender subconjuntos{#understanding-subsets}

Informações conceituais sobre subconjuntos.

Ao usar um subconjunto, lembre-se das seguintes coisas:

* Todos os seus benchmarks agora estão relacionados ao seu subconjunto, não ao conjunto de dados inteiro, o que é muito mais útil ao analisar um subconjunto específico. Consulte [Compreensão de benchmarks](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* O uso de um subconjunto afeta todos os seus espaços de trabalho, pois o subconjunto é aplicado globalmente à Análise de big data.
* Os subconjuntos afetam apenas métricas e dimensões desnormalizadas, não dimensões normais.
* Ao usar [!DNL Report], os subconjuntos não afetam os dados nos relatórios publicados para que outras pessoas possam visualizá-los.
* Depois de aplicado, seu subconjunto entrará em vigor para todos os trabalhos subsequentes no perfil, incluindo a próxima vez que você abrir essa instância da Análise de big data, até removê-lo.
* O único local que indica que um subconjunto foi aplicado é o menu de contexto que você atinge ao clicar com o botão direito do mouse em um espaço de trabalho.

   ![](assets/mnu_Subset.png)

* Você deve estar trabalhando online para alterar ou remover um subconjunto. Se você estiver trabalhando offline e tiver aplicado um subconjunto, não será possível exibir os resultados de todo o conjunto de dados. Consulte [Trabalhando off-line e on-line](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >O tamanho do seu subconjunto é limitado à quantidade de dados no filtro que reside em um único servidor da Análise de big data. Portanto, se o conjunto de dados abranger um cluster de servidores da Análise de big data, os dados para o seu subconjunto serão provenientes de apenas um servidor da Análise de big data no cluster.

Um usuário em um grande varejista deseja criar um subconjunto (cache local) de uma semana útil específica de dados e, em seguida, executar consultas somente nessa semana de dados. Para fazer isso, o usuário cria um subconjunto para os dias de interesse.

O exemplo a seguir mostra um gráfico de barras de Visitantes ao longo do tempo e uma legenda de métrica de Tráfego. A primeira figura não contém seleções: todos os dados no conjunto de dados são representados. A segunda figura mostra os dados de um subconjunto de Dias = {...} por Visitantes, em que Dias é baseado em uma seleção dos elementos de 1º de abril a 5º de abril na dimensão Dia.

![](assets/client-sub1.png)

