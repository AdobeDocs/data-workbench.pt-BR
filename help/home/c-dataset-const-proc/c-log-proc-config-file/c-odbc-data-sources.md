---
description: O servidor do Data Workbench (InsightServer64.exe) pode ler dados de eventos de qualquer banco de dados SQL (por exemplo, Oracle ou Microsoft SQL Server) que tenha um driver compatível com ODBC 3.0.
title: Fontes de dados ODBC
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
exl-id: b22b1e27-9b6c-4708-b45c-a9605807689a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 1%

---

# Fontes de dados ODBC{#odbc-data-sources}

O servidor do Data Workbench (InsightServer64.exe) pode ler dados de eventos de qualquer banco de dados SQL (por exemplo, Oracle ou Microsoft SQL Server) que tenha um driver compatível com ODBC 3.0.

O suporte ODBC do servidor do Data Workbench é semelhante ao suporte existente para carregar dados de Sensores ou de arquivos de log gerados por processos externos. No entanto, há algumas considerações e limitações adicionais:

* O suporte ODBC do servidor do Data Workbench é compatível com os recursos de cluster. Os dados são distribuídos entre todos os servidores de processamento e todo o processamento subsequente (incluindo o processamento de consultas) se beneficia totalmente do clustering.
* O suporte a ODBC depende de drivers ODBC de terceiros. Para que o suporte ODBC funcione, esses drivers devem ser configurados na máquina em que o servidor do Data Workbench é executado, usando ferramentas externas à plataforma Adobe. As máquinas do Data Workbench não exigem configuração adicional.
* A tabela ou exibição da qual os dados são carregados deve ter uma coluna ID crescente. Para qualquer linha, o valor nessa coluna (que pode ser uma coluna real na tabela ou qualquer expressão de coluna SQL) não deve diminuir à medida que novas linhas são inseridas no banco de dados. Se essa restrição for violada, os dados serão perdidos. Para obter o desempenho adequado, é necessário um índice nessa expressão de coluna ou coluna.

   >[!NOTE]
   >
   >É possível que várias linhas tenham o mesmo valor na coluna [!DNL Increasing ID]. Uma possibilidade é uma coluna de carimbo de data e hora com precisão menor do que perfeita.

* O servidor do Data Workbench não pode carregar colunas com dados longos (dados acima de um determinado comprimento, conforme determinado pelo aplicativo de banco de dados específico em uso).
* A recuperação de dados de um banco de dados é mais lenta do que lê-los a partir de um arquivo de disco. Os conjuntos de dados que carregam dados de uma fonte ODBC demoram muito mais para serem processados (principalmente ao reprocessar) do que conjuntos de dados de tamanho equivalente cujos dados vêm de Sensores ou outros arquivos de disco.

Para obter informações sobre como reprocessar seus dados, consulte [Reprocessando e Retransformação](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**Para configurar o servidor Insight para ODBC[!DNL event data]**

A configuração do servidor do Data Workbench para carregar dados de um banco de dados SQL requer que você execute primeiro as seguintes etapas em ordem:

1. Instale o software cliente do banco de dados apropriado, incluindo um driver ODBC, na máquina do servidor do Data Workbench na qual o conjunto de dados é processado.

   >[!NOTE]
   >
   >Se você estiver carregando dados de evento ODBC para processamento em um cluster de servidores do Data Workbench, deverá instalar o software cliente do banco de dados em todos os servidores de processamento no cluster. Para obter informações sobre como especificar servidores de processamento em um cluster, consulte o *Server Products Installation and Administration Guide*.

1. Configure uma Fonte de Dados usando o Administrador da Fonte de Dados ODBC para Windows.

   É importante observar que o servidor do Data Workbench (InsightServer64.exe) é executado como um serviço do Windows. Portanto, a Fonte de Dados normalmente deve ser configurada como um DSN de Sistema em vez de um DSN de Usuário para que o servidor do Data Workbench possa usá-la. Você pode encontrar mais informações sobre essa etapa de configuração na documentação do software do seu banco de dados.

Depois de instalar o software cliente do banco de dados na máquina do servidor do Data Workbench apropriada, você pode configurar o conjunto de dados para usar a fonte de dados ODBC editando os parâmetros apropriados no arquivo de configuração [!DNL Log Processing] para o perfil desejado.

## Parâmetros {#section-15c0218d93364693a565f2609a12f73e}

Para dados de bancos de dados que usam o padrão Open Database Connectivity (ODBC), os seguintes parâmetros estão disponíveis:

<table id="table_606D8A90DA4A43C29F2C6130F8C753F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> O identificador da fonte ODBC. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome da fonte de dados </td> 
   <td colname="col2"> Um DSN, conforme fornecido por um administrador da máquina do servidor do Data Workbench em que o conjunto de dados é processado, que se refere ao banco de dados do qual os dados devem ser carregados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Senha do banco de dados </td> 
   <td colname="col2"> A senha a ser usada na conexão com o banco de dados. Se uma senha tiver sido configurada para o DSN no <span class="wintitle"> Data Source Administrator</span>, isso pode ser deixado em branco. Qualquer senha fornecida aqui substitui a senha configurada para o DSN no <span class="wintitle"> Data Source Administrator</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de usuário do banco de dados </td> 
   <td colname="col2"> A ID de usuário a ser usada ao se conectar ao banco de dados. Se uma ID de usuário tiver sido configurada para o DSN no <span class="wintitle"> Administrador da Fonte de Dados</span>, isso pode ser deixado em branco. Qualquer ID de usuário fornecida aqui substitui a ID de usuário configurada para o DSN no <span class="wintitle"> Administrador da Fonte de Dados</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campos </td> 
   <td colname="col2"> Um vetor de objetos de coluna que especifica um mapeamento de colunas de dados no banco de dados para campos de dados no mecanismo de execução do servidor do Data Workbench. Cada coluna tem entradas <span class="wintitle"> Nome da Coluna</span> e <span class="wintitle"> Nome do Campo</span>. <span class="wintitle"> O </span> Nome da Coluna é uma expressão da coluna SQL que deve ser válida no contexto da tabela identificada pelo  <span class="wintitle"> Identificador da </span> Tabela descrito acima. Pode ser um nome de coluna ou qualquer expressão SQL com base em qualquer número de colunas na tabela. Uma função de formatação pode ser necessária para converter valores de determinados tipos de dados em strings de uma maneira que não perca precisão. Todos os dados são convertidos implicitamente em strings usando o método de formatação padrão do banco de dados, o que pode causar perda de dados para alguns tipos de dados de coluna (como tipos de dados de data/hora) se expressões de formatação explícitas não forem usadas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aumento da coluna ID </td> 
   <td colname="col2"> <p>Um nome de coluna ou expressão de coluna SQL que atende ao critério que aumenta (ou pelo menos não diminui) à medida que novas linhas são adicionadas. Ou seja, se a Linha B for adicionada à tabela em um momento posterior à Linha A, o valor dessa coluna (ou expressão da coluna) na Linha B deve ser maior (de acordo com a ordem de classificação nativa do banco de dados) do que o valor correspondente na Linha A. </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> O nome <span class="wintitle"> Aumentando a coluna de ID </span>pode ser o mesmo que o nome de uma coluna existente, mas não é necessário. </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> Pressupõe-se que essa expressão tenha um tipo de dados de caractere SQL. Se a coluna ID que está aumentando for de algum outro tipo de dados, esse valor deve ser uma expressão de coluna para convertê-la em uma string. Como isso geralmente significa que as comparações são lexicográficas (caractere por caractere), é importante formatar o valor cuidadosamente. </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> A expressão é usada nas cláusulas ORDER BY do SQL e comparada com as cláusulas WHERE do SQL. É extremamente importante ter um índice criado na expressão exata da coluna usada. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID da Fonte de Log </td> 
   <td colname="col2"> <p>O valor desse parâmetro pode ser qualquer string. Se um valor for especificado, esse parâmetro permitirá diferenciar entradas de log de diferentes fontes de log para identificação de origem ou processamento direcionado. O campo x-log-source-id é preenchido com um valor que identifica a origem do log para cada entrada de log. Por exemplo, se você deseja identificar entradas de log de uma fonte ODBC chamada ODBCSource01, você pode digitar <span class="filepath"> de ODBCSource01.</span> e essa string seria passada para o campo x-log-source-id para cada entrada de log dessa fonte. </p> <p> Para obter informações sobre o campo x-log-source-id, consulte <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> Campos de registro de dados do evento</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Executar no servidor </td> 
   <td colname="col2"> Valor de índice no arquivo <span class="filepath"> profile.cfg</span> do servidor de processamento que faz as consultas ODBC para obter dados do banco de dados. (O parâmetro Servidores de processamento no arquivo <span class="filepath"> profile.cfg</span> lista todos os servidores de processamento do conjunto de dados, e cada servidor tem um valor de índice, sendo o primeiro 0.) O valor padrão é 0. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Identificador de tabela </td> 
   <td colname="col2"> Uma expressão SQL que nomeia a tabela ou exibição da qual os dados devem ser carregados. Um identificador de tabela típico é do formulário SCHEMA.TABLE. </td> 
  </tr> 
 </tbody> 
</table>

Este exemplo mostra a janela de configuração [!DNL Log Processing] no Data Workbench com uma fonte de dados ODBC. Essa Fonte de Dados pega dados de uma tabela chamada [!DNL VISUAL.VSL] em um banco de dados com [!DNL Data Source Name] &quot;VSTestO&quot;. Cinco (5) objetos de coluna ( [!DNL Fields]) mapeiam dados das colunas de dados no banco de dados para o servidor do Data Workbench.

![](assets/cfg_LogProcessing_LogSources_ODBC.png)
