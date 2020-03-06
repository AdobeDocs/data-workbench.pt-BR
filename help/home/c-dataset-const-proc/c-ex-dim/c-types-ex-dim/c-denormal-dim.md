---
description: Uma dimensão desnormalizada tem uma relação um para um com sua dimensão pai contável.
solution: Analytics
title: Dimensões desnormalizadas
topic: Data workbench
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões desnormalizadas{#denormal-dimensions}

Uma dimensão desnormalizada tem uma relação um para um com sua dimensão pai contável.

Você definiria uma dimensão desnormalizada sempre que a dimensão desejada contivesse um elemento exclusivo para cada elemento do pai. Por exemplo, [!DNL EMail Address] é uma dimensão desnormalizada com um pai de Visitante. Cada Visitante tem um endereço de email, e cada elemento na dimensão Endereço de email é o endereço de email de um único visitante. Mesmo que dois visitantes tenham o mesmo endereço de email, os endereços são elementos distintos da dimensão Endereço de email.

É possível usar dimensões desnormalizadas em qualquer visualização de tabela, em tabelas detalhadas ou para criar filtros. Além disso, é possível usar dimensões desnormalizadas com a funcionalidade de exportação de segmentos do servidor da análise de big data para exportar valores de campos (como [!DNL Tracking ID] ou [!DNL EMail Address]) com muitos valores. Como qualquer dado de segmento que você deseja exportar deve ser definido como uma dimensão dentro do perfil, é necessário criar uma dimensão desnormalizada que armazene as sequências de caracteres brutas dos dados do campo.

>[!NOTE]
>
>Ao usar uma dimensão desnormalizada em uma tabela ou outra visualização que espera uma dimensão normal, uma dimensão desnormalizada derivada é criada automaticamente. A dimensão denormal derivada tem uma relação um para muitos com a dimensão pai.

Para obter informações sobre a visualização de tabelas de detalhes e filtros, consulte o capítulo Visualizações de análise no Guia ** do usuário da Análise de big data. Para obter informações sobre exportação de segmentos, consulte o capítulo Configuração de recursos de interface e análise no Guia *do usuário da Análise de* big data.

>[!NOTE]
>
>Dimensões desnormalizadas podem ser muito caras em tempo de consulta e espaço em disco. Uma dimensão desnormalizada com pai [!DNL Page View]e uma sequência de caracteres de entrada média de 50 bytes pode adicionar 25 GB de dados aos buffers em um conjunto de dados comum e grande, equivalente a cerca de 13 dimensões de visualização de página simples ou numéricas, ou cerca de 125 dimensões de nível de sessão. Nunca adicione uma dimensão desnormalizada a um conjunto de dados sem uma avaliação cuidadosa do impacto no desempenho.

As dimensões denormal são definidas pelos seguintes parâmetros:

<table id="table_532AD791E39B4CF296FFA1C33FB8302E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descritivo da dimensão como aparece na análise de big data. O nome da dimensão não pode incluir um hífen (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comentários </td> 
   <td colname="col2"> Opcional. Notas sobre a dimensão estendida. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condição </td> 
   <td colname="col2"> As condições em que a relação entre o Pai e o valor do campo de entrada deve ser criada. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Oculto </td> 
   <td colname="col2"> Determina se a dimensão aparece na interface da análise de big data. Por padrão, esse parâmetro é definido como false. Se, por exemplo, a dimensão for usada apenas como base de uma métrica, você poderá definir esse parâmetro como verdadeiro para ocultar a dimensão da exibição da análise de big data. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrada </td> 
   <td colname="col2"> O valor relacionado à dimensão pai (Pai). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elementos normalizados </td> 
   <td colname="col2"> Um parâmetro de ajuste de desempenho que especifica o número de elementos de dimensão cujos nomes devem ser armazenados na memória do sistema. A configuração desse parâmetro para um valor mais alto faz com que uma dimensão desnormalizada use mais RAM, mas resulta em consultas mais rápidas. O valor padrão é 16383. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operação </td> 
   <td colname="col2"> <p>As operações disponíveis são as seguintes: </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> PRIMEIRO NÃO EM BRANCO: O primeiro valor de entrada que não está em branco é usado, independentemente de ser proveniente da primeira entrada do registro. Se <span class="wintitle"> Input</span> for um campo de vetor, a primeira linha no vetor para a entrada de log relevante será usada. </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> PRIMEIRA LINHA: O valor da primeira entrada de log relacionada ao elemento de dimensão pai é usado, mesmo se a entrada estiver em branco. Se <span class="wintitle"> Input</span> for um campo de vetor, a primeira linha no vetor para a entrada de log relevante será usada. Se esse valor estiver em branco ou não for um número, ou se a entrada de log relevante não atender à Condição da dimensão, nenhum valor será usado. </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> ÚLTIMO NÃO BRANCO: O último valor de entrada que não está em branco é usado, independentemente de ser proveniente da última entrada do registro. Se <span class="wintitle"> Input</span> for um campo de vetor, a primeira linha no vetor para a entrada de log relevante será usada. </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> ÚLTIMA LINHA: O valor da última entrada de log relacionada ao elemento de dimensão pai é usado, mesmo se a entrada estiver em branco. Se <span class="wintitle"> Input</span> for um campo de vetor, a primeira linha no vetor para a entrada de log relevante será usada. Se esse valor estiver em branco ou não for um número, ou se a entrada de log relevante não atender à Condição da dimensão, nenhum valor será usado. </li> 
     </ul> </p> <p> <p>Observação:  Se Operation não gerar valor, um valor em branco ("") será usado. </p> </p> <p> Você deve especificar uma operação para garantir que a dimensão seja definida conforme desejado. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pai </td> 
   <td colname="col2"> O nome da dimensão pai. Qualquer dimensão contável pode ser uma dimensão pai. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

A dimensão desnormalizada mostrada neste exemplo pega todos os dados no campo x-trackingid como entrada e os inclui em uma dimensão chamada ID do visitante. Para um segmento de visitantes que você criou, é possível exportar os dados na dimensão ID do visitante (bem como em qualquer outra dimensão definida).

![](assets/cfg_Transformation_Dim_Denormal.png)

