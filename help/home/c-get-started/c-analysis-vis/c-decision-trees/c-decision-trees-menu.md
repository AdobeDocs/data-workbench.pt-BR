---
description: O menu Árvore decisória inclui recursos para definir o caso de uso positivo, os filtros, as opções de distribuição de folhas, a matriz de confusão e outras opções avançadas.
title: Opções da árvore decisória
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Opções da árvore decisória{#decision-tree-options}

O menu Árvore decisória inclui recursos para definir o caso de uso positivo, os filtros, as opções de distribuição de folhas, a matriz de confusão e outras opções avançadas.

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Botões da barra de ferramentas </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ir </td> 
   <td colname="col2"> Clique para executar o algoritmo da árvore de decisão e exibir a visualização. Isso fica esmaecido até que haja entradas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reset </td> 
   <td colname="col2"> Limpa as entradas e o modelo da árvore decisória e redefine o processo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salvar </td> 
   <td colname="col2"><b>Salve a árvore</b>decisória. É possível salvar a Árvore decisória em diferentes formatos: 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Linguagem de marcação preditiva (<b>PMML</b>), um formato de arquivo baseado em XML usado por aplicativos para descrever e trocar modelos de árvore decisória. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Texto</b> que exibe colunas simples e linhas de true ou false, porcentagens, número de membros e valores de entrada. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">Uma <b>Dimensão</b> com ramificações correspondentes a elementos de resultado previstos. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opções </td> 
   <td colname="col2"> Consulte a tabela abaixo para ver o menu Opções. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu Opções </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Definir Maiúsculas e Minúsculas Positivas </td> 
   <td colname="col2"> Define a seleção do espaço de trabalho atual como o Caso Positivo do modelo. Apaga as letras maiúsculas e minúsculas se não houver nenhuma seleção. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Definir filtro de preenchimento </td> 
   <td colname="col2"> Define a seleção do espaço de trabalho atual como o Filtro de preenchimento do modelo e será extraída de visitantes que atenderem a essa condição. O padrão é "Todos". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mostrar descrição do filtro complexo </td> 
   <td colname="col2"> Exibe descrições dos filtros definidos. Clique para exibir os scripts de filtragem para Caso positivo e Filtro de população. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ocultar nós </td> 
   <td colname="col2"> Oculta nós com apenas uma pequena porcentagem da população. Esse comando de menu é exibido somente quando a árvore decisória é exibida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matriz de Confusão </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Opções</span> &gt; <span class="uicontrol"> Matriz</span> de conversão para exibir os valores de precisão, recuperação, precisão e pontuação F. Quanto mais próximo de 100 por cento, melhor a pontuação. </p> <p>A Matriz de Confusão fornece quatro contagens de precisão do modelo usando uma combinação de valores: 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Positivo Real (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Positivo Previsto (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Negativo Real (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Previsto Negativo (PN) </li> 
     </ul> </p> <p>Dica:  Esses números são obtidos pela aplicação do modelo de pontuação resultante dos 20% de dados de teste retidos e já conhecidos como a resposta verdadeira. Se a pontuação for maior que 50 por cento, será previsto como um caso positivo (que corresponde ao filtro definido). Em seguida, precisão = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN) e Precision = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibir legenda </td> 
   <td colname="col2">Permite que você alterne uma tecla de legenda para ligar e desligar na Árvore decisória. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />Esse comando de menu é exibido somente quando a árvore decisória é exibida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Advanced </td> 
   <td colname="col2"> Clique para abrir o menu Avançado para obter o uso mais detalhado da Árvore decisória. Consulte a tabela abaixo para ver as opções de menu. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu Avançado </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tamanho do conjunto de treinamento </td> 
   <td colname="col2"> <p>Controla o tamanho do conjunto de treinamento usado para o edifício do modelo. Conjuntos maiores demoram mais para treinar, conjuntos menores demoram menos tempo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalização de entrada </td> 
   <td colname="col2"> <p> Permite que o usuário especifique se deve usar a técnica Min-Max ou Pontuação Z para normalizar as entradas no modelo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fator de sobreamostragem SMOTE </td> 
   <td colname="col2"> Quando o Caso positivo não ocorre com muita frequência (menos de 10%) na amostra de treinamento, o SMOTE é usado para fornecer amostras adicionais. Essa opção permite que o usuário indique quantas mais amostras serão criadas usando SMOTE. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de Distribuição de Classe Folha </td> 
   <td colname="col2"> Permite definir o limite assumido para uma folha durante o processo de construção da árvore. Por padrão, todos os membros de um nó devem ser idênticos para que seja uma folha (antes do estágio de poda). </td> 
  </tr> 
 </tbody> 
</table>

