---
description: Após definir seu objetivo, hipótese e detalhes do experimento, bem como criar o conteúdo do teste, é necessário configurar o Sensor para implantar o experimento controlado.
solution: Analytics,Analytics
title: Configurar e implantar o experimento
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
exl-id: 957c2ea2-72a5-4bb2-af1d-65187613c26d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Configurar e implantar o experimento{#configuring-and-deploying-the-experiment}

Após definir seu objetivo, hipótese e detalhes do experimento, bem como criar o conteúdo do teste, é necessário configurar o Sensor para implantar o experimento controlado.

## Configurar o arquivo de configuração de experimento {#section-037fe7dea9c94aee9cdc354dafdb7c03}

Para configurar o experimento, você deve concluir a planilha de configuração do experimento fornecida pelo Adobe (chamada [!DNL TestExperiment.xls] por padrão). Esse arquivo configura [!DNL Sensor] para executar o experimento e é a versão do Excel do arquivo de texto que você especificou em [Modificando o parâmetro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

Esse arquivo pode conter informações sobre vários experimentos, que podem ser executados ao mesmo tempo ou em momentos diferentes e usar grupos e porcentagens diferentes, mas esses experimentos não estão correlacionados de forma alguma.

Os usuários são colocados em um grupo para cada experimento listado no arquivo que está configurado para execução no momento.

>[!NOTE]
>
>Cada experimento é independente de todos os outros experimentos. As mudanças que você faz em um experimento não afetam nenhum outro experimento e, embora os visitantes possam estar em vários experimentos, os resultados não se relacionam entre si. Se você acha que existe uma correlação entre as mudanças em vários experimentos, você deve criar um novo experimento que teste essas mudanças juntas.

**Para configurar seu experimento**

Você deve concluir este arquivo antes do início do experimento e não modificar a informação enquanto o experimento estiver em execução.

>[!NOTE]
>
>Qualquer experimento é prontamente inválido se a definição do experimento mudar após o início do experimento.

1. Se você tiver acesso de administrador à Web ou aos servidores de aplicativos, navegue até a pasta de instalação [!DNL Sensor] em qualquer máquina [!DNL Sensor] no cluster da Web para acessar o arquivo [!DNL TestExperiment.xls]. Se você não tiver acesso de administrador, entre em contato com o gerente de conta do Adobe para solicitar o arquivo [!DNL TestExperiment.xls].

1. Abra o arquivo [!DNL TestExperiment.xls] (é possível renomear esse arquivo, se desejar) e preencha os seguintes campos:

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Experimento </td> 
   <td colname="col2"> <p>Um nome descritivo para o experimento. Cada nome de experimento deve ser exclusivo e não pode conter espaços. </p> <p>Os nomes de experimento são usados ao exibir os resultados dos experimentos no <span class="keyword"> Insight </span>. Os nomes aparecem como a primeira metade dos nomes dos elementos na dimensão de experimento controlado. A segunda metade do nome do elemento é o nome do grupo do campo Group neste arquivo. Cada grupo é nomeado no seguinte formato usando o nome do experimento seguido pelo nome do grupo: </p> <p><i>Nome do grupo.ExperimentName</i> </p> <p>Por exemplo: <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Início </td> 
   <td colname="col2"> <p>A data e hora em que você deseja que o experimento comece. Se você não inserir valores, o experimento começará imediatamente após a implantação do arquivo. </p> <p>Formato: DD/MM/AAAA H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">Se você deixar os horários de início e parada vazios, o experimento é executado indefinidamente. </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">Você pode predefinir horários de início e parada com bastante antecedência; portanto, você pode configurar todos os seus experimentos para o próximo ano de uma só vez, se desejar. </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">As horas de início e parada são baseadas na hora do sistema do servidor da Web. Se esse relógio mudar por qualquer motivo, seu experimento pode começar ou parar inesperadamente. </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">Se quiser adicionar um experimento como uma entrada de arquivo de configuração, mas não quiser que o experimento seja executado em breve, você pode comentar as informações do experimento usando o sinal de número "#" ou definir tempos de início e parada no passado. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>A data e hora em que você deseja que o experimento termine. Quando a data e a hora de parada ocorrer, o <span class="wintitle"> Sensor </span> deixará de enviar os valores de cookie identificados como um grupo de teste para os URIs de teste e enviará todos os cookies para os URIs do grupo de controle. </p> <p>Formato: DD/MM/AAAA H:MM </p> <p>Consulte as notas para o campo <span class="wintitle"> Iniciar </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo </td> 
   <td colname="col2"> <p>Um nome descritivo para cada grupo de visitantes no experimento. Os nomes de grupo não podem conter espaços. </p> <p>Os nomes de grupo são usados ao exibir os resultados dos experimentos no <span class="keyword"> Insight </span>. Para obter mais informações, consulte a descrição do campo Experimento . </p> <p>Um grupo de controle pode ser definido implicitamente ou explicitamente com base no valor inserido no campo Percentage . </p> <p> <p>Observação:  Para atender ao número de visitantes necessários durante o período de tempo definido para que a experiência seja estatisticamente válida, talvez seja necessário diminuir o nível de confiança ou aumentar o período de tempo. Por exemplo, se o intervalo de tempo for de cinco dias, o nível de confiança será de 98% e o número de visitantes necessários exceder o número esperado para esse período de tempo, será necessário aumentar o período ou diminuir o nível de confiança até que o número de visitantes esperado exceda o número necessário para executar um experimento estatisticamente válido. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porcentagem </td> 
   <td colname="col2"> <p>A porcentagem de visitantes do site que serão incluídos em cada grupo definido. Esses valores podem ser expressos como porcentagens ou valores decimais. Além disso, ambos os valores devem ser maiores ou menores que um. </p> <p>Por exemplo: </p> <p>33,3% e 66,7% </p> <p>.99 e .01 </p> <p>Se a soma de todos os grupos for menor que 100, o excesso indefinido assumirá um grupo de controle como padrão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL original </td> 
   <td colname="col2"> <p>O URI do conteúdo a ser remapeado, seguido por $. Esse valor diferencia maiúsculas e minúsculas. </p> <p>Formato: index.asp$ </p> <p>Os URIs originais podem ser especificados usando um cifrão ($) no final do URI para indicar que é necessária uma correspondência exata do nome do arquivo. Por exemplo, a expressão <span class="filepath"> /product/product_view.asp$ </span> corresponde somente a essa página exata, enquanto <span class="filepath"> /product </span> corresponde a qualquer página no diretório <span class="filepath"> /product </span> e pode ser usada para remapear toda a subárvore. As entradas de URL originais que não especificam o caractere $ no final do nome do arquivo são ignoradas pelo experimento, a menos que o parâmetro ExpPartialMatch tenha sido definido como "on". Para obter mais informações sobre esse parâmetro, consulte <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> Modificando o Parâmetro ExpPartialMatch (Opcional) </a>. </p> <p>A funcionalidade de experimento controlado ignora qualquer sequência de consulta anexada ao fluxo de URI. Por exemplo, a página </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 não  </span> é um URI válido, mas a página  <span class="filepath"> /product/product_view.asp  </span> é um URI válido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL remapeado </td> 
   <td colname="col2"> <p>O URI do conteúdo alternativo. </p> <p>Formato: index2.asp </p> <p>Consulte as notas do campo URL original . </p> </td> 
  </tr> 
 </tbody> 
</table>

Este é um exemplo de uma planilha [!DNL TextExperiment.xls] concluída:

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>Não modifique as posições da coluna na planilha.

Este exemplo indica que o experimento &quot;New_Homepage&quot; começa em 1º de junho de 2006, termina em 30 de junho de 2006 e contém um grupo de controle com 50% dos visitantes e um grupo de teste com 50% dos visitantes, que visualizam conteúdo diferente para um URI.

>[!NOTE]
>
>Embora o arquivo de amostra acima tenha um grupo de controle explícito definido, não é necessário definir explicitamente um grupo de controle — o experimento cria automaticamente o grupo de controle. Se a soma das porcentagens para todos os grupos em um experimento for menor que 100%, um grupo de controle implícito será atribuído a usuários que não se enquadram em um dos grupos explícitos.

1. Para inserir comentários para fornecer informações adicionais sobre experimentos específicos, comece a célula com um sinal de número (#) e siga os comentários. Comentários podem ser inseridos em qualquer lugar do arquivo.
1. Depois de concluir as variáveis na planilha de configuração do experimento, salve as alterações e salve o arquivo no formato de texto delimitado por tabulação ( [!DNL *.txt]) usando o nome especificado no parâmetro ExpFile no arquivo de configuração [!DNL Sensor]. Consulte [Modificando o parâmetro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   Este é um exemplo de um arquivo de texto de configuração experimental:

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >Devido às guias necessárias neste arquivo, não edite o arquivo de texto de configuração de experimento manualmente. Se precisar fazer alterações no arquivo, faça as alterações no arquivo de configuração experimental do Excel e salve novamente o arquivo como um arquivo de texto delimitado por tabulação.

Se você tiver definido os Tempos de início e parada, não há razão para excluir um experimento do arquivo de configuração de experimento. Manter todos os experimentos listados no arquivo de configuração experimental é, na verdade, uma boa maneira de manter um registro de como você definiu cada um de seus experimentos.

## Implantação do arquivo de configuração e conteúdo de teste {#section-34ff29649f584b93bc6129b75084b37c}

Você deve implantar o arquivo de configuração de experiência em cada máquina do cluster da Web que esteja executando um [!DNL Sensor] e servindo as páginas envolvidas no experimento. Você pode fazer isso usando um procedimento manual ou o sistema de gerenciamento de conteúdo existente.

**Para implantar o conteúdo de teste**

* Em cada aplicativo ou servidor da Web que esteja executando um [!DNL Sensor] que esteja servindo páginas envolvidas no experimento, use seu processo de publicação existente para implantar o conteúdo de teste no local apropriado.

   Por exemplo, se você quiser publicar a página de grupo de teste [!DNL index2.asp] na pasta de teste do seu site ( [!DNL mysite.com]), publique o arquivo em [!DNL www.mysite.com/test].

   >[!NOTE]
   >
   >Não vincule a nenhum de seus arquivos de teste diretamente de uma página do seu site. Isso invalida os resultados do teste e as pontuações do índice.

**Para implantar seu experimento**

* Em cada aplicativo ou servidor da Web que esteja executando um [!DNL Sensor] que esteja servindo páginas envolvidas no experimento, coloque o arquivo de texto de configuração do experimento no diretório especificado no parâmetro ExpFile no arquivo de configuração [!DNL Sensor]. Consulte [Modificando o parâmetro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

[!DNL Sensor] seleciona aleatoriamente os visitantes do site para cada grupo com base nas porcentagens definidas no arquivo e retorna o conteúdo do grupo de controle ou teste para eles, conforme apropriado.
