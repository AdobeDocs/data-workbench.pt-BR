---
description: Você pode criar um segmento dos elementos de qualquer dimensão contável e, em seguida, exportar os dados desse segmento em um lote ou em tempo real, em um arquivo delimitado por tabulação.
title: Configurar segmentos para exportar
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 6%

---

# Configurar segmentos para exportar{#configure-segments-for-export}

{{eol}}

Você pode criar um segmento dos elementos de qualquer dimensão contável e, em seguida, exportar os dados desse segmento em um lote ou em tempo real, em um arquivo delimitado por tabulação.

Toda vez que você esporta um segmento, ocorre a saída de métricas e dados de dimensão para todos os elementos da dimensão incluídos nesse segmento. É possível controlar como os dados de saída são formatados para que outros sistemas possam fazer upload dos dados facilmente.

>[!NOTE]
>
>Não é possível exportar dimensões de relatório, pois elas usam um [!DNL report time.metric] para referência. Como solução alternativa, se você colocar um código fixo [!DNL report time.metric] no perfil, a exportação do segmento pode usá-lo como ponto de referência para as dimensões do relatório. No entanto, a variável [!DNL report time.metric] O não atualiza automaticamente com base na Hora de início do perfil, de modo que, quando quiser alterar a referência da dimensão do relatório, altere a dimensão do código fixo [!DNL report time.metric] arquivo.

Para configurar um segmento para exportação, você deve abrir e editar um [!DNL .export] arquivo.

1. No [!DNL Profile Manager], clique no botão **[!UICONTROL Export]** no [!DNL File] para mostrar seu conteúdo.

       Se o diretório Export não existir, crie-o da seguinte maneira:
   
   1. Navegue até o diretório de instalação do Data Workbench.
   1. Abra o diretório do perfil com o qual você está trabalhando.
   1. No diretório Profile , crie um novo diretório chamado &quot;Export&quot;.

1. No [!DNL Profile Manager], clique com o botão direito do mouse na célula vazia no [!DNL User] para o diretório Export e clique em **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Um arquivo chamado [!DNL New Segment Export.export] aparece no [!DNL File] para Exportar.

1. Renomeie o novo arquivo clicando com o botão direito do mouse no [!DNL User] para o arquivo e digitando o novo nome no parâmetro Arquivo .
1. Abra o novo arquivo clicando com o botão direito do mouse no [!DNL User] para o arquivo e clicando em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   A janela de configuração do [!DNL .export] é exibido.

1. Clique em **[!UICONTROL Query]** e modifique os campos do [!DNL .export] conforme descrito na tabela a seguir:

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parâmetro... </th> 
   <th colname="col2" class="entry"> Fornecer essas informações... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Comando </td> 
   <td colname="col2"> <p>Opcional. Um programa a ser executado após a criação do Arquivo de saída. Este campo deve referenciar um executável (um <span class="filepath"> .exe </span> arquivo), não um comando shell. </p> <p>Observação: A exportação do segmento falhará se houver um espaço no parâmetro de comando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> <p>Opcional. Um filtro nomeado ou uma expressão de filtro. Você pode criar um filtro nomeado usando um editor de filtro e, em seguida, digitar o nome desse filtro aqui ou digitar uma expressão de filtro propriamente dita. </p> <p>Para obter mais informações sobre editores de filtro, consulte <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Editores de filtro </a>. Para obter mais informações sobre a sintaxe da expressão de filtro, consulte <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Sintaxe para expressões de filtro </a>. </p> <p>Os elementos de Nível que correspondem ao filtro são exportados, enquanto todos os outros elementos não são. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nível </td> 
   <td colname="col2"> <p>A dimensão contável cujos elementos devem ser exportados. </p> <p>Exemplo: Um nível de Visitante exporta uma linha de dados para cada visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo de saída </td> 
   <td colname="col2"> <p>Caminho e nome do arquivo dos dados exportados. Se o perfil estiver sendo executado em um cluster de servidores Data Workbench, cada servidor de Data Workbench gravará um Arquivo de Saída contendo uma parte dos dados. </p> <p>O diretório de instalação do servidor do Data Workbench contém um diretório Exportações, onde é possível salvar o arquivo de saída. Por exemplo, você pode inserir <span class="filepath"> Exportações\Segmento do visitante.txt </span>, onde <span class="filepath"> Visitor Segment.txt </span> é o nome do arquivo que contém os dados exportados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formato de saída </td> 
   <td colname="col2"> A métrica ou os dados da dimensão a serem exportados para cada elemento de Nível. Se a saída for um arquivo delimitado por tabulação, os campos deverão ser separados por caracteres de tabulação e o formato deverá terminar com os caracteres de nova linha apropriados. Para obter mais informações, consulte <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> Sobre o Formato de Saída </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de Término da Programação </td> 
   <td colname="col2"> <p>Opcional. A data e hora de término da programação, incluindo o fuso horário. </p> <p>Formato: Fuso horário AAAA-MM-DD hh:mm </p> <p>Exemplo: 2013-08-01 12:01 EDT </p> <p>As exportações programadas param neste momento; no entanto, o arquivo de saída ainda é gerado novamente sempre que sua definição é alterada. Este campo não tem sentido sem definir a Programação a Cada. Para obter mais informações sobre as configurações de fuso horário, consulte o <i>Guia de configuração do conjunto de dados</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Agendar a cada </td> 
   <td colname="col2"> Opcional. A frequência na qual gerar novamente o arquivo de saída. Os valores suportados são hora, dia, semana e mês. O Arquivo de Saída ainda é gerado novamente a qualquer momento em que sua definição é alterada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de Início da Programação </td> 
   <td colname="col2"> <p>Opcional. A data e hora de início da programação, incluindo o fuso horário. </p> <p>Formato: Fuso horário AAAA-MM-DD hh:mm </p> <p>Exemplo: 2013-08-01 12:01 EDT </p> <p>As exportações programadas começam nesse momento e a programação é relativa a esse momento. Este campo não tem sentido sem definir <span class="wintitle"> Agendar a cada </span>. Para obter mais informações sobre as configurações de fuso horário, consulte o <i>Guia de configuração do conjunto de dados</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de Tempo (s) </td> 
   <td colname="col2"> Opcional. O tempo máximo permitido para uma exportação de segmento ser gerado. Se o intervalo especificado for excedido, a exportação recomeçará. Configurar esse valor como 0 (zero) remove o limite. O valor padrão é de 600 segundos. </td> 
  </tr> 
 </tbody> 
</table>

1. Clique com o botão direito do mouse **[!UICONTROL (New)]** na parte superior da janela, em seguida, clique em **[!UICONTROL Save]**.
1. Para disponibilizar esse arquivo para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção do arquivo criado [!DNL .export] no [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Salvar o [!DNL .export] para o servidor do Data Workbench faz com que a exportação seja executada uma vez imediatamente, mesmo que a Hora de início da programação esteja definida como uma data e hora futuras.

   Veja a seguir uma amostra [!DNL .export] arquivo.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >O [!DNL Visitor Segment.export] o arquivo exibido na amostra refere-se ao filtro Segmento do visitante . Modificar a definição desse filtro altera a definição da exportação.
