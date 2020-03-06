---
description: O perfil de tráfego contém as seguintes dimensões para ajudar a identificar as ações do visitante.
solution: Analytics
title: Dimensões do perfil de tráfego
topic: Data workbench
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensões do perfil de tráfego{#traffic-profile-dimensions}

O perfil de tráfego contém as seguintes dimensões para ajudar a identificar as ações do visitante.

As dimensões na tabela a seguir são definidas no conjunto de dados de transformação para incluir arquivos na pasta Traffic\Dataset\Transformation directory.

| Nome | Tipo | Nível | Descrição |
|---|---|---|---|
| Dia | Simples | Sessão | O dia da primeira entrada do registro da sessão. |
| Dias da semana | Simples | Sessão | O dia da semana da primeira entrada do registro de uma sessão. |
| Duração Exata da Página (Oculta) | Numérico | Exibição da Página | A duração, em milissegundos, da exibição de página, conforme medido ao subtrair o tempo da próxima exibição de página do momento dessa exibição de página. A duração exata da última exibição de página em uma sessão é sempre 0. |
| Hora | Simples | Sessão | A hora da primeira entrada do registro de uma sessão. |
| Hora do dia | Simples | Sessão | A hora do dia da primeira entrada do registro de uma sessão. |
| Mês | Simples | Sessão | O mês da primeira entrada de registro de uma sessão. |
| Exibição da Página | Contável | Sessão | Uma entrada de registro ou &quot;Registro de dados de evento&quot; que satisfaz a condição de exibição de página. |
| Referenciador | Simples | Sessão | O domínio de segundo nível do referenciador da primeira entrada de log da sessão (ou Nenhum se for um domínio de referenciador interno). |
| Sessão | Contável | Visitante | Um período de atividade contígua relacionada por um Visitante. É delimitado por um período de inatividade de 30 minutos e um domínio de referenciador externo ou uma Duração máxima de sessão de 48 horas. Ambos os tempos limite e o conjunto de domínios considerados internos podem ser configurados no [!DNL Transformation.cfg] arquivo. |
| URI | Simples | Exibição da Página | O fluxo de URI de uma exibição de página. A dimensão URI pode ser redefinida usando as transformações ReplaceURI, PrependURI e AppendURI. |
| Visitante | Contável | N/D | Um valor exclusivo de x-trackingid. Geralmente corresponde a um navegador exclusivo se cookies persistentes forem usados. Caso contrário, o x-trackingid pode se basear no número IP ou em algum outro identificador exclusivo, como nome comum x.509. |
| Semana | Simples | Sessão | A semana da primeira entrada do registro de uma sessão. |

As dimensões na tabela a seguir são definidas no diretório Dimensão do perfil Tráfego:

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensão </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col03" class="entry"> Nível </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Navegador </td> 
   <td colname="col2"> Simples </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> O tipo de agente do usuário usado pelo visitante, incluindo o número da versão (por exemplo, MSIE 6.0). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tipo de navegador </td> 
   <td colname="col2"> Simples </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> O tipo de agente do usuário usado pelo visitante (por exemplo, MSIE). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mecanismo de pesquisa </td> 
   <td colname="col2"> Simples </td> 
   <td colname="col03">Sessão <p>PRIMEIRA LINHA </p></td> 
   <td colname="col3"> O primeiro mecanismo de pesquisa na sessão do visitante quando um visitante tiver pesquisado de um mecanismo de pesquisa nomeado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI seguinte </td> 
   <td colname="col2"> Derivado (ShiftDim com base na dimensão URI) </td> 
   <td colname="col03"> Exibição da Página </td> 
   <td colname="col3"> O URI do URI seguinte após o URI atualmente selecionado. Essa dimensão derivada é usada para realizar análises sobre o que os visitantes fazem depois de qualquer URI. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Onetime vs Repetir </td> 
   <td colname="col2"> Derivado (SegmentDim com base nas métricas Repetir visitantes e Visitantes únicos) </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> O tipo de visitante: uma vez ou repita. Visitantes únicos tiveram apenas uma sessão no site, enquanto visitantes repetidos tiveram mais de uma sessão. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página </td> 
   <td colname="col2"> Derivado (RenameDim com base na dimensão URI) </td> 
   <td colname="col03"> Exibição da Página </td> 
   <td colname="col3"> O nome de cada página visitada durante uma sessão. Inicialmente, o nome de cada página é igual ao URI, mas pode ser alterado para facilitar a interpretação. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referenciador </td> 
   <td colname="col2"> Herdado da dimensão do Referenciador incorporado </td> 
   <td colname="col03"> Sessão </td> 
   <td colname="col3"> O nome de domínio de segundo nível do site que primeiro indicou uma sessão para o site (conforme fornecido pelo navegador do visitante). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Frase de pesquisa </td> 
   <td colname="col2"> Simples </td> 
   <td colname="col03">Sessão <p>PRIMEIRA LINHA </p></td> 
   <td colname="col3"> A primeira frase de pesquisa em uma sessão de visitante, como transmitida por um mecanismo de pesquisa quando um visitante pesquisou de um mecanismo de pesquisa nomeado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Termo de Pesquisa </td> 
   <td colname="col2"> Muitos para muitos </td> 
   <td colname="col03"> Sessão </td> 
   <td colname="col3"> Cada termo de pesquisa como passado por um mecanismo de pesquisa quando um visitante tem um click-through de referenciador de pesquisa de um mecanismo de pesquisa nomeado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duração da sessão </td> 
   <td colname="col2"> Derivado (MetricDim com base na métrica Duração exata da página) </td> 
   <td colname="col03"> Sessão </td> 
   <td colname="col3"> A duração de uma sessão em incrementos de 30 segundos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número da sessão </td> 
   <td colname="col2"> Simples </td> 
   <td colname="col03"> Sessão </td> 
   <td colname="col3"> O número de vezes que um visitante visitou o site. Por exemplo, os visitantes que acessam pela primeira vez têm um Número de sessão "1", os visitantes que acessam pela segunda vez têm um Número de sessão "2", etc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições de página da sessão </td> 
   <td colname="col2"> Derivado (MetricDim com base na métrica Exibições de página) </td> 
   <td colname="col03"> Sessão </td> 
   <td colname="col3"> O número de exibições de página em uma sessão. Por exemplo, selecionar "3" na dimensão Exibições de página da sessão selecionaria todas as sessões com exatamente 3 exibições de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mecanismo de pesquisa </td> 
   <td colname="col2"> Simples </td> 
   <td colname="col03"> Sessão </td> 
   <td colname="col3"> O nome de domínio de segundo nível do primeiro site que é um mecanismo de pesquisa nomeado que encaminhou um visitante para o site durante uma sessão (conforme fornecido pelo navegador do visitante). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensões de tempo </td> 
   <td colname="col2"> Simples </td> 
   <td colname="col03"> Sessão </td> 
   <td colname="col3"> A hora, o dia, a hora do dia, a semana, o dia da semana, o mês, o trimestre ou o ano em que uma Sessão começou. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensões do Relatório de Tempo </td> 
   <td colname="col2"> Derivado (dimensões LastN e Renomear com base em dimensões de tempo incorporadas) </td> 
   <td colname="col03"> Sessão </td> 
   <td colname="col3"> Dimensões incluindo Dias atrás, Dias do mês passado, Dias da semana passada, Dias deste mês, Dias desta semana, Horas de hoje, Horas de ontem, Últimos 12 meses, Últimos 2 meses, Últimas 2 semanas, Últimas 24 horas, Últimos 3 meses, Últimas 4 semanas, Últimas 6 meses, Últimos 7 dias, Últimos 7 dias e Hoje, Últimas 8 semanas, Últimos 9 meses, Último mês, Última semana, Meses Atrás, Este mês, Esta semana, Este e Últimos 14 dias, Este e Últimos 6 meses, Este e Últimas 8 semanas, Hoje, Hoje, Hoje e Últimos 30 dias, Semanas Atrás e Ontem fornecem uma maneira conveniente de criar um Espaço de Trabalho ou Relatório que sempre mostra uma parte dos dados nos Dados et. Cada uma se baseia em quando uma sessão começou. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Herdado do URI integrado do Dimension </td> 
   <td colname="col03"> Exibição da Página </td> 
   <td colname="col3"> O URI de cada página exibida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições de página do visitante </td> 
   <td colname="col2"> Derivado (MetricDim com base na métrica Exibições de página) </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> O número de exibições de página até o momento para um visitante. Por exemplo, selecionar "3" na dimensão de Exibições de página do visitante selecionaria todos os visitantes com exatamente 3 exibições de página em todas as sessões. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Referenciador do visitante </td> 
   <td colname="col2"> Herdado do Referenciador de dimensão incorporado </td> 
   <td colname="col03"> Visitante </td> 
   <td colname="col3"> O nome de domínio de segundo nível do site que primeiro indicou um Visitante ao site para sua primeira sessão (conforme fornecido pelo navegador do visitante). </td> 
  </tr> 
 </tbody> 
</table>

