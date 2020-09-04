---
description: Instruções para configurar comunicações para o Insight Server ou o Repeater.
solution: Insight
title: Configurações de comunicações
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
translation-type: tm+mt
source-git-commit: 638eca495223fc9d5326bf9462a9c289d6fe2d9e
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---


# Configurações de comunicações{#communications-configuration-settings}

Instruções para configurar comunicações para o Insight Server ou o Repeater.

Preencha os parâmetros no seguinte arquivo:

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Antes de modificar quaisquer parâmetros não listados nesta tabela, entre em contato com o Adobe.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Arquivo de controle de acesso </td> 
   <td colname="col2"> <p>Localização do arquivo <span class="filepath"> Controle de acesso.cfg </span> . O local padrão é a pasta <span class="filepath"> Controle de acesso </span> no diretório de instalação do <span class="keyword"> Insight Server </span> ou do <span class="wintitle"> Repeater </span> . </p> <p>Exemplo: <code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Diretório de log de acesso </td> 
   <td colname="col2"> <p>Pasta para a qual deseja mapear os logs de auditoria. </p> <p>Exemplo: <code>Access Log Directory = string: Audit\\</code> </p> <p> <p>Observação:  Você pode mapear logs de auditoria para outra unidade local (por exemplo: <span class="filepath"> string: P:\\Audit\\ </span>), mas não mapeie registros de auditoria para uma unidade de rede. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log de acesso detalhado </td> 
   <td colname="col2"> Esse parâmetro pode ser definido como true ou false. É usado para ativar e desativar a filtragem de log de auditoria. Para garantir que cada solicitação seja registrada, defina o parâmetro como Verdadeiro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interface IP </td> 
   <td colname="col2"> <p>Endereço IP a ser usado quando duas placas de rede estiverem disponíveis para acessar duas redes diferentes. </p> <p>Exemplo: <code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta </td> 
   <td colname="col2"> <p>Porta não segura (HTTP) na qual o <span class="keyword"> Insight Server </span> ou o <span class="wintitle"> Repeater </span> escuta. A porta padrão é 80. Digitar um valor de 0 desativa conexões não seguras. </p> <p>Exemplo: <code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ciphers SSL </td> 
   <td colname="col2"> Alguns ambientes exigem mais segurança de comunicação do que outros. Se quiser usar um conjunto de criptografia SSL específico, você pode especificá-lo com este parâmetro. <p>Exemplo: <code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta SSL </td> 
   <td colname="col2"> <p>Porta segura (via SSL) na qual o <span class="keyword"> Insight Server </span> ou o <span class="wintitle"> Repeater </span> escuta. A porta padrão é 443. Digitar um valor de 0 desativa conexões seguras. </p> <p>Exemplo: <span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Cabeçalho para Configurações do servidor de registro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome do cliente </td> 
   <td colname="col2"> <p>O nome do cliente a ser exibido para clientes não especificados em alertas administrativos, como no exemplo a seguir: </p> <p>"Nenhum dado recebido do sensor XYZ para o cliente 'Não especificado' em 15." </p> <p>Exemplo: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>Usando o exemplo acima, os alertas administrativos para clientes não especificados passam a ter a seguinte redação: </p> <p>"Nenhum dado recebido do sensor XYZ para o cliente ‘CompanyAB’ em 15." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Caminho local = string: Logs\\ </p> </td> 
   <td colname="col2"> <p>Pasta na qual deseja armazenar os arquivos de log. </p> <p>Exemplo: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Para poder acessar essa pasta pelo Gerenciador de Arquivos do <span class="wintitle"> Servidor </span>, o local especificado neste parâmetro deve corresponder ao local especificado no parâmetro Caminhos do Log no arquivo <span class="filepath"> Log Processing.cfg </span> . Para obter mais informações sobre como modificar o diretório Logs no arquivo <span class="filepath"> Log Processing.cfg </span> , consulte o capítulo Log Processing Configuration File do <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Caminho local = string: Auditoria\\ </p> </td> 
   <td colname="col2"> <p>Pasta para a qual deseja mapear os logs de auditoria. </p> <p>Exemplo: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Observação:  <p>Você pode mapear logs de auditoria para outra unidade local (por exemplo: <span class="filepath"> string: P:\\Audit\\ </span>), mas não mapeie registros de auditoria para uma unidade de rede. </p> <p>Para poder acessar esta pasta a partir do Gerenciador de Arquivos do <span class="wintitle"> Servidor </span>, o local especificado neste parâmetro deve corresponder ao local no parâmetro Diretório de Log de Acesso neste arquivo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>Este parâmetro se aplica somente ao <span class="keyword"> Insight Server </span>. </p> <p>Para obter mais informações sobre como especificar o Servidor de Normalização Centralizada para o seu cluster do <span class="keyword"> Insight Server </span> , consulte o capítulo Arquivo de Configuração de Processamento de Log do Guia <i>de Configuração de</i>Conjunto de Dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Este parâmetro se aplica somente ao <span class="keyword"> Insight Server </span>. </p> <p>Permite que você visualização o <span class="keyword"> status do Relatório na interface de Status Detalhado do </span> Insight Server <span class="keyword"> </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
