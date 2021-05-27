---
description: Esse arquivo funciona não apenas como uma planilha, mas também como um registro de suas decisões sobre o experimento.
solution: Analytics,Analytics
title: Planilha de design de experimento
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
exl-id: 554790ab-1182-4481-87b0-e768ea769ddf
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# Planilha de design de experimento{#experiment-design-spreadsheet}

Esse arquivo funciona não apenas como uma planilha, mas também como um registro de suas decisões sobre o experimento.

Se você precisar de ajuda para projetar seu experimento, poderá usar a planilha de design de experimento (chamada VS Controlled Experiment Design.xls por padrão) fornecida pelo Adobe.

A planilha de design experimental pode fornecer inferências estatísticas úteis somente quando a métrica em questão for definida como uma porcentagem de visitantes que atendem a alguns critérios. Ou seja, é útil somente ao testar uma hipótese de métrica baseada em visitante.

**Para projetar seu experimento usando o arquivo de design de experimento**

1. Se você tiver acesso de administrador aos servidores da Web ou de aplicativos, navegue até a pasta de instalação [!DNL Sensor] em qualquer máquina [!DNL Sensor] no cluster da Web. Se você não tiver acesso de administrador, entre em contato com o gerente de conta do Adobe para solicitar o arquivo.
1. Abra o arquivo VS Controlled Experiment Design.xls. (Se desejar, é possível renomear esse arquivo.)

   A planilha na página a seguir é um exemplo de como você preencheria a planilha ao se preparar para testar a hipótese de exemplo usada em todo este guia.

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. Insira o texto ou os valores para todos os campos em azul neste arquivo, que estão descritos na tabela a seguir. Os campos calculados são definidos na segunda tabela.

<table id="table_C343F7A4BF3D4E0E9A5E9739EC7C2E10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Neste campo... </th> 
   <th colname="col2" class="entry"> Especificar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Título do experimento </td> 
   <td colname="col2"> Um nome descritivo para o seu experimento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descrição do experimento </td> 
   <td colname="col2"> Uma descrição textual do experimento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica sendo estudada </td> 
   <td colname="col2"> <p>O nome da métrica em que o experimento se baseia. </p> <p>Exemplo: Conversão do visitante </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Definição de métrica </td> 
   <td colname="col2"> <p>A definição da métrica em que o experimento se baseia. </p> <p>Formato: Visitantes[X]/Visitantes </p> <p>Exemplo: <span class="filepath"> Visitantes[URI='conversionpage.asp']/Visitantes</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de início prevista </td> 
   <td colname="col2"> A data e a hora em que você deseja que o experimento comece. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de Término Pretendida </td> 
   <td colname="col2"> A data e a hora em que você deseja que o experimento termine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seleções aplicáveis </td> 
   <td colname="col2"> (Opcional) O nome da dimensão e o conjunto de elementos ou o intervalo pelo qual você deseja segmentar ainda mais o conjunto de dados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URIs de experiência </td> 
   <td colname="col2"> Os URIs envolvidos na hipótese. Você define os URIs atuais para o grupo de controle e os URIs alternativos que você criou ou criará para os grupos de teste. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métricas esperadas para seleções de aplicativo </td> 
   <td colname="col2"> Cabeçalho para os valores de métrica que você espera de seu site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Média de visitantes por dia </td> 
   <td colname="col2"> O número médio de visitantes ao seu site por dia. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversão do visitante </td> 
   <td colname="col2"> A taxa média de conversão do visitante para seu site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> O experimento determinará se o nome da métrica dos grupos de teste é ... </td> 
   <td colname="col2"> Cabeçalho para como os valores da métrica devem ser comparados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maior que o valor do grupo de controle? </td> 
   <td colname="col2"> Defina esse campo como True se desejar concluir que a métrica do grupo de teste aumentou durante o experimento. Defina esse campo como Falso para reduzir o número de visitantes necessários para tirar conclusões. O Adobe recomenda que você o defina como Verdadeiro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Menor que o valor do grupo de controle? </td> 
   <td colname="col2"> Defina esse campo como True se desejar concluir que a métrica do grupo de teste diminuiu durante o experimento. O Adobe recomenda que você o defina como Verdadeiro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pelo menos (Nível de detecção) </td> 
   <td colname="col2"> A porcentagem pela qual você deseja que a métrica do grupo de teste seja maior ou menor do que a do grupo de controle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Com um nível de confiança de pelo menos </td> 
   <td colname="col2"> O nível de confiança desejado para os valores do grupo de teste. O nível de confiança determina o número de falsos positivos para medir a probabilidade de a expectativa declarada ser verdadeira. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> e um Nível de potência de </td> 
   <td colname="col2"> O nível de energia desejado para os valores do grupo de teste. O nível de energia determina o número de falsos negativos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % de visitantes </td> 
   <td colname="col2"> Cabeçalho para a porcentagem dos valores de visitantes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo de teste </td> 
   <td colname="col2"> Porcentagem de visitantes que você deseja incluir no grupo de teste. Você pode reproduzir com esse número até que o valor no campo Total (Geralmente 100%) da seção Visitantes seja igual ou maior que o valor no campo Mínimo de visitantes necessários (Grupos de teste e controle) , ambos descritos na tabela a seguir. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo de controle </td> 
   <td colname="col2"> Porcentagem de visitantes que você deseja incluir no grupo de controle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Outras notas de design </td> 
   <td colname="col2"> Quaisquer observações que você deseja salvar para referência futura. </td> 
  </tr> 
 </tbody> 
</table>

Os campos restantes são calculados com base nos valores inseridos e descritos na tabela a seguir.

| Campo | Descrição |
|---|---|
| Métricas esperadas para seleções de aplicativo | Cabeçalho para os valores de métrica que você espera de seu site. |
| Visitantes esperados por período | Normalmente, esse campo é calculado automaticamente pela planilha. Ele depende da suposição de que, na maioria dos dias, o site recebe muito mais visitantes novos do que visitantes recorrentes. Se esse não for o caso, o cálculo dessa célula deve ser substituído pelo número real de visitantes esperados durante o experimento. |
| Pontuação Z calculada para erro de tipo I | A pontuação Z para um resultado falso positivo. Trata - se de um cálculo estatístico intermédio. |
| Pontuação Z calculada para erro de tipo II | A pontuação Z para um resultado falso negativo. Trata - se de um cálculo estatístico intermédio. |
| Visitantes mínimos necessários (Grupos de teste e controle) | O número mínimo de visitantes necessário em seu experimento para atender ao nível de confiança, nível de energia e pontuação Z especificados, expresso como uma porcentagem do valor no campo Visitantes esperados por período . |
| Visitantes mínimos necessários (Grupos de teste e controle) | Número mínimo de visitantes necessários em seu experimento para atender ao seu nível de confiança, nível de energia e pontuação Z especificados. Esse valor deve ser menor ou igual ao valor no campo Total (geralmente 100%) da seção Visitors . |
| Tempo Mínimo de Experiência (Dias) | Número mínimo de dias que você precisa executar seu experimento para atender ao nível de confiança, nível de energia e pontuação Z especificados. Esse número calculado está sujeito aos mesmos problemas discutidos no campo Visitantes esperados por período . No caso de um site com muitos visitantes recorrentes, o campo Tempo mínimo de experiência (Dias) é o número esperado de dias para ver um número de visitantes únicos igual ao valor no campo Visitantes mínimos obrigatórios . |
| Visitantes | Cabeçalho para os valores de visitantes. |
| Grupo de teste | Número de visitantes necessários no grupo de teste. |
| Grupo de controle | Número de visitantes necessários no grupo de controle. |
| Total (Normalmente 100%) | Número total de visitantes necessários para a experiência. Esse valor deve ser igual ou superior ao valor no campo Mínimo de visitantes necessários (Grupos de teste e controle). |
| Precisão do grupo de teste (no nível de confiança do Target) | Porcentagem indicando que há uma chance igual ao nível de confiança especificado de que o valor medido da métrica calculada para o grupo de teste estará dentro dessa porcentagem de seu valor real. |
| Precisão do grupo de controle (no nível de confiança do Target) | Porcentagem indicando que há uma chance igual ao nível de confiança especificado de que o valor medido da métrica calculada para o grupo de controle estará dentro dessa porcentagem de seu valor real. |
| Pontuação Z (na Precisão do Target) | Número de desvios-padrão que um determinado valor representa a média de teste. |
| Nível de confiança real (no intervalo de destino) | O nível de confiança alcançado para o experimento. O nível de confiança mede a probabilidade da expectativa declarada ser verdadeira. |
| Intervalo Real (no Nível de Confiança do Target) | O intervalo de confiança obtido para o experimento, que fornece um intervalo estimado de valores que provavelmente incluirá um parâmetro de população desconhecido. Esse intervalo é calculado a partir de um determinado conjunto de dados de amostra. |

Você precisa ver o valor no campo Mínimo de visitantes necessários (Grupos de teste e controle) . . .

![](assets/Experiment_Design_Min_Visitors.png)

e compare-a com o valor no campo Total na coluna [!DNL Visitors].

![](assets/Experiment_Design_Total_Visitors.png)

Para que seu experimento seja estatisticamente válido, o valor no campo Total (normalmente 100%) deve ser igual ou maior que o valor no campo Mínimo de visitantes necessários (Grupos de teste e controle) .

Considerando as informações fornecidas, o que a planilha de exemplo mostra é que 10.475 visitantes precisam participar deste experimento para atingir a taxa de confiança de 95% inserida (que é a confiança mínima sugerida para qualquer experimento controlado, embora você possa aumentar esse número). O experimento, como projetado atualmente, inclui 30.000 visitantes, o que é bem maior do que o número mínimo de visitantes necessário.

Se você mantiver o mesmo número de dias, poderá aumentar o nível de confiança, desde que o número total de visitantes continue a atender ou exceda o mínimo necessário.

1. Salve o arquivo para seus registros e use as informações do arquivo para configurar o experimento usando a planilha de configuração de experimento. Para obter mais informações sobre essa planilha, consulte [Configuração e implantação do experimento](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).
