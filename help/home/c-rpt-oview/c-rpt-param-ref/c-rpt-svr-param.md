---
description: Informações sobre os parâmetros Report Server.cfg.
title: Parâmetros do Report Server.cfg
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# Parâmetros do Report Server.cfg{#report-server-cfg-parameters}

{{eol}}

Informações sobre os parâmetros Report Server.cfg.

A amostra [!DNL Report Server.cfg] mostrado em [Configuração da conexão com o servidor Insight](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) contém apenas os parâmetros incluídos no [!DNL Report Server.cfg] por padrão.

Se você entrar em contato com o Adobe License Server por meio de um servidor proxy, será necessário adicionar o vetor de Licenciamento e seus parâmetros ao [!DNL Report Server.cfg]. A seguir, um exemplo desse vetor e seus parâmetros que você pode usar em um modelo para seu vetor de Licenciamento:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

A tabela a seguir fornece descrições do [!DNL Report Server.cfg] parâmetros de arquivo:

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Extensão do Excel </td> 
   <td colname="col2"> <p>As extensões compatíveis do Excel incluem: </p> <p>Extensão do Excel = string: <span class="filepath"> .xlsx </span> </p> <p>Extensão do Excel = string: <span class="filepath"> .xls </span> (esse é o padrão) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fontes </td> 
   <td colname="col2"> <p>Opcional. Vetor que lista as fontes que <span class="keyword"> Servidor de relatórios </span> deve usar para renderizar caracteres especiais unicode baseados em UTF8. O número de fontes na lista é ilimitado. </p> <p>A primeira fonte deve ser sempre o Console do Lucida Sans. Se esse parâmetro não for incluído na variável <span class="filepath"> Report Server.cfg </span> arquivo, <span class="keyword"> Servidor de relatórios </span> O usa somente o console Lucida Sans para exibir o texto. </p> <p> <span class="keyword"> Servidor de relatórios </span> O usa a primeira fonte da lista para renderizar todos os caracteres até encontrar um caractere que não possa ser renderizado. Em seguida, usa a segunda fonte na lista para renderizar esse caractere. Se essa fonte não renderizar o caractere, <span class="keyword"> Servidor de relatórios </span> O usa a terceira fonte da lista para renderizar esse caractere e assim por diante, até atingir o fim da lista de fontes. Se a fonte correta não estiver listada no vetor, <span class="keyword"> Servidor de relatórios </span> exibe o valor hexadecimal do caractere. </p> <p> <p>Observação: Não faça alterações nesse parâmetro enquanto <span class="keyword"> Servidor de relatórios </span> está em execução. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gama </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gama </span> definição de <span class="filepath"> .png </span> saída do arquivo. O valor padrão é 1.6. </p> <p> <p>Observação: O Adobe não recomenda alterar esse valor. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licenciamento </td> 
   <td colname="col2"> <p>Opcional. Você precisa modificar os parâmetros deste vetor somente se entrar em contato com o servidor de licenças do Adobe por meio de um servidor proxy. </p> <p>Identificador de seção definido para entrar em contato com o servidor de licenças do Adobe por meio de um servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço Proxy </td> 
   <td colname="col2"> O endereço de um servidor proxy que <span class="keyword"> Servidor de relatórios </span> deve ser usado para acessar o servidor de licença do Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Senha do Proxy </td> 
   <td colname="col2"> Opcional. A senha associada à <span class="wintitle"> Nome de usuário proxy </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta de Proxy </td> 
   <td colname="col2"> A porta do servidor proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome de usuário proxy </td> 
   <td colname="col2"> Opcional. O nome de usuário usado para acessar o servidor proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Local da rede </td> 
   <td colname="col2"> O local de rede que <span class="keyword"> Servidor de relatórios </span> O usa para resolver o nome comum do servidor para um endereço IP. Os locais de rede são definidos no arquivo de endereço localizado no diretório Endereços na máquina do servidor do Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidores </td> 
   <td colname="col2"> <p>Identificador de seção para parâmetros definidos por você para configurar quais máquinas do servidor do Data Workbench <span class="keyword"> Servidor de relatórios </span> deve se conectar para gerar relatórios. Isso inclui um número que indica quantos itens estão listados nesse vetor. </p> <p>Para cada servidor, adicione uma entrada serverInfo e complete os parâmetros conforme necessário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço </td> 
   <td colname="col2"> Endereço IP da máquina do servidor do Data Workbench para a qual <span class="keyword"> Servidor de relatórios </span> deve se conectar para gerar relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> O nome que <span class="keyword"> Servidor de relatórios </span> O usa internamente para identificar o servidor do Data Workbench. Este é apenas um rótulo interno, portanto, você pode usar qualquer nome que desejar. Para fins de consistência, sugerimos que você use o nome comum, conforme listado no certificado digital do servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Porto através do qual <span class="keyword"> Servidor de relatórios </span> se comunica com o servidor do Data Workbench. Para conexões seguras, esse valor geralmente é 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço Proxy </td> 
   <td colname="col2"> O endereço de um servidor proxy que <span class="keyword"> Servidor de relatórios </span> deve usar para acessar o servidor do Data Workbench. Esse parâmetro é necessário somente quando um servidor proxy é necessário para se conectar às máquinas do servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Senha do Proxy </td> 
   <td colname="col2"> A senha para o servidor proxy. Esse parâmetro é necessário somente quando um servidor proxy é necessário para se conectar às máquinas do servidor do Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta de Proxy </td> 
   <td colname="col2"> A porta do servidor proxy. O valor padrão é 8080. Esse parâmetro é necessário somente quando um servidor proxy é necessário para se conectar às máquinas do servidor do Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome de usuário proxy </td> 
   <td colname="col2"> O nome de usuário para o servidor proxy. Esse parâmetro é necessário somente quando um servidor proxy é necessário para se conectar às máquinas do servidor do Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificado de cliente SSL </td> 
   <td colname="col2"> Nome do arquivo de certificado SSL para o <span class="keyword"> Servidor de relatórios </span> máquina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome comum do servidor SSL </td> 
   <td colname="col2"> <span class="wintitle"> Nome comum do servidor </span> listado no certificado digital do servidor do Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar SSL </td> 
   <td colname="col2"> Indica se o SSL é usado para comunicação segura entre o servidor do Data Workbench e o <span class="keyword"> Servidor de relatórios </span>. As opções são true ou false. O valor padrão é true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de Memória de Resultado (KB) </td> 
   <td colname="col2"> <p>A quantidade de memória (em KB) que você deseja disponibilizar para relatórios e alertas. O valor padrão é 50000. </p> <p>Ao executar relatórios, <span class="keyword"> Servidor de relatórios </span> verifica esse valor primeiro e, em seguida, verifica o valor no parâmetro Tamanho máximo da fatia . Por exemplo, se você definir esse parâmetro como 50.000 e o Tamanho máximo da fatia como 50, <span class="keyword"> Servidor de relatórios </span> O executa apenas 50 espaços de trabalho por vez, mesmo se o espaço estiver disponível para executar mais espaços de trabalho. </p> <p> <p>Observação: Esse limite nunca deve exceder o valor definido no parâmetro de Limite de Memória de Consulta do servidor do Data Workbench e, idealmente, deve ser definido um pouco abaixo do valor de <span class="wintitle"> Limite de Memória de Consulta </span> para fornecer algum espaço para outros usuários que podem estar executando relatórios ao mesmo tempo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tamanho máximo da fatia </td> 
   <td colname="col2"> O número máximo de espaços de trabalho do relatório que <span class="keyword"> Servidor de relatórios </span> pode ser executado de uma vez. O valor padrão é 50. Para obter mais informações sobre como <span class="keyword"> Servidor de relatórios </span> usa essa configuração, consulte o <span class="wintitle"> Limite de Memória de Resultado (KB) </span> descrição do parâmetro. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Atualizar software </td> 
   <td colname="col2"> <p>Indica se deve ser permitido <span class="keyword"> do servidor de relatórios </span> software a ser atualizado pelo servidor do Data Workbench. As opções são true ou false. O valor padrão é true. </p> <p>Este é um exemplo desse parâmetro que você pode usar em um modelo: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar a renderização de hardware OpenGL </td> 
   <td colname="col2"> <p>Controla se <span class="keyword"> Servidor de relatórios </span> O usa a renderização de hardware (como a placa gráfica da máquina) para produzir a saída do relatório. As opções são true ou false. O valor padrão é true. </p> <p>Esse parâmetro deve ser definido como false somente quando você tiver problemas com a placa gráfica. Quando definido como falso, <span class="keyword"> Servidor de relatórios </span> O não tenta usar a renderização de hardware e usa a renderização de software por padrão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Relatórios </td> 
   <td colname="col2"> Identificador de seção para parâmetros definidos para configurar relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de Mensagem de Conclusão </td> 
   <td colname="col2"> <p>A frequência (em segundos) com a qual <span class="keyword"> Servidor de relatórios </span> imprime mensagens de status de conclusão quando as consultas estão sendo executadas durante a geração de relatórios ou alertas. O valor padrão é de 120 segundos. </p> <p>Exemplo: As consultas do Workspace são 62,145672% concluídas. </p> <p>As mensagens de conclusão são gravadas no <span class="filepath"> reportserver.log </span> e são sincronizados com o servidor. Essa configuração controla o <span class="filepath"> status.txt </span> arquivos enviados para frente e para trás para cada conjunto de relatórios, de modo que a porcentagem de conclusão possa ser mostrada com miniaturas. As mensagens são enviadas sempre que um conjunto de relatórios é concluído ou quando o intervalo é atingido, o que ocorrer primeiro. Definir esse valor mais alto não afeta a taxa na qual você vê o relatório gerado na interface do cliente pelas miniaturas, mas afeta quantas mensagens temporárias você vê. Especificar um valor baixo pode fazer com que o sistema gaste uma grande quantidade de tempo sincronizando dados, pois os dados são sincronizados de <span class="keyword"> Servidor de relatórios </span> para o perfil, em todas as DPUs e para todos os clientes conectados sempre que uma <span class="filepath"> status.txt </span> alterações na mensagem. </p> <p>O sistema sempre envia um <span class="filepath"> status.txt </span> quando um conjunto de relatórios é concluído, independentemente da configuração desse parâmetro de configuração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perfis </td> 
   <td colname="col2"> <p>Número que indica quantos itens estão listados nesse vetor. Para cada perfil para o qual os relatórios devem ser criados, adicione uma <span class="wintitle"> ReportProfile </span> no vetor Perfis e preencha os parâmetros Servidor e Perfil. </p> <p> <span class="wintitle"> Servidor </span> - O nome que <span class="keyword"> Servidor de relatórios </span> O usa internamente para identificar o servidor do Data Workbench. Esse nome deve ser o nome comum do servidor listado no certificado SSL do servidor do Data Workbench. </p> <p> <span class="wintitle"> Perfil </span> - Nome do perfil para o qual os relatórios devem ser criados. Esse nome deve corresponder ao perfil nomeado na máquina do servidor do Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para erros </td> 
   <td colname="col2"> <p>O endereço do servidor SMTP do qual você deseja enviar <span class="wintitle"> Servidor de relatórios </span> erros por email. </p> <p>Exemplo: <span class="filepath"> mail.mycompany.com </span> </p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para senha de erros </td> 
   <td colname="col2"> <p>A senha para fazer logon no servidor SMTP. Esse parâmetro é opcional, a menos que o logon seja necessário para enviar emails. </p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para envio de erros </td> 
   <td colname="col2"> O endereço de email do qual você deseja enviar <span class="wintitle"> Servidor de relatórios </span> erros. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para Erros Enviados para </td> 
   <td colname="col2"> <p>Os endereços de email para os quais os alertas são enviados. </p> <p>Exemplo: <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para nome de usuário de erros </td> 
   <td colname="col2"> <p>O nome de usuário para fazer logon no servidor SMTP. Esse parâmetro é opcional, a menos que o logon seja necessário para enviar emails. </p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de Status </td> 
   <td colname="col2"> <p>A frequência (em segundos) com a qual <span class="wintitle"> Servidor de relatórios </span> gera e envia informações de status para o servidor do Data Workbench a ser exibido em <span class="wintitle"> Status detalhado </span>. </p> <p>O valor padrão é de 120 segundos. Não é recomendável definir esse valor como um valor pequeno, como dois minutos, pois uma fila de relatórios pode levar horas para ser executada. Nesse caso, você pode considerar uma configuração de 600 a 1200 segundos. </p> <p>Para obter mais informações sobre <span class="wintitle"> Status detalhado </span>, consulte o capítulo Interfaces administrativas do <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Guia do usuário do Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de atualização </td> 
   <td colname="col2"> <p>A frequência (em minutos) com a qual <span class="keyword"> Servidor de relatórios </span> monitora todos os perfis listados no vetor Perfis para obter novos relatórios e alertas. O valor padrão é de 10 minutos. </p> <p>O tempo especificado é dividido entre todos os perfis listados. Por exemplo, se o intervalo estiver definido como 10 minutos e você estiver monitorando dois perfis, cada perfil será monitorado por 5 minutos. Se um perfil estiver sendo monitorado quando um relatório ou alerta novo ou modificado for salvo no perfil, o relatório ou alerta será disponibilizado imediatamente para geração. </p> <p>Se a variável <span class="wintitle"> Intervalo de atualização </span> estiver configurada para monitorar mais de um perfil, é importante que essa configuração seja alta o suficiente para carregar todos os perfis dentro do tempo configurado. Em sistemas com muitas dimensões grandes configuradas, por exemplo, onde pode levar vários minutos para recuperar a conexão de dados inicial com todos os nomes de elemento, essa configuração deve ser longa o suficiente para que ocorra a sincronização completa. Caso contrário, o sistema emitirá um erro de sincronização de perfil. </p> </td> 
  </tr> 
 </tbody> 
</table>
