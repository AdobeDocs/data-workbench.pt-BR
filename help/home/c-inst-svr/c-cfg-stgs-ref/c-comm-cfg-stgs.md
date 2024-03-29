---
description: Instruções para configurar comunicações para o Insight Server ou o Repetidor.
title: Configurações de comunicações
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# Configurações de comunicações{#communications-configuration-settings}

{{eol}}

Instruções para configurar comunicações para o Insight Server ou o Repetidor.

Complete os parâmetros no seguinte arquivo:

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Antes de modificar qualquer parâmetro não listado nesta tabela, entre em contato com o Adobe.

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
   <td colname="col2"> <p>Localização do <span class="filepath"> Access Control.cfg </span> arquivo. O local padrão é o <span class="filepath"> Controle de acesso </span> na pasta <span class="keyword"> Servidor Insight </span> ou <span class="wintitle"> Repetidor </span> diretório de instalação. </p> <p>Exemplo: <code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Diretório de log de acesso </td> 
   <td colname="col2"> <p>Pasta para a qual deseja mapear os logs de auditoria. </p> <p>Exemplo: <code>Access Log Directory = string: Audit\\</code> </p> <p> <p>Observação: Você pode mapear logs de auditoria para outra unidade local (por exemplo: <span class="filepath"> sequência de caracteres: P:\\Audit\\ </span>), mas não mapeie logs de auditoria para uma unidade de rede. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Detalhe do Log de Acesso </td> 
   <td colname="col2"> Esse parâmetro pode ser definido como verdadeiro ou falso. É usado para ativar e desativar a filtragem de log de auditoria. Para garantir que cada solicitação seja registrada, defina o parâmetro como True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Interface IP </td> 
   <td colname="col2"> <p>Endereço IP a ser usado quando duas placas de rede estiverem disponíveis para acessar duas redes diferentes. </p> <p>Exemplo: <code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <p>Porta não segura (HTTP) na qual <span class="keyword"> Servidor Insight </span> ou <span class="wintitle"> Repetidor </span> escuta. A porta padrão é 80. Inserir um valor de 0 desativa conexões não seguras. </p> <p>Exemplo: <code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cifras SSL </td> 
   <td colname="col2"> Alguns ambientes exigem mais segurança de comunicação do que outros. Se quiser usar um conjunto de cifras SSL específico, você pode especificá-lo com este parâmetro. <p>Exemplo: <code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta SSL </td> 
   <td colname="col2"> <p>Porta segura (via SSL) na qual a variável <span class="keyword"> Servidor Insight </span> ou <span class="wintitle"> Repetidor </span> escuta. A porta padrão é 443. Inserir um valor de 0 desativa as conexões seguras. </p> <p>Exemplo: <span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Cabeçalho para configurações do Servidor de Log. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome do cliente </td> 
   <td colname="col2"> <p>Nome do cliente a ser exibido para clientes não especificados em alertas administrativos, como no exemplo a seguir: </p> <p>"Nenhum dado recebido do sensor XYZ para o cliente 'Não especificado' em 15." </p> <p>Exemplo: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>Usando o exemplo acima, os alertas administrativos para clientes não especificados passam a ter a seguinte redação: </p> <p>"Nenhum dado recebido do sensor XYZ para a ‘EmpresaAB’ do cliente em 15." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Caminho local = string: Logs\\ </p> </td> 
   <td colname="col2"> <p>Pasta na qual deseja armazenar os arquivos de log. </p> <p>Exemplo: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>Para acessar essa pasta no <span class="wintitle"> Gerenciador de arquivos do servidor </span>, o local especificado nesse parâmetro deve corresponder ao local especificado no parâmetro Caminhos de log na variável <span class="filepath"> Log Processing.cfg </span> arquivo. Para obter mais informações sobre como modificar o diretório Logs no <span class="filepath"> Log Processing.cfg </span> consulte o capítulo Arquivo de configuração de processamento de log do <i>Guia de configuração do conjunto de dados</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Caminho local = string: Auditoria\\ </p> </td> 
   <td colname="col2"> <p>Pasta para a qual deseja mapear os logs de auditoria. </p> <p>Exemplo: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Observação:  <p>Você pode mapear logs de auditoria para outra unidade local (por exemplo: <span class="filepath"> sequência de caracteres: P:\\Audit\\ </span>), mas não mapeie logs de auditoria para uma unidade de rede. </p> <p>Para acessar essa pasta no <span class="wintitle"> Gerenciador de arquivos do servidor </span>, o local especificado neste parâmetro deve corresponder ao local que você está no parâmetro Diretório de Log de Acesso neste arquivo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizarServidor: </td> 
   <td colname="col2"> <p>Esse parâmetro se aplica somente a <span class="keyword"> Servidor Insight </span>. </p> <p>Para obter mais informações sobre como especificar o Servidor de normalização centralizado para o seu <span class="keyword"> Servidor Insight </span> cluster, consulte o capítulo Arquivo de configuração de processamento de log do <i>Guia de configuração do conjunto de dados</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Esse parâmetro se aplica somente a <span class="keyword"> Servidor Insight </span>. </p> <p>Permite que você visualize <span class="keyword"> do relatório </span> na interface de Status Detalhado para <span class="keyword"> Servidor Insight </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
