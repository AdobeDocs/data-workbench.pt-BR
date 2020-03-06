---
description: Informações sobre parâmetros Report.cfg.
solution: Analytics
title: Parâmetros de Report.cfg
topic: Data workbench
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Parâmetros de Report.cfg{#report-cfg-parameters}

Informações sobre parâmetros Report.cfg.

A amostra [!DNL Report.cfg] mostrada em [Configurar o conjunto](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) de relatórios contém apenas os parâmetros incluídos no [!DNL Report.cfg] arquivo por padrão. A tabela a seguir fornece descrições de todos os parâmetros de [!DNL Report.cfg] arquivo disponíveis.

Se você precisar adicionar outros parâmetros a um [!DNL Report.cfg] arquivo, é necessário fazer isso usando um editor de texto. Para obter etapas para fazer isso, incluindo exemplos de como definir cada entrada de parâmetro, consulte [Editando arquivos](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)Report.cfg existentes.

>[!NOTE]
>
>Os parâmetros desta tabela são listados em ordem alfabética. Quando você abre o [!DNL Report.cfg] arquivo na Análise de big data, os vetores são listados em ordem alfabética, seguidos pelos parâmetros individuais listados em ordem alfabética.

<table id="table_F55E925EA34F43B6832788BB6878BB4A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Limite de Alerta </td> 
   <td colname="col2"> <p><i>Opcional</i>. Esse parâmetro se aplica somente aos relatórios com indicadores de métrica. Número de indicadores de métricas que devem aparecer na planilha antes do envio de um relatório de alerta. </p> <p>Se apenas uma métrica estiver sendo monitorada na planilha do indicador de métrica, defina o limite como 1. O relatório é gerado quando a métrica na planilha é avaliada como uma seta para cima/para baixo ou como um X. Se mais de uma métrica estiver sendo monitorada no relatório, você poderá selecionar o número de indicadores de métrica que devem ser avaliados como uma seta para cima/para baixo ou um X antes de o relatório ser gerado. Por exemplo, se duas métricas estiverem sendo monitoradas: 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">Se o limite for definido como 1, o relatório será gerado se uma das métricas na planilha for avaliada como uma seta para cima/para baixo ou como um X. </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">Se o limite for definido como 2, ambas as métricas devem avaliar para uma seta para cima/para baixo ou para um X antes de o relatório ser gerado. </li> 
     </ul> </p> <p>Para obter mais informações sobre indicadores de métricas, consulte o Guia <i>do Usuário da Análise de</i>big data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Permitir Regeneração de Relatório </td> 
   <td colname="col2"> <p>Indica se o Servidor de <span class="keyword"> relatórios gera </span> ou regenera automaticamente relatórios específicos ao criar ou modificar esses relatórios. As opções são true ou false. Se definido como true, a criação ou modificação de um espaço de trabalho de relatório faz com que o <span class="keyword"> </span> Servidor de Relatório gere novamente esse relatório para a execução mais recente. </p> <p> <p>Observação:  Alterar o arquivo <span class="filepath"> Report.cfg </span> faz com que o <span class="keyword"> Report Server </span> regenere todos os relatórios controlados por esse <span class="filepath"> arquivo Report.cfg </span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Anexos </td> 
   <td colname="col2"> <p><i>Opcional</i>. Identificador de seção para o nome e o tipo de conteúdo de quaisquer anexos que saem com relatórios distribuídos por email, incluindo o número de anexos. </p> <p>Para adicionar um novo anexo: 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">Abra o arquivo <span class="filepath"> Report.cfg </span> na Análise de big data. </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">Clique com o botão direito do mouse em <span class="uicontrol"> Anexos </span> e clique em <span class="uicontrol"> Adicionar novo filho </span> &gt; <span class="uicontrol"> Anexo </span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo de conteúdo </td> 
   <td colname="col2"> <p>Tipo de conteúdo do arquivo a ser anexado. </p> <p>Exemplo: image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FileName </td> 
   <td colname="col2"> <p>Localização e nome do ficheiro a anexar. </p> <p>Exemplo: <span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conjunto de cores </td> 
   <td colname="col2"> Identifica o esquema de cores a ser usado para arquivos <span class="filepath"> .png </span> . 0 é para um fundo preto; 1 é para um fundo branco; e 2 é para uma imagem em tons de cinza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comando para execução </td> 
   <td colname="col2"> <i>Opcional</i>. Um comando em lote ou executável que é executado após a geração do conjunto de relatórios. Se a inicialização do interpretador do shell de comando for necessária, preceda o comando com cmd /c. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modelo padrão do Excel </td> 
   <td colname="col2"> <p><i>Opcional</i>. Nome do arquivo de modelo genérico do Excel ( <span class="filepath"> .xls </span> ou <span class="filepath"> .xlsx </span>) que você deseja usar ao gerar relatórios como arquivos do Excel. Esse parâmetro oferece suporte a caminhos completos de arquivos, como <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>Esse arquivo é usado para todos os relatórios do Excel, a menos que um modelo tenha sido definido especificamente para um relatório específico. Consulte <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Usando um Arquivo de Modelo </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome da dimensão </td> 
   <td colname="col2"> <i>Opcional</i>. Nome da dimensão para a qual você deseja gerar dinamicamente um relatório. Se você inserir um nome de dimensão nesse parâmetro, deverá inserir um valor nos parâmetros Arquivo de pesquisa ou Métrica N superior e Valor N superior. A dimensão nomeada neste parâmetro deve existir no conjunto de dados para o qual os relatórios estão sendo criados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Somente Email Se Perfeito </td> 
   <td colname="col2"> <i>Opcional</i>. Permite que o usuário especifique que um conjunto de relatórios deve ser enviado somente quando nenhum erro ocorrer durante a execução. As opções são verdadeiras e falsas. O valor padrão é false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data final </td> 
   <td colname="col2"> <p><i>Opcional</i>. A última data e hora em que você deseja que o relatório seja executado. Desta vez, é baseado no tempo de início do conjunto de dados. </p> <p>Formato: MM/DD/AAAA fuso horário hh:mm, usando a sintaxe de 24 horas para o horário </p> <p>Exemplo: 01/08/2007 12:01 EDT </p> <p>Para obter mais informações sobre as configurações de fuso horário, consulte o Guia <i>de configuração de</i>conjuntos de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Todo(a) </td> 
   <td colname="col2"> Frequência da geração do conjunto de relatórios: dia, semana ou mês. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo limite do Excel Watchdog (segundos) </td> 
   <td colname="col2"> <p><i>Opcional</i>. O número de segundos que você deseja que o <span class="keyword"> Report Server aguarde </span> que o Microsoft Excel responda ao gerar um relatório como um arquivo do Excel antes que o <span class="keyword"> Report Server </span> decida que o Excel não está respondendo e conclua o processo. O uso desse parâmetro permite que o <span class="keyword"> Report Server encerre </span> o Excel quando ele não responde e continue processando seus relatórios que não são do Excel. O padrão é 300.0. Para desativar essa funcionalidade, defina esse parâmetro como 0,0. </p> <p>Verifique se o valor definido é longo o suficiente para permitir que o relatório seja exportado para o Excel. Caso contrário, <span class="keyword"> o Servidor de relatórios </span> pode encerrar prematuramente o Excel e seu relatório não será gerado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtrar fórmula </td> 
   <td colname="col2"> <p><i>Opcional</i>. Filtro que é aplicado a cada espaço de trabalho no conjunto de relatórios. </p> <p>Para obter mais informações, consulte a <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> sintaxe para criar filtros </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Correção gama </td> 
   <td colname="col2"> <p>Configuração de gama para saída de arquivo <span class="filepath"> .png </span> . O padrão é 1.6. </p> <p> <p>Observação:  A Adobe recomenda que você não altere esse valor. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ocultar logotipos </td> 
   <td colname="col2"> Indica se o Servidor de relatórios oculta os logotipos ao gerar seus relatórios. As opções são <span class="filepath"> true </span> ou <span class="filepath"> false </span>. Se definido como <span class="filepath"> falso </span>, seu relatório será gerado com o logotipo do Relatório. The default is <span class="filepath"> false </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo de pesquisa </td> 
   <td colname="col2"> <p><i>Opcional</i>. Quando esse parâmetro é preenchido, o Servidor de relatórios é executado no modo dinâmico e gera relatórios para cada elemento da dimensão especificada no parâmetro Nome da dimensão. Esse arquivo deve conter duas colunas delimitadas por tabulação, sem uma linha de cabeçalho. </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">A coluna 1 contém uma lista de elementos de dimensão. </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">A coluna 2 contém os endereços de email dos destinatários do relatório. Um relatório para um dado elemento na coluna 1 é enviado para o endereço de email na mesma linha da coluna 2. Você pode inserir vários endereços de email separando-os por vírgulas (sem espaços). Se os relatórios não forem enviados por email, essa coluna poderá estar vazia, mas deverá existir. </li> 
     </ul> </p> <p> <p>Observação:  Se você inserir um valor nesse parâmetro, deverá informar um valor no parâmetro Nome da Dimensão. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Somente notificação </td> 
   <td colname="col2"> Essa <span class="wintitle"> configuração do Servidor de </span> relatórios permite configurar o análise de big data para enviar um email quando um relatório é gerado. Configurar esse valor como <span class="filepath"> true </span> não envia o relatório, mas envia um email notificando ao usuário inscrito que o relatório foi gerado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Relatório de email </td> 
   <td colname="col2"> <p>Identificador de seção para distribuir relatórios por email. Para distribuir relatórios por email, preencha os seguintes parâmetros para a entrada Relatório de <span class="wintitle"> email </span> . Todos os relatórios no conjunto de relatórios são enviados por email em uma mensagem para os endereços de email especificados no parâmetro Destinatários. </p> <p> <p>Observação:  O Servidor de relatórios envia um email somente quando gerou pelo menos um relatório. </p> </p> <p>Para habilitar o envio de relatórios por email, você deve concluir pelo menos os seguintes parâmetros para esta entrada: 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">Servidor SMTP </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">Destinatários </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">Endereço do remetente </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">Somente notificação </li> 
     </ul> </p> <p> <p>Observação:  Para enviar relatórios por e-mail depois de regerar um conjunto de relatórios, consulte <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> Editando arquivos Report.cfg existentes </a>. </p> </p> <p>O valor Somente notificação está disponível nas versões 5.4x e 5.5x. </p> <p>Para que um grande conjunto de destinatários seja notificado (mais de 20), é altamente recomendável usar listas de distribuição de email. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modelo XSL do Corpo </td> 
   <td colname="col2"> <p><i>Opcional</i>. Caminho do arquivo de modelo XSL a ser aplicado ao arquivo <span class="filepath"> reports.xml </span> . O uso desse parâmetro permite que o Servidor de relatórios envie seus relatórios dentro do email distribuído em vez de como anexos. O texto resultante é usado como o corpo da mensagem de email. </p> <p>Consulte <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Arquivos de amostra de relatório </a> para obter uma amostra do arquivo. </p> <p>Para obter informações sobre o XSLT (Extensible Stylesheet Language), consulte <a href="http://www.w3.org/Style/XSL/" format="http" scope="external"> A Família Extensible Stylesheet Language </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Destinatários </td> 
   <td colname="col2"> Endereços de email das pessoas para as quais você deseja enviar o relatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço do remetente </td> 
   <td colname="col2"> Endereço de email do remetente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome do remetente </td> 
   <td colname="col2"> Opcional. Nome do remetente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP </td> 
   <td colname="col2"> Endereço da máquina do servidor SMTP e a senha e o nome de usuário necessários para autenticação. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Assunto </td> 
   <td colname="col2"> <i>Opcional</i>. Linha de assunto que descreve o email a ser enviado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Somente notificação </td> 
   <td colname="col2"> Permite configurar o análise de big data para enviar um email quando um relatório em segundo plano é gerado. Definir esse valor como Verdadeiro não envia o relatório, mas envia um email vinculando o usuário inscrito ao local do relatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Raiz de saída </td> 
   <td colname="col2"> <p><i>Opcional</i>. Local de saída dos conjuntos de relatórios gerados. O padrão é a pasta <i>&lt;nome do perfil&gt;</i>\Reports no diretório de instalação do Servidor de relatórios. </p> <p>Para configurar o Servidor <span class="keyword"> de relatórios </span> para gerar relatórios em um portal, defina a Raiz de <span class="wintitle"> saída </span> para a raiz do documento do servidor Web usado para o portal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pré-carregar Filtro de Consulta </td> 
   <td colname="col2"> <p><i>Opcional</i>. Esse parâmetro se aplica somente ao tipo de relatório <span class="wintitle"> Principal Elemento de Dimensão </span> . </p> <p>O nome do filtro que você deseja aplicar à consulta que deve ser executada para determinar os N principais elementos de dimensão antes que o relatório possa ser gerado. O padrão é <span class="wintitle"> Broken_Session_Filter </span>. Para obter mais informações sobre o Filtro de sessão <span class="wintitle"> quebrada </span>, consulte o Guia <i>do Usuário da Análise de</i>big data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tipos de relatórios </span> </td> 
   <td colname="col2"> <p>Formato(s) em que deseja gerar a saída. É possível usar qualquer uma ou todas as opções a seguir para produzir o conjunto de relatórios em vários formatos ao mesmo tempo: 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">O Excel cria uma pasta de trabalho do Excel com uma visualização por planilha. Como regra geral, use arquivos Excel para distribuição de email. Consulte <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Geração de relatórios como arquivos do Microsoft Excel </a>. Para obter informações sobre como usar um arquivo de modelo, consulte <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> Uso de um arquivo de modelo </a>. </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png cria arquivos Gráficos de Rede Portáteis. Como regra geral, use arquivos <span class="filepath"> .png </span> para exibição em um navegador da Web (portal). </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">A miniatura cria uma miniatura (arquivo <span class="filepath"> .jpg </span> ) do espaço de trabalho. O tamanho padrão é 240 x 180. Para alterar o tamanho padrão, edite os parâmetros Miniatura X e Miniatura Y. </li> 
     </ul> </p> <p>Para adicionar um novo tipo de relatório ao editar <span class="filepath"> Report.cfg </span> na análise de big data, clique com o botão direito do mouse em <span class="uicontrol"> Tipos de relatório </span>, clique em <span class="uicontrol"> Adicionar novo filho </span>e selecione o tipo de relatório desejado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data inicial </td> 
   <td colname="col2"> <p>A primeira data e hora em que você deseja que o relatório seja executado. Desta vez, é baseado no tempo de início do conjunto de dados. </p> <p>Formato: MM/DD/AAAA fuso horário hh:mm, usando a sintaxe de 24 horas para o horário. </p> <p>Para obter mais informações sobre as configurações de fuso horário, consulte o Guia <i>de configuração de</i>conjuntos de dados. </p> <p> <p>Observação:  Os relatórios começam a ser executados quando os carimbos de data e hora dos dados no perfil correspondem à data e hora especificadas. </p> </p> <p>Exemplo: </p> <p>Se a data de início for 08/08/2006 12:00 EST, os relatórios serão executados para dados com um carimbo de data e hora de 08/08/2006 12:00 EST e posterior. 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">Os relatórios diários serão executados para 08/08/2006 e a cada dia depois para dados com hh:mm = 12:00 EST. </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">Os relatórios semanais serão executados para 08/08/2006 e para cada sétimo dia depois para dados com hh:mm = 12:00 EST. </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">Os relatórios mensais serão executados para 08/08/2006 e para o 8.o dia de cada mês a partir daí, para dados com hh:mm = 12:00 EST. </li> 
     </ul> </p> <p>A métrica Tempo do <span class="wintitle"> relatório </span> afeta as dimensões do relatório "Últimos N", como "Últimos 7 dias", "Ontem" e "Há 3 semanas". Para consultas no Servidor de relatórios, a <span class="wintitle"> métrica Tempo do relatório </span> ( <span class="filepath"> Tempo do relatório.métrica </span>) identifica a data e a hora para a qual os relatórios estão sendo executados. Inicialmente, essa é a data e a hora especificadas no parâmetro Data inicial, que é incrementado pelo período especificado pelo parâmetro Cada. Para consultas na análise de big data, a métrica Tempo do <span class="wintitle"> relatório </span> se baseia na meia-noite da métrica Como de ( <span class="filepath"> As de.metric </span>). Devido à diferença nas definições da métrica Tempo do relatório, se você consultar um espaço de trabalho que usa uma dimensão Último N, poderá receber resultados diferentes na análise de big data e no <span class="keyword"> Servidor de relatório </span> para o mesmo espaço de trabalho. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatura X </td> 
   <td colname="col2"> <i>Opcional</i>. Número inteiro que controla o tamanho (em pixels) do eixo X das miniaturas geradas como saída. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatura Y </td> 
   <td colname="col2"> <i>Opcional</i>. Número inteiro que controla o tamanho (em pixels) do eixo Y das miniaturas geradas como saída. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica N superior </td> 
   <td colname="col2"> <p><i>Opcional</i>. Consulte a descrição do parâmetro N Valor Superior. </p> <p> <p>Observação:  Se você inserir um valor nesse parâmetro, deverá informar um valor no parâmetro Nome da Dimensão e no parâmetro Valor Superior N. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valor N Superior </td> 
   <td colname="col2"> <p><i>Opcional</i>. Quando esse parâmetro é preenchido, o Servidor de <span class="keyword"> relatórios </span> é executado no modo dinâmico e gera relatórios para o número superior (especificado neste parâmetro) de elementos para a dimensão especificada no parâmetro Nome da dimensão, contando pela métrica especificada no parâmetro Métrica Top N. </p> <p>Exemplo: Se você digitar Página no parâmetro Nome da Dimensão, Sessões no parâmetro Métrica N Superior e 5 nesse parâmetro, o relatório gerado listará as cinco principais páginas com o maior número de sessões. </p> <p> <p>Observação:  Se você inserir um valor nesse parâmetro, deverá informar um valor no parâmetro Nome da dimensão e no parâmetro Métrica N superior. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar apenas amostra local </td> 
   <td colname="col2"> <i>Opcional</i>. Indica se você deseja que o Servidor de <span class="keyword"> relatórios gere relatórios </span> usando apenas a amostra local do conjunto de dados. A definição desse parâmetro como true permite que você visualize uma amostra do conjunto de relatórios (sem colocar uma carga em um servidor de análise de big data) para ver a aparência da saída sem precisar de todo o tempo necessário para processar os dados. Isto funciona como uma função de teste. As opções são true ou false. O padrão é false. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caminho da área de trabalho </td> 
   <td colname="col2"> <p><i>Opcional</i>. Localização de uma coleção de espaços de trabalho para um determinado conjunto de relatórios. Isso é útil para manter uma única cópia dos espaços de trabalho que precisam ser gerados e distribuídos de várias maneiras, usando arquivos <span class="filepath"> Report.cfg </span> para vários conjuntos de relatórios. O diretório raiz desse caminho pode ser qualquer pasta de perfil. Não insira uma barra (\) no início da string de caminho. </p> <p>Exemplo: Você pode salvar os espaços de trabalho comuns para o Conjunto A e o Conjunto B na pasta <span class="filepath"> Relatórios\Comuns </span> e, em seguida, definir os arquivos <span class="filepath"> Report.cfg </span> para dois conjuntos de relatórios diferentes, cada um com configurações de geração e distribuição diferentes. Em ambos os <span class="filepath"> arquivos Report.cfg, você definiria o parâmetro Caminho da Workspace como nome </span> \Reports\Common do <i></i>perfil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo de saída XSL </td> 
   <td colname="col2"> <i>Opcional</i>. Caminho do arquivo de saída criado quando o Modelo <span class="wintitle"> XSL </span> é aplicado ao índice do relatório. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modelo XSL </td> 
   <td colname="col2"> <p><i>Opcional</i>. Caminho do arquivo de modelo XSL a ser aplicado ao índice do relatório. O <span class="filepath"> .xml transformado resultante </span> é gravado no Arquivo de saída <span class="wintitle"> XSL especificado </span>. Consulte <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> Arquivos de amostra de relatório </a> para obter uma amostra do arquivo. </p> <p> <p>Observação:  A menos que você use um modelo <span class="filepath"> .xsl </span> ao gerar seus relatórios, todos os relatórios serão distribuídos por email como anexos. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

