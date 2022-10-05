---
description: O Gerenciador de Arquivos do Servidor permite que você administre e gerencie remotamente os computadores do servidor do Data Workbench de qualquer Data Workbench autorizada fornecendo acesso a todos os diretórios e arquivos no diretório de instalação do produto, incluindo arquivos de configuração e pesquisa.
title: Gerenciador de arquivos do servidor
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 1%

---

# Gerenciador de arquivos do servidor{#server-files-manager}

{{eol}}

O Gerenciador de Arquivos do Servidor permite que você administre e gerencie remotamente os computadores do servidor do Data Workbench de qualquer Data Workbench autorizada fornecendo acesso a todos os diretórios e arquivos no diretório de instalação do produto, incluindo arquivos de configuração e pesquisa.

Você pode acessar o [!DNL Server Files Manager] usando o [!DNL Admin] , bem como clicando com o botão direito do mouse no nó do computador do servidor do Data Workbench no [!DNL Servers Manager] e clicando em **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>Você pode criar novos gerenciadores de arquivos do servidor que exibem os diretórios selecionados. Consulte [Criação de novos gerenciadores de arquivos do servidor](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

A coluna à esquerda de [!DNL Server Files Manager] lista nomes de arquivos e pastas. As marcas de verificação nas colunas central e direita indicam onde esses diretórios e arquivos residem na estrutura do arquivo.

Se um arquivo reside no diretório de instalação do produto, a variável *nome do servidor* (por exemplo, servidor do Data Workbench) contém uma marca de seleção. Se um arquivo residir no computador do usuário do Data Workbench na *Diretório de instalação do Data Workbench*\Diretório Temp, o [!DNL Temp] contém uma marca de seleção. A cor das marcas de verificação indica se os arquivos que residem em locais diferentes foram modificados ao mesmo tempo.

* Uma marca de seleção vermelha na coluna de nome do servidor indica que a pasta ou o arquivo reside no computador do servidor do Data Workbench.
* Uma marca de verificação vermelha na [!DNL Temp] indica que a cópia local do arquivo ou pasta tem a mesma data e hora Modificadas que o arquivo ou pasta no computador do servidor do Data Workbench.
* Uma marca de verificação branca na [!DNL Temp] indica que o arquivo ou a pasta na *Diretório de instalação do Data Workbench*\O diretório Temp tem uma data e hora Modificadas diferentes do arquivo ou pasta no computador do servidor do Data Workbench.

O gráfico a seguir mostra o [!DNL Server Files Manager] com marcas de verificação em vermelho e branco:

![](assets/vis_FileManager_RedWhiteChecks.png)

**Para gerenciar diretórios e arquivos usando o[!DNL Server Files Manager]**

Você pode usar o [!DNL Server Files Manager] para manipular diretórios e arquivos em um computador servidor do Data Workbench.

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
   <td colname="col2"> <p>Clique com o botão direito do mouse na célula ao lado do diretório, no nome do servidor ou <span class="wintitle"> Temp</span> coluna. Você verá as seguintes informações: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Caminho. O caminho do diretório. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir. O nome do diretório. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">De. A localização do diretório, Remoto ou Temporário. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Data (somente na coluna Temp). Data de criação ou data da última revisão para a cópia local. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para ver detalhes sobre um arquivo </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção ao lado do arquivo no nome do servidor ou <span class="wintitle"> Temp</span> coluna. Você verá as seguintes informações: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Caminho. O caminho do arquivo. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">Arquivo. O nome do arquivo. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">De. A localização do diretório, Remoto ou Temporário. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Data. Data da última revisão do arquivo. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Tamanho. O tamanho do arquivo. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para baixar um diretório no computador local </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção no <i>nome do servidor</i> para esse diretório e clique em <span class="uicontrol"> Tornar Diretório Local</span>. Uma marca de verificação para o diretório é exibida no <span class="wintitle"> Temp</span> coluna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para transferir um ficheiro para o computador local </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção no <i>nome do servidor</i> para este arquivo e clique em <span class="uicontrol"> Tornar local</span>. Uma marca de seleção para o arquivo aparece no <span class="wintitle"> Temp</span> coluna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para transferir a última parte de um ficheiro de registro para o computador local </p> </td> 
   <td colname="col2"> <p>Para evitar a necessidade de baixar um arquivo de log inteiro (especialmente quando você sabe que a mensagem de erro está perto do fim do arquivo), clique com o botão direito do mouse na marca de seleção na coluna de nome do servidor do arquivo, clique em <span class="uicontrol"> Cauda</span>e selecione o tamanho da porção que deseja baixar. Uma marca de seleção para o arquivo aparece no <span class="wintitle"> Temp</span> coluna. O arquivo local contém apenas a quantidade de dados especificada, a partir do fim do arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para abrir um diretório </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do diretório na <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Abrir</span> &gt; <span class="uicontrol"> pasta</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para abrir um arquivo </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do arquivo na <span class="wintitle"> Temp</span> coluna, clique em <span class="uicontrol"> Abrir</span>, em seguida, clique em <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> no Bloco de Notas</span>ou <span class="uicontrol"> pasta</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salve uma cópia local de um diretório no servidor do Data Workbench </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do diretório na <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Salvar diretório em</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salve uma cópia local de um arquivo no servidor do Data Workbench </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do arquivo na <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Salvar em</span> &gt; <i>&lt;<span class="uicontrol"> nome do perfil</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Remover uma cópia local de um diretório ou ficheiro </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do diretório ou arquivo na <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Remover</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copie e cole um arquivo como um anexo de email no Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Clique com o botão direito do mouse na marca de seleção do arquivo na <span class="wintitle"> Temp</span> e clique em <span class="uicontrol"> Copiar</span>. No corpo do email, pressione Ctrl+v para anexar o arquivo. </p> </td> 
  </tr> 
 </tbody> 
</table>
