---
description: A principal ferramenta usada pelos administradores do sistema é o Gerenciador de servidores.
solution: Analytics
title: Gerenciador de servidores
topic: Data workbench
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Gerenciador de servidores{#servers-manager}

A principal ferramenta usada pelos administradores do sistema é o Gerenciador de servidores.

É a principal interface para determinar o status geral do sistema e para executar as funções de configuração do sistema, gerenciamento de arquivos e monitoramento de erros.

O Gerenciador de Servidores exibe um ponto colorido (nó) para cada servidor e [!DNL Sensor] instalação da Análise de big data no sistema e fornece um status de sistema rápido para cada instalação. Ele também exibe um nó para a instalação do Análise de big data.

Os nós verdes representam conexões ativas, os nós vermelhos representam conexões que estão desativadas ou inacessíveis de outra forma, e os nós cinza representam conexões cujos estados são indeterminados.

![](assets/vis_SysStat_RedGreenDots.png)

Clicar com o botão direito do mouse em um nó exibe informações sobre o componente de conexão e fornece acesso a qualquer menu relacionado.

As tabelas a seguir descrevem as informações fornecidas quando você clica com o botão direito do mouse em um nó para a Análise de big data, servidor da Análise de big data (incluindo um servidor mestre da Análise de big data em um cluster) ou [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Nome do produto, versão e número da compilação. </p> <p>Exemplo: Análise de big data 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Endereço </p> </td> 
   <td colname="col2"> <p>Endereço IP do computador da Análise de big data. </p> <p>Exemplo: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar </p> </td> 
   <td colname="col2"> <p>Um link para o arquivo de configuração <span class="keyword"> do Análise de big data </span> . Clique em <span class="uicontrol"> Configurar </span> &gt; <span class="uicontrol"> Insight.cfg </span> para exibir a janela de configuração da Análise de big data. Quaisquer alterações feitas e salvas nessa janela serão refletidas no arquivo <span class="filepath"> Insight.cfg </span> no diretório de instalação do Análise de big data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Nome do produto, versão e número da compilação. </p> <p>Exemplo: Servidor Análise de big data 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NC </p> </td> 
   <td colname="col2"> <p>O nome comum do computador do servidor da Análise de big data. </p> <p>Exemplo: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Endereço </p> </td> 
   <td colname="col2"> <p>Endereço IP ou nome de domínio totalmente qualificado do servidor conforme configurado no arquivo Endereços no computador e o parâmetro Local de rede no arquivo <span class="filepath"> Insight.cfg </span> . </p> <p>Exemplo: 100.0.0.1 </p> <p>Para obter informações sobre o arquivo Endereços, consulte o Guia <i>de Instalação e Administração de Produtos para</i>Servidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Status atual do servidor da Análise de big data. Este campo exibe OK quando o servidor da Análise de big data está sendo executado normalmente. Se um erro tiver ocorrido e o nó do servidor do Análise de big data estiver vermelho, o campo exibirá o erro (por exemplo, "403 Proibido"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status detalhado </p> </td> 
   <td colname="col2"> <p>Um link para a interface <span class="keyword"> de Status detalhado do servidor da Análise de big data, </span> <span class="wintitle"> </span> que é útil para solucionar erros ou outros problemas com o servidor da Análise de big data. </p> <p>Para obter mais informações, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> A interface</a>de status detalhada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ambiente de Trabalho Remoto </p> </td> 
   <td colname="col2"> <p>Abre uma <span class="wintitle"> sessão de Área de Trabalho Remota </span> para o computador servidor Análise de big data. </p> <p>Para obter mais informações, consulte <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> a opção Área de trabalho remota </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Arquivos do servidor </p> </td> 
   <td colname="col2"> <p>Um link para o Gerenciador de Arquivos do <span class="wintitle"> Servidor </span>, que exibe os diretórios e arquivos no diretório de instalação do servidor do Análise de big data. </p> <p>Para obter mais informações, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> O Gerenciador de Arquivos do Servidor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Monitor do servidor </p> </td> 
   <td colname="col2"> <p>Um link para a interface do Monitor de <span class="wintitle"> </span> servidor, que é útil para solucionar problemas ou rastrear parâmetros de desempenho. </p> <p>Para obter mais informações, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> A interface do monitor do servidor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores relacionados </p> </td> 
   <td colname="col2"> <p>Somente para clusters de servidores do Análise de big data. </p> <p>Um menu que lista os nomes comuns dos computadores listados no arquivo *.address do servidor <span class="filepath"> da Análise de big data principal </span> . Essa lista geralmente inclui todos os servidores de processamento da Análise de big data <span class="keyword"> </span> no cluster. Esse menu será exibido somente se a Análise de big data tiver uma cópia do arquivo *.address do servidor <span class="filepath"> mestre da Análise de big data </span> . </p> <p>Ao clicar em Servidores <span class="uicontrol"> relacionados </span>, você pode clicar em: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Lista de monitores de servidor </span>, que exibe os detalhes da lista da interface do Monitor de <span class="wintitle"> </span> servidor para todos os servidores relacionados </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">O nome comum de qualquer servidor da Análise de big data, que exibe um menu de contexto que permite abrir qualquer um dos seguintes para esse servidor específico: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Status detalhado </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> A Interface Detalhada Do Status </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Área de trabalho remota </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> A Opção Área De Trabalho Remota </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Gerenciador de arquivos do servidor </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> O Gerenciador De Arquivos Do Servidor </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Monitor do servidor </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> A Interface Do Monitor De Servidor </a>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Product </p> </td> 
   <td colname="col2"> <p>Nome do produto, versão e número da compilação. </p> <p>Exemplo: Sensor 3.76; J3,67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> A ID do <span class="wintitle"> sensor </span> especificada no arquivo de configuração do <span class="wintitle"> Sensor </span> para esta instalação. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>Endereço IP do servidor da Web ou de aplicativos no qual o <span class="wintitle"> Sensor </span> está instalado. </p> <p>Exemplo: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>ID do processo atribuída pelo sistema operacional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Se o <span class="wintitle"> Sensor </span> e o servidor da Análise de big data se comunicam usando SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hora </p> </td> 
   <td colname="col2"> <p>Hora (HH:MM:SS) que o <span class="wintitle"> Sensor estabeleceu </span> pela última vez uma conexão com o servidor da Análise de big data. </p> </td> 
  </tr> 
 </tbody> 
</table>
