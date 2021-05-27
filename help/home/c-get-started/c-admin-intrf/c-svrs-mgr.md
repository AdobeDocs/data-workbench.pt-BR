---
description: A principal ferramenta usada pelos administradores do sistema é o Gerenciador de Servidores.
title: Gerenciador de servidores
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---

# Gerenciador de servidores{#servers-manager}

A principal ferramenta usada pelos administradores do sistema é o Gerenciador de Servidores.

É a principal interface para determinar o status geral do sistema e executar a configuração do sistema, o gerenciamento de arquivos e as funções de monitoramento de erros.

O Gerenciador de Servidores exibe um ponto colorido (nó) para cada servidor do Data Workbench e [!DNL Sensor] instalação em seu sistema e fornece status instantâneo do sistema para cada instalação. Ele também exibe um nó para a instalação do Data Workbench.

Os nós verdes representam conexões ativas, os nós vermelhos representam conexões que estão desativadas ou inacessíveis de outra forma, e os nós cinza representam conexões cujos estados são indeterminados.

![](assets/vis_SysStat_RedGreenDots.png)

Clicar com o botão direito do mouse em um nó exibe informações sobre o componente de conexão e fornece acesso a qualquer menu relacionado.

As tabelas a seguir descrevem as informações fornecidas quando você clica com o botão direito do mouse em um nó para o Data Workbench, o servidor do Data Workbench (incluindo um servidor do Data Workbench principal em um cluster) ou [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Produto </p> </td> 
   <td colname="col2"> <p>Nome do produto, versão e número da compilação. </p> <p>Exemplo: Data Workbench 5.3 (0000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Endereço </p> </td> 
   <td colname="col2"> <p>Endereço IP do computador Data Workbench. </p> <p>Exemplo: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar </p> </td> 
   <td colname="col2"> <p>Um link para o arquivo de configuração <span class="keyword"> da Data Workbench </span>. Clique em <span class="uicontrol"> Configurar </span> &gt; <span class="uicontrol"> Insight.cfg </span> para exibir a janela de configuração da Data Workbench. Todas as alterações feitas e salvas nessa janela são refletidas no arquivo <span class="filepath"> Insight.cfg </span> no diretório de instalação do Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Produto </p> </td> 
   <td colname="col2"> <p>Nome do produto, versão e número da compilação. </p> <p>Exemplo: Data Workbench server 5.3 (00000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NC </p> </td> 
   <td colname="col2"> <p>O nome comum do computador do servidor do Data Workbench. </p> <p>Exemplo: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Endereço </p> </td> 
   <td colname="col2"> <p>Endereço IP ou nome de domínio totalmente qualificado do servidor, conforme configurado no arquivo Endereços no computador e o parâmetro Local da Rede no arquivo <span class="filepath"> Insight.cfg </span> . </p> <p>Exemplo: 100.0.0.1 </p> <p>Para obter informações sobre o arquivo Endereços, consulte o <i>Guia de Instalação e Administração de Produtos do Servidor</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Status atual do servidor do Data Workbench. Este campo exibe OK quando o servidor do Data Workbench está sendo executado normalmente. Se um erro tiver ocorrido e o nó do servidor do Data Workbench estiver vermelho, o campo exibirá o erro (por exemplo, "403 Forbidden"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status detalhado </p> </td> 
   <td colname="col2"> <p>Um link para a interface <span class="keyword"> do servidor do Data Workbench </span> <span class="wintitle"> Status Detalhado </span>, que é útil para solucionar erros ou outros problemas com o servidor do Data Workbench. </p> <p>Para obter mais informações, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> A Interface de Status Detalhada</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Área de Trabalho Remota </p> </td> 
   <td colname="col2"> <p>Abre uma sessão <span class="wintitle"> de Área de Trabalho Remota </span> no computador servidor do Data Workbench. </p> <p>Para obter mais informações, consulte <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> A Opção de Área de Trabalho Remota </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Arquivos do servidor </p> </td> 
   <td colname="col2"> <p>Um link para o <span class="wintitle"> Gerenciador de Arquivos do Servidor </span>, que exibe os diretórios e arquivos no diretório de instalação do servidor do Data Workbench. </p> <p>Para obter mais informações, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> O Gerenciador de Arquivos do Servidor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Monitor de servidor </p> </td> 
   <td colname="col2"> <p>Um link para a interface do <span class="wintitle"> Server Monitor </span>, que é útil para solucionar problemas ou rastrear parâmetros de desempenho. </p> <p>Para obter mais informações, consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> A interface do monitor do servidor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores relacionados </p> </td> 
   <td colname="col2"> <p>Somente para clusters do servidor do Data Workbench. </p> <p>Um menu que lista os nomes comuns dos computadores listados no arquivo *.address </span> do servidor de Data Workbench principal <span class="filepath">. Essa lista geralmente inclui todos os servidores de Data Workbench <span class="keyword"> de processamento </span> no cluster. Esse menu aparece somente se o Data Workbench tiver uma cópia do arquivo *.address </span> do servidor do Data Workbench principal.<span class="filepath"> </span></span></p> <p>Ao clicar em <span class="uicontrol"> Servidores Relacionados </span>, você pode clicar em: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Lista de Monitores do Servidor  </span>, que exibe os detalhes da lista da  <span class="wintitle"> interface do Monitor do  </span> Servidor para todos os servidores relacionados </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">O nome comum de qualquer servidor do Data Workbench, que exibe um menu de contexto que permite abrir qualquer um dos seguintes para esse servidor específico: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Status Detalhado  </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> A Interface de Status Detalhada </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Área de Trabalho Remota  </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> A Opção de Área de Trabalho Remota </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Gerenciador de arquivos do servidor </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> O Gerenciador de Arquivos do Servidor </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Monitor de servidor  </span>. Consulte <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> A interface do monitor do servidor </a>. </li> 
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
   <td colname="col1"> <p>Produto </p> </td> 
   <td colname="col2"> <p>Nome do produto, versão e número da compilação. </p> <p>Exemplo: Sensor 3.76; J3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> A ID <span class="wintitle"> Sensor </span> especificada no arquivo de configuração <span class="wintitle"> Sensor </span> para esta instalação. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>Endereço IP do servidor Web ou de aplicativos no qual o <span class="wintitle"> Sensor </span> está instalado. </p> <p>Exemplo: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>ID do processo atribuída pelo sistema operacional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Se o <span class="wintitle"> Sensor </span> e o servidor do Data Workbench se comunicam usando SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hora </p> </td> 
   <td colname="col2"> <p>Hora (HH:MM:SS) que o <span class="wintitle"> Sensor </span> estabeleceu por último uma conexão com o servidor do Data Workbench. </p> </td> 
  </tr> 
 </tbody> 
</table>
