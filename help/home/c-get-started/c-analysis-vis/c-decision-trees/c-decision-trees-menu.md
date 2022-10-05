---
description: O menu Árvore de decisão inclui recursos para definir o caso de uso positivo, filtros, opções de distribuição de folhas, matriz de confusão e outras opções avançadas.
title: Opções de árvore de decisão
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
exl-id: e139562d-4613-4159-a858-2a78a2e896dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 2%

---

# Opções de árvore de decisão{#decision-tree-options}

{{eol}}

O menu Árvore de decisão inclui recursos para definir o caso de uso positivo, filtros, opções de distribuição de folhas, matriz de confusão e outras opções avançadas.

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
   <td colname="col2"> Clique em para executar o algoritmo da árvore de decisão e exibir a visualização. Essa opção fica esmaecida até que haja entradas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Redefinir </td> 
   <td colname="col2"> Apaga entradas e o modelo da árvore de decisão e redefine o processo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salvar </td> 
   <td colname="col2"><b>Salvar a árvore de decisão</b>. É possível salvar a Árvore de decisão em diferentes formatos: 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Linguagem de marcação preditiva (<b>PMML</b>), um formato de arquivo baseado em XML usado por aplicativos para descrever e trocar modelos de árvore de decisão. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Texto</b> exibição de colunas e linhas simples de true ou false, porcentagens, número de membros e valores de entrada. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">A <b>Dimension</b> com ramificações correspondentes a elementos de resultado previstos. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opções </td> 
   <td colname="col2"> Consulte a tabela abaixo para ver o menu Opções . </td> 
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
   <td colname="col1"> Definir Maiúsculas/Minúsculas Positivas </td> 
   <td colname="col2"> Define a seleção do espaço de trabalho atual como o Caso Positivo do modelo. Apaga as letras maiúsculas e minúsculas se não houver nenhuma seleção. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Definir filtro de população </td> 
   <td colname="col2"> Define a seleção do espaço de trabalho atual como o Filtro de população do modelo e será proveniente de visitantes que atendem a essa condição. O padrão é "Todos". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mostrar descrição de filtro complexo </td> 
   <td colname="col2"> Exibe descrições dos filtros definidos. Clique em para exibir os scripts de filtragem para Caso positivo e Filtro de população. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ocultar nós </td> 
   <td colname="col2"> Oculta nós com apenas uma pequena porcentagem da população. Esse comando de menu é exibido somente quando a árvore de decisão é exibida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matriz de Confusão </td> 
   <td colname="col2"> <p>Clique em <span class="uicontrol"> Opções</span> &gt; <span class="uicontrol"> Matriz de Confusão</span> para visualizar os valores de Precisão, Recall, Precisão e Pontuação F. Quanto mais próximo de 100 por cento, melhor a pontuação. </p> <p>A Matriz de Confusão fornece quatro contagens de precisão do modelo usando uma combinação de valores: 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Positivo Real (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Positivo previsto (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Negativo Real (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Previsto Negativo (PN) </li> 
     </ul> </p> <p>Dica: Esses números são obtidos pela aplicação do modelo de pontuação resultante dos dados de 20% de testes retidos e já conhecidos como a verdadeira resposta. Se a pontuação for maior que 50%, é previsto como um caso positivo (que corresponde ao filtro definido). Em seguida, Precisão = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN) e Precision = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibir Legenda </td> 
   <td colname="col2">Permite ativar e desativar uma chave de legenda na Árvore de decisão. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />Esse comando de menu é exibido somente quando a árvore de decisão é exibida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avançado </td> 
   <td colname="col2"> Clique para abrir o menu Avançado para um uso detalhado da Árvore de decisão. Consulte a tabela abaixo para ver as opções de menu. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu avançado </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tamanho do Conjunto de Treinamento </td> 
   <td colname="col2"> <p>Controla o tamanho do conjunto de treinamento usado para o edifício do modelo. Conjuntos maiores levam mais tempo para treinar, conjuntos menores levam menos tempo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalização de entrada </td> 
   <td colname="col2"> <p> Permite que o usuário especifique se deseja usar a técnica Min-Max ou a Pontuação Z para normalizar entradas no modelo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fator de sobreamostragem SMOTE </td> 
   <td colname="col2"> Quando o caso positivo não ocorre com muita frequência (menos de 10%) na amostra de treinamento, o SMOTE é usado para fornecer amostras adicionais. Essa opção permite que o usuário indique quantas mais amostras serão criadas usando o SMOTE. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de Distribuição de Classe Folha </td> 
   <td colname="col2"> Permite definir o limite assumido para uma folha durante o processo de criação da árvore. Por padrão, todos os membros de um nó devem ser idênticos para que seja uma folha (antes do estágio de poda). </td> 
  </tr> 
 </tbody> 
</table>
