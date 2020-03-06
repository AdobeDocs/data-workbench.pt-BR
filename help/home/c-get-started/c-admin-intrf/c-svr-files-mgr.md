---
description: O Gerenciador de Arquivos do Servidor permite que você administre e gerencie remotamente os computadores do servidor do Análise de big data de qualquer Análise de big data autorizada fornecendo acesso a todos os diretórios e arquivos no diretório de instalação do produto, incluindo arquivos de configuração e de pesquisa.
solution: Analytics
title: Gerenciador de arquivos do servidor
topic: Data workbench
uuid: 62625b9d-587f-4a78-8328-2270869909f8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gerenciador de arquivos do servidor{#server-files-manager}

O Gerenciador de Arquivos do Servidor permite que você administre e gerencie remotamente os computadores do servidor do Análise de big data de qualquer Análise de big data autorizada fornecendo acesso a todos os diretórios e arquivos no diretório de instalação do produto, incluindo arquivos de configuração e de pesquisa.

Você pode acessar o [!DNL Server Files Manager] usando o [!DNL Admin] menu e clicando com o botão direito do mouse no nó do computador do servidor do Análise de big data no [!DNL Servers Manager] e clicando em **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>Você pode criar novos gerenciadores de arquivos do servidor que exibem diretórios selecionados. Consulte [Criação de novos gerentes](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816)de arquivos do servidor.

A coluna esquerda de [!DNL Server Files Manager] lista os nomes de arquivos e pastas. As marcas de seleção nas colunas central e direita indicam onde, na estrutura do arquivo, esses diretórios e arquivos residem.

Se um arquivo residir no diretório de instalação do produto, a coluna do nome *do* servidor (por exemplo, servidor do Análise de big data) conterá uma marca de seleção. Se um arquivo residir no computador do usuário da Análise de big data no diretório *de instalação da Análise de big data\Temp, a*[!DNL Temp] coluna conterá uma marca de seleção. A cor das marcas de seleção indica se os arquivos que residem em locais diferentes foram modificados ao mesmo tempo.

* Uma marca de seleção vermelha na coluna de nome do servidor indica que a pasta ou o arquivo reside no computador do servidor da Análise de big data.
* Uma marca de seleção vermelha na [!DNL Temp] coluna indica que a cópia local do arquivo ou pasta tem a mesma data e hora Modificadas que o arquivo ou pasta no computador servidor do Análise de big data.
* Uma marca de seleção em branco na [!DNL Temp] coluna indica que o arquivo ou pasta no diretório ** de instalação da Análise de big data\Temp tem uma data e hora Modificadas diferentes do arquivo ou pasta no computador servidor da Análise de big data.

O gráfico a seguir mostra o [!DNL Server Files Manager] com marcas de seleção em vermelho e branco:

![](assets/vis_FileManager_RedWhiteChecks.png)

**Para gerenciar diretórios e arquivos usando a variável[!DNL Server Files Manager]**

Você pode usar o para manipular diretórios e arquivos [!DNL Server Files Manager] em um computador servidor do Análise de big data.

A tabela a seguir lista as tarefas que podem ser concluídas usando o [!DNL Server Files Manager]:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para executar esta tarefa... </th> 
   <th colname="col2" class="entry"> Ação... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Para ver os arquivos em qualquer diretório </p> </td> 
   <td colname="col2"> <p>Clique no nome do diretório para exibir seu conteúdo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ocultar o conteúdo de um diretório </p> </td> 
   <td colname="col2"> <p>Clique no nome do diretório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver detalhes sobre um diretório </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na célula ao lado do diretório na coluna Nome do servidor ou <span class="wintitle"> Temp</span> . Você verá as seguintes informações: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Caminho. O caminho do diretório. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir. O nome do diretório. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">De. A localização do diretório, Remoto ou Temporário. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Data (somente coluna Temp). Data de criação ou a data da última revisão da cópia local. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver detalhes sobre um arquivo </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção ao lado do arquivo no nome do servidor ou na coluna <span class="wintitle"> Temp</span> . Você verá as seguintes informações: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Caminho. O caminho do arquivo. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">Arquivo. O nome do arquivo. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">De. A localização do diretório, Remoto ou Temporário. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Data. Data da última revisão do arquivo. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Tamanho. O tamanho do arquivo. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para fazer download de um diretório para o computador local </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção na coluna de nome <i>do</i> servidor para este diretório e clique em <span class="uicontrol"> Tornar diretório local</span>. Uma marca de seleção para o diretório é exibida na coluna <span class="wintitle"> Temp</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para baixar um arquivo no computador local </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção na coluna de nome <i>do</i> servidor para este arquivo e clique em <span class="uicontrol"> Tornar local</span>. Uma marca de seleção para o arquivo é exibida na coluna <span class="wintitle"> Temp</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para baixar a última parte de um arquivo de log no computador local </p> </td> 
   <td colname="col2"> <p>Para evitar ter que baixar um arquivo de log inteiro (especialmente quando você sabe que a mensagem de erro está próxima ao final do arquivo), clique com o botão direito do mouse na marca de seleção na coluna de nome do servidor do arquivo, clique em <span class="uicontrol"> Causa</span>e selecione o tamanho da parte que deseja baixar. Uma marca de seleção para o arquivo é exibida na coluna <span class="wintitle"> Temp</span> . O arquivo local contém apenas a quantidade de dados especificada, começando pelo final do arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para abrir um diretório </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do diretório na coluna <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Abrir</span> &gt; <span class="uicontrol"> pasta</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para abrir um arquivo </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do arquivo na coluna <span class="wintitle"> Temp</span> , clique em <span class="uicontrol"> Abrir</span>e, em seguida, clique em <span class="uicontrol"> Análise</span>de big data, <span class="uicontrol"> em Bloco de notas</span>ou <span class="uicontrol"> pasta</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvar uma cópia local de um diretório no servidor da Análise de big data </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do diretório na coluna <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Salvar diretório em</span> &gt; <i>&lt;<span class="uicontrol"> nome</span>do perfil&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvar uma cópia local de um arquivo no servidor da Análise de big data </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do arquivo na coluna <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Salvar em</span> &gt; <i>&lt;<span class="uicontrol"> nome</span>do perfil&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Remover uma cópia local de um diretório ou ficheiro </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do diretório ou arquivo na coluna <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Remover</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copiar e colar um arquivo como anexo de email no Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do arquivo na coluna <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Copiar</span>. No corpo do seu email, pressione Ctrl+v para anexar o arquivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

