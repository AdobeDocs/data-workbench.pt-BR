---
description: A área de trabalho é onde você organiza e acessa todos os seus espaços de trabalho e relatórios.
title: Bancadas
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
exl-id: e714ca25-5e94-408a-9d4e-6e1c13e2a3ef
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Bancadas{#worktops}

{{eol}}

A área de trabalho é onde você organiza e acessa todos os seus espaços de trabalho e relatórios.

Na maioria dos casos, a variável [!DNL Worktop] é exibida imediatamente após abrir o Data Workbench. Os recursos da [!DNL Worktop] inclua a barra lateral e a interface com guias. Além disso, a barra lateral permite adicionar visualizações e acessar funções usadas regularmente.

**Bancada**

![](assets/client-wktp.png)

O [!DNL Worktop] também permite criar e salvar espaços de trabalho e relatórios novos e atualizados, bem como publicar espaços de trabalho e relatórios no servidor do Data Workbench para que outras pessoas acessem.

O [!DNL Worktop] a tabela de elementos abaixo descreve cada elemento da variável [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689">
 <tbody>
  <tr>
   <td colname="col1"> Barra lateral </td>
   <td colname="col2"> <p>A barra lateral fornece contexto e controle para espaços de trabalho, bem como conhecimento do estado atual de um espaço de trabalho e acesso a funções usadas regularmente. As seguintes funções estão disponíveis na barra lateral: </p> <p> <b>Conexão:</b> Um indicador de status mostrando o status online. Clique no status da conexão para habilitar ou desabilitar <span class="wintitle"> Trabalhar online</span>. Consulte <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Trabalhar offline e online</a>. </p> <p> <b>Perfil:</b> Um indicador do perfil atual em uso. </p> <p> <b>A partir de: </b>Um indicador de status que mostra a atualização dos dados no conjunto de dados do perfil. Esses dados são baixados e processados no servidor DPU, que só pode ocorrer quando você está trabalhando online. </p> <p> <b>Confiança de Consulta/Amostra:</b> Um indicador da conclusão da consulta. Quando o status consulta 100%, todos os dados são consultados. </p> <p> <b>Adicionar:</b> Permite adicionar visualizações como painéis, legendas e tabelas à barra lateral. Consulte <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> Adicionar visualizações à barra lateral</a>. </p> <p> <b>Opções:</b> Permite reverter para uma configuração anterior da barra lateral e ocultar automaticamente a barra lateral. </p> <p>As configurações da barra lateral são salvas na variável <span class="filepath"> barralateral.vw</span> ao fechar o Data Workbench. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Tabulação e subguia ou subdiretórios suspensos (não exibido) </p> </td>
   <td colname="col2"> <p>Cada guia que aparece no <span class="wintitle"> Trabalho</span> corresponde ao <i>nome do perfil de trabalho</i>\Espaços de trabalho\<i>nome da guia</i> no diretório de instalação do Data Workbench e representa um tipo específico de informações, como Painéis, Atividade, Aquisição, Visitantes e assim por diante. As subpastas na pasta de nome da guia são exibidas como subguias por padrão, mas também como subdiretórios. Consulte <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> Personalização de guias de desktop</a>. </p> <p> <p>Observação: Cada perfil de Data Workbench é fornecido com um conjunto padrão de guias. Como sua implementação pode ser totalmente personalizada, os espaços de trabalho (e, portanto, as guias) que aparecem podem ser diferentes do que está documentado neste guia. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Status do perfil </td>
   <td colname="col2"> Fornece o status da conexão ao servidor do Data Workbench e o nome do perfil carregado no momento. A data e a hora de início dos dados no conjunto de dados do perfil são exibidas abaixo do indicador online. </td>
  </tr>
  <tr>
   <td colname="col1"> Minimizar, Maximizar, Fechar </td>
   <td colname="col2"> Funções padrão do Windows. </td>
  </tr>
  <tr>
   <td colname="col1"> Miniaturas </td>
   <td colname="col2"> <p>Uma miniatura é um instantâneo de um espaço de trabalho que aparece no <span class="wintitle"> Trabalho</span>. Um novo instantâneo é tirado sempre que você salva o espaço de trabalho. As miniaturas permitem identificar rapidamente um espaço de trabalho específico na <span class="wintitle"> Trabalho</span>. </p> <p>Para abrir um espaço de trabalho, clique na miniatura. </p> <p> <p>Observação: Cada perfil de Data Workbench é fornecido com um conjunto padrão de espaços de trabalho. Como sua implementação pode ser totalmente personalizada, os espaços de trabalho (e, portanto, as miniaturas) exibidos podem ser diferentes do documentado neste guia. </p> </p> <p>Para obter mais informações sobre espaços de trabalho, consulte <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> Configuração da barra lateral</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Mensagens de erro </td>
   <td colname="col2"> <p>As mensagens de erro são exibidas em vermelho abaixo do status . Para obter descrições de código de status, consulte <a href="https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>Por exemplo: 403_Proibido. </p> </td>
  </tr>
 </tbody>
</table>
