---
description: O recurso de exportação CRS (Customer Record Service) permite exportar a Data Workbench para os Serviços principais da Adobe Analytics para integrar com outros recursos do Analytics, incluindo Reports & Analytics.
title: Exportar para os serviços principais do Analytics
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
exl-id: 573085e8-2260-4872-be90-a84ad61145bb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 2%

---

# Exportar para os serviços principais do Analytics{#exporting-to-analytics-core-services}

O recurso de exportação CRS (Customer Record Service) permite exportar a Data Workbench para os Serviços principais da Adobe Analytics para integrar com outros recursos do Analytics, incluindo Reports &amp; Analytics.

>[!NOTE]
>
>Para que o recurso de exportação do CRS funcione, a Analytics ID de um visitante deve se basear no serviço de Experience Cloud ID (ECID). Embora a ECID possa ser preenchida na Data Workbench para um visitante, se o cliente estiver no período de carência ou o cookie do visitante não tiver sido substituído pela ECID, a exportação do CRS não funcionará para esse visitante. Para obter mais informações, consulte [Identificação de visitantes](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) e [Período de carência do serviço de ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html).

Em uma **Tabela de detalhes** (clique com o botão direito do mouse em **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** em um espaço de trabalho), é possível definir valores de atributo e as variáveis necessárias para integrar com os Reports &amp; Analytics do Analytics (usando os Serviços de pipeline de Adobe).

1. **Clique com o botão direito do mouse no cabeçalho da tabela e clique em New Customer Record Service (Novo serviço de registro do cliente).**

   ![](assets/6_4_CRS.png)

1. **Nomeie o arquivo de exportação e salve.**

   A janela de edição do arquivo de exportação será aberta.

1. **** **OpenQuery > Configuração CRS**.
1. **Clique com o botão direito do mouse em Atributos CRS > Adicionar novo.**
1. **** ***Inserir parâmetros*** **de atributos CRS**.

   Abra a nova entrada e insira ou verifique valores na seção *Atributos CRS* do arquivo de exportação:

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Nome do atributo</b> </p> </td> 
      <td colname="col2">Nome da variável <i>Atributos do cliente</i> exibida em <i>Reports &amp; Analytics</i>. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Tipo de atributo</b> </td> 
      <td colname="col2"> <p>Esse parâmetro aceita valores de (<i>int</i>, <i>string</i>). </p> <p>Observação: Se um atributo for <b>não</b> inscrito no Analytics: <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">O atributo será criado com qualquer tipo de atributo válido suportado pelo Analytics (para esta versão, está limitado a apenas <i>string</i> e <i>int</i>). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Se um tipo de atributo inválido for inserido, você receberá um erro informando uma falha na assinatura do Analytics. </li> 
      </ul> </p> <p>Se um atributo for <b>já</b> inscrito no Analytics: </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Certifique-se de inserir o tipo de atributo correto para o atributo já inscrito. </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Se você inserir o tipo errado para o atributo, seu comportamento dependerá do manuseio dos tipos de atributos pelo Analytics. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Nome do campo</b> </p> </td> 
      <td colname="col2">Nome da dimensão ou métrica da qual os valores do atributo são selecionados. <p>Observação: O <i><b>Nome do Campo</b></i> em <i>Atributos CRS</i> deve ser o mesmo que <b><i>Campos de Saída</i> &gt; <i>Nome do Campo</i></b> (que é preenchido automaticamente com base no atributo selecionado). Se o <i>Nome do Campo</i> for inválido, a exportação não será executada. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Clique com o botão direito do mouse em **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Insira as informações **[!UICONTROL Report Suite ID]**.

   Abra a nova entrada e digite ou verifique valores na seção *Report Suite* do arquivo de exportação:

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Conjunto de relatórios</b> </td> 
      <td colname="col2">ID do conjunto de relatórios em <i>Reports &amp; Analytics</i> identificando as variáveis <i>Atributo do cliente</i> que estão sendo exportadas. <p> <p>Observação: Embora <i>Reports &amp; Analytics</i> permita adicionar a vários conjuntos de relatórios, a Data Workbench 6.4 só exportará um único conjunto de relatórios identificado em <i>index 0</i>. <p>O valor do conjunto de relatórios inserido nesse campo é a ID do conjunto de relatórios (e não o nome do conjunto de relatórios). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Insira o parâmetro do campo ECID.

   **Campo** ECID: Nome da dimensão no perfil que representa a Adobe Experience Cloud ID. Este é um campo obrigatório e qualquer valor de dimensão inválido inserido não será exportado.

1. (opcional) Preencha o parâmetro Campo de ID do visitante .

   **Campo** de ID do visitante: Se o usuário desejar enviar qualquer outra ID personalizada para um visitante em seus dados, é aqui que ele insere o nome da dimensão que representa a ID de visitante personalizada. Este é um campo opcional e pode ser deixado em branco.
