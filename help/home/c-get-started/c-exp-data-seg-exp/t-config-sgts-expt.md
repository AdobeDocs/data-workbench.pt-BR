---
description: Você pode criar um segmento dos elementos de qualquer dimensão contável e, em seguida, produzir dados desse segmento em um lote ou em tempo real em um arquivo delimitado por tabulação.
solution: Analytics
title: Configurar segmentos para exportação
topic: Data workbench
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar segmentos para exportação{#configure-segments-for-export}

Você pode criar um segmento dos elementos de qualquer dimensão contável e, em seguida, produzir dados desse segmento em um lote ou em tempo real em um arquivo delimitado por tabulação.

Toda vez que você esporta um segmento, ocorre a saída de métricas e dados de dimensão para todos os elementos da dimensão incluídos nesse segmento. É possível controlar como os dados de saída são formatados para que outros sistemas possam fazer upload dos dados facilmente.

>[!NOTE]
>
>Não é possível exportar dimensões de relatório, pois elas usam um [!DNL report time.metric] arquivo para referência. Como solução, se você colocar um código fixo [!DNL report time.metric] no perfil, a exportação do segmento poderá usá-lo como ponto de referência para as dimensões do relatório. No entanto, o [!DNL report time.metric] não é atualizado automaticamente com base na Hora de início do perfil, portanto, quando você deseja alterar a referência da dimensão do relatório, é necessário alterar o [!DNL report time.metric] arquivo codificado permanentemente.

Para configurar um segmento para exportação, você deve abrir e editar um [!DNL .export] arquivo.

1. Na [!DNL Profile Manager], clique no **[!UICONTROL Export]** diretório na [!DNL File] coluna para mostrar seu conteúdo.

       Se o diretório Export não existir, crie-o da seguinte maneira:
   
   1. Navegue até o diretório de instalação do Análise de big data.
   1. Abra o diretório do perfil com o qual você está trabalhando.
   1. No diretório Profile, crie um novo diretório chamado &quot;Export&quot;.

1. Na [!DNL Profile Manager], clique com o botão direito do mouse na célula vazia na [!DNL User] coluna do diretório Export e, em seguida, clique em **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Um arquivo com o nome [!DNL New Segment Export.export] aparece na [!DNL File] coluna para Exportar.

1. Renomeie o novo arquivo clicando com o botão direito do mouse na [!DNL User] coluna do arquivo e digitando o novo nome no parâmetro Arquivo.
1. Abra o novo arquivo clicando com o botão direito do mouse na [!DNL User] coluna do arquivo e clicando em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   A janela de configuração do [!DNL .export] arquivo é exibida.

1. Clique em **[!UICONTROL Query]** e modifique os campos do [!DNL .export] arquivo conforme descrito na tabela a seguir:

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parâmetro... </th> 
   <th colname="col2" class="entry"> Fornecer estas informações... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Comando </td> 
   <td colname="col2"> <p>Opcional. Um programa a ser executado após a criação do Arquivo de saída. Esse campo deve fazer referência a um executável (um arquivo <span class="filepath"> .exe </span> ), não a um comando shell. </p> <p>Observação:  A exportação do segmento falhará se houver um espaço no parâmetro command. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> <p>Opcional. Um filtro nomeado ou uma expressão de filtro. Você pode criar um filtro nomeado usando um editor de filtro e, em seguida, digitar o nome desse filtro aqui ou digitar uma expressão de filtro propriamente dita. </p> <p>Para obter mais informações sobre editores de filtro, consulte <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Filtrar editores </a>. Para obter mais informações sobre a sintaxe de expressão de filtro, consulte <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Sintaxe para expressões de filtro </a>. </p> <p>Os elementos de Nível que correspondem ao filtro são exportados, enquanto todos os outros elementos não são exportados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nível </td> 
   <td colname="col2"> <p>A dimensão contável cujos elementos devem ser exportados. </p> <p>Exemplo: Um nível de Visitante exporta uma linha de dados para cada visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo de saída </td> 
   <td colname="col2"> <p>Caminho e nome do arquivo dos dados exportados. Se o perfil estiver sendo executado em um cluster de servidores da Análise de big data, cada servidor da Análise de big data gravará um Arquivo de saída contendo uma parte dos dados. </p> <p>O diretório de instalação do servidor do Análise de big data contém um diretório Exportações no qual é possível salvar o arquivo de saída. Por exemplo, você pode inserir <span class="filepath"> Exportações\Segmento do visitante </span>, onde <span class="filepath"> Visitor Segment.txt </span> é o nome do arquivo que contém os dados exportados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formato de saída </td> 
   <td colname="col2"> Os dados de métrica ou dimensão a serem exportados para cada elemento de Nível. Se a saída for um arquivo delimitado por tabulação, os campos devem ser separados por caracteres de tabulação e o formato deve terminar com os caracteres de nova linha apropriados. Para obter mais informações, consulte <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> Sobre o formato de saída </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de término da programação </td> 
   <td colname="col2"> <p>Opcional. A data e a hora de término da programação, incluindo o fuso horário. </p> <p>Formato: Fuso horário YYYY-MM-DD hh:mm </p> <p>Exemplo: 2013-08-01 12:01 EDT </p> <p>As exportações programadas param neste momento; no entanto, o Arquivo de saída ainda é gerado novamente sempre que sua definição é alterada. Este campo não tem sentido sem definir Agendar a cada. Para obter mais informações sobre as configurações de fuso horário, consulte o Guia <i>de configuração de</i>conjuntos de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Agendar a cada </td> 
   <td colname="col2"> Opcional. A frequência na qual o arquivo de saída deve ser gerado novamente. Os valores suportados são hora, dia, semana e mês. O Arquivo de saída ainda é gerado novamente sempre que sua definição for alterada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de início da programação </td> 
   <td colname="col2"> <p>Opcional. A data e a hora de início do agendamento, incluindo o fuso horário. </p> <p>Formato: Fuso horário YYYY-MM-DD hh:mm </p> <p>Exemplo: 2013-08-01 12:01 EDT </p> <p>As exportações programadas começam no momento e a programação é relativa a esse momento. Esse campo não tem sentido sem definir <span class="wintitle"> Agendar a cada </span>. Para obter mais informações sobre as configurações de fuso horário, consulte o Guia <i>de configuração de</i>conjuntos de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de tempo (s) </td> 
   <td colname="col2"> Opcional. O tempo máximo permitido para decorrer enquanto uma exportação de segmento é gerada. Se o intervalo especificado for excedido, a exportação recomeçará. Definir esse valor como 0 (zero) remove o limite. O valor padrão é 600 segundos. </td> 
  </tr> 
 </tbody> 
</table>

1. Clique com o botão direito do mouse **[!UICONTROL (New)]** na parte superior da janela e clique em **[!UICONTROL Save]**.
1. Para disponibilizar esse arquivo para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção do [!DNL .export] arquivo criado na [!DNL User] coluna e, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Salvar o [!DNL .export] arquivo no servidor da Análise de big data faz com que a exportação seja executada imediatamente, mesmo se a Hora de início da programação estiver definida como uma data e hora futuras.

   The following is a sample [!DNL .export] file.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >O [!DNL Visitor Segment.export] arquivo mostrado na amostra refere-se ao filtro Segmento do visitante. Modificar a definição desse filtro altera a definição da exportação.

