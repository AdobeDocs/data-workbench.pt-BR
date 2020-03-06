---
description: Os exportadores fornecem as instruções para a saída dos dados do evento.
solution: Analytics
title: Definindo Exportadores
topic: Data workbench
uuid: 565d4482-6c25-407c-bda7-0d116180902a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definindo Exportadores{#defining-exporters}

Os exportadores fornecem as instruções para a saída dos dados do evento.

A funcionalidade de transformação fornece três tipos de exportadores para exportar [!DNL .vsl] arquivos, arquivos de registro, arquivos XML e dados ODBC como [!DNL .vsl] arquivos, arquivos de texto ou arquivos de texto delimitados que podem ser usados pelas rotinas de carregamento do DataWarehouse, agências de auditoria ou outros alvos.

>[!NOTE]
>
>Para que um exportador funcione corretamente, a fonte de log deve atender aos requisitos apropriados discutidos na seção Fontes [de](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea) log do Arquivo [de Configuração de Processamento de](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)Log.

**Definição de um exportador**

1. Abrir [!DNL Transform.cfg] na análise de big data. Consulte [Para editar o arquivo](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13)Insight Transform.cfg.
1. Clique com o botão direito do mouse **[!UICONTROL Exporters]** e, em seguida, clique em **[!UICONTROL Add New]**.
1. Selecione uma das seguintes opções:

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**
   >[!NOTE]
   >
   >Para a [!DNL ExportVSLFile] opção, todos os campos estendidos no arquivo de entrada e todos os campos definidos pelo usuário do formulário cs(*cabeçalho*) são sempre gravados no arquivo de saída VSL. Se um campo estendido existente for substituído, o novo valor será gravado no arquivo de saída, mesmo se o campo estiver em branco.

1. Edite os parâmetros Exportadores no arquivo de configuração usando a seguinte tabela como guia:

   <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Parâmetro </th> 
      <th colname="col2" class="entry"> Descrição </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> Formato de dados </td> 
      <td colname="col2"> <p>Somente para <span class="wintitle"> ExportTextFile</span> . O formato de cada linha de saída, que consiste em escape de nome de campo (expresso como %<i>field</i>%) e qualquer outro texto fixo desejado. O formato deve incluir um separador de linha, geralmente [CR] [LF]. </p> <p> Um sinal de porcentagem literal (%) pode ser incorporado na string de formato, escapando do caractere como mostrado aqui: %% </p> <p> Um exemplo de entrada para o parâmetro Formato de dados é <span class="filepath"> %x-timestring% %x-trackingid%[CR][LF]</span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Campos </td> 
      <td colname="col2">Somente para <span class="wintitle"> ExportDelimitedTextFile</span> . Nomes dos campos a serem enviados. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Delimitador </td> 
      <td colname="col2"> <p>Opcional. Somente para <span class="wintitle"> ExportDelimitedTextFile</span> . Caractere usado para separar os campos no arquivo de saída. </p> <p> O software não pode escapar dos delimitadores incluídos nos valores dos dados. Como resultado, a Adobe não recomenda usar vírgulas como delimitadores. </p> <p> Se você pressionar a tecla Ctrl e clicar com o botão direito do mouse no parâmetro Delimitador, um menu <span class="wintitle"> Inserir</span> será exibido. Esse menu contém uma lista de caracteres especiais que são usados com frequência como delimitadores. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Separador de linha </td> 
      <td colname="col2">Opcional. Somente para <span class="wintitle"> ExportDelimitedTextFile</span> . Os caracteres usados para separar linhas nos arquivos de saída. O valor padrão é [CR] [LF]. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Nome </td> 
      <td colname="col2"> <p>Opcional. Identificador do exportador. Esse nome é exibido na interface de Status <span class="wintitle"></span> Detalhado. </p> <p> Para obter informações sobre a interface Status <span class="wintitle"> Detalhado, consulte o Guia</span> do Usuário da Análise de <i></i>big data. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Comentários </td> 
      <td colname="col2"> Opcional. Notas sobre o exportador. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Caminho de saída </td> 
      <td colname="col2"> <p>Caminho onde os arquivos de saída devem ser armazenados. O caminho é relativo à pasta de instalação do servidor da análise de big data. </p> <p> <p>Observação: O servidor de análise de big data que armazena dados de saída está processando o servidor #0 no arquivo <span class="filepath"> profile.cfg</span> . </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Período de rotação do arquivo </td> 
      <td colname="col2"> <p>Opcional. A frequência na qual os dados são exportados para o arquivo de saída. Cada arquivo de saída contém dados relacionados a um período de tempo específico chamado período de rotação. Todos os cálculos de tempo estão em GMT: Um dia começa à meia-noite GMT e termina no dia seguinte à meia-noite GMT, mesmo se os dados gravados no arquivo incluírem um campo que foi transformado para a hora local. </p> <p> Os valores disponíveis são os seguintes: </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> ANO. Cada arquivo contém dados de um ano civil. </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> MÊS. Cada arquivo contém dados de um mês do calendário. Os meses são numerados de 1 (janeiro) a 12 (dezembro). </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> SEMANA. Cada arquivo contém dados de uma semana. Uma semana começa na segunda-feira. A semana que começa em um dos primeiros sete dias do ano é a semana 1 e a semana anterior (parcial), se houver, é a semana 0. </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> DIA. Cada arquivo contém dados de um dia de calendário. </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> HORA. Cada arquivo contém dados por uma hora. </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> NONE. Nenhuma rotação é executada. Todos os dados são gravados no mesmo arquivo (ou em um conjunto de arquivos, conforme determinado por outras configurações de parâmetro). Consulte o parâmetro Formato <span class="wintitle"> de nome de</span> arquivo nesta tabela. </li> 
      </ul> <p>O período padrão de rotação do arquivo é DAY. </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> Defina a rotação do arquivo como NONE somente ao trabalhar no <span class="wintitle"> modo</span>Offline. Consulte a descrição do parâmetro Modo <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13"></a> offline. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Formato do nome do arquivo </td> 
      <td colname="col2"> <p>Opcional. O formato do nome do arquivo de saída. </p> <p> Cada entrada de log pode ser armazenada em um arquivo cujo nome é derivado da hora de início do período de rotação e, opcionalmente, de valores de campos nas linhas que contém. Os campos a serem usados no nome do arquivo são incorporados como escape do nome do campo (expresso como %<i>fieldname</i>%). </p> <p>Os componentes de nome de arquivo relacionados ao período de rotação são incorporados na string de formato usando as seguintes sequências de escape: 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyyy% (ano de quatro dígitos) </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy% (ano com dois dígitos) </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm% (mês com dois dígitos, 01 - 12) </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %ww% (semana de dois dígitos, 01 - 52) </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd% (dia com dois dígitos, 01 - 31) </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH% (hora de dois dígitos, 00 - 23) </li> 
      </ul> </p> <p> O formato de nome de arquivo padrão é <span class="filepath"> %yyyy%%mm%%dd%-%x-mask%.txt</span> </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> As sequências de escape fazem distinção entre maiúsculas e minúsculas. </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> Quando o Período de rotação do arquivo está definido como NONE, uma sequência vazia é substituída por cada uma das sequências de escape, se houver. </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> Um erro é gerado se <span class="wintitle"> o Formato</span> de Nome de Arquivo não resultar em um nome de arquivo exclusivo para cada período de rotação (consulte o parâmetro Período de Rotação de Arquivo nesta tabela). Por exemplo, ao usar o período de rotação DIA, as sequências de escape %dd%, %mm% e %yy% ou %yyyy% devem estar presentes no padrão para evitar perda de dados. </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> Se você estiver usando sequências de escape de nome de campo dentro do padrão e o campo em questão tiver muitos valores distintos, muitos arquivos de saída serão gravados para cada período de rotação. Observe que esse cenário pode resultar em desempenho ruim, portanto, você deve usar esse recurso com cautela. </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> Os cálculos são sempre em GMT. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Executar na rolagem </td> 
      <td colname="col2"> <p>Opcional. Quando cada arquivo é finalizado, um comando externo (Windows) pode ser executado. A linha de comando é derivada do nome de arquivo final, substituindo as seguintes sequências de escape neste parâmetro: </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%. A parte do diretório do nome do arquivo final, incluindo a barra invertida à direita. </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%. O nome do arquivo (excluindo o diretório e a extensão) do arquivo final. </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%. A extensão (incluindo o "." à esquerda) do nome do arquivo final. </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %caminho%. O nome completo do caminho do arquivo, equivalente a %dir%%file%%ext%. </li> 
      </ul> <p> Por padrão, esse parâmetro está vazio (nenhum comando é executado). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Limite de memória </td> 
      <td colname="col2"> <p>Opcional. A quantidade de memória em bytes usada para armazenar a saída do exportador em buffer. O valor padrão é 10.000.000 bytes. </p> <p> <p>Observação:  Se houver muitos arquivos de saída abertos ao mesmo tempo, você pode aumentar esse valor, mas pode diminuir a quantidade de memória disponível para uso por outros componentes do sistema. A diminuição desse valor, no entanto, pode atrasar o processo de exportação. Para obter ajuda, entre em contato com a Adobe. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Limite de arquivos abertos </td> 
      <td colname="col2"> <p>Opcional. O número máximo de ficheiros que podem ser abertos ao mesmo tempo para saída do exportador. Se esse número for excedido, um erro será registrado no log de eventos e o servidor do análise de big data parará de ser executado. O valor padrão é 1000. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Depois de definir seu exportador (e fazer alterações em outros parâmetros) no [!DNL Transform.cfg] arquivo, salve o arquivo localmente e salve-o no perfil apropriado na máquina do servidor da análise de big data.
