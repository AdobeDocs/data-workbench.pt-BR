---
description: Informações sobre os parâmetros Report Server.cfg.
solution: Analytics
title: Parâmetros do Report Server.cfg
topic: Data workbench
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Parâmetros do Report Server.cfg{#report-server-cfg-parameters}

Informações sobre os parâmetros Report Server.cfg.

A amostra [!DNL Report Server.cfg] mostrada em [Configuração da conexão com o Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) contém apenas os parâmetros incluídos no [!DNL Report Server.cfg] arquivo por padrão.

Se você entrar em contato com o Adobe License Server por meio de um servidor proxy, precisará adicionar o vetor de licenciamento e seus parâmetros ao [!DNL Report Server.cfg]. Veja a seguir um exemplo desse vetor e seus parâmetros que você pode usar como modelo para seu vetor de Licenciamento:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

A tabela a seguir fornece descrições dos parâmetros do [!DNL Report Server.cfg] arquivo:

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
   <td colname="col2"> <p>As extensões suportadas do Excel incluem: </p> <p>Extensão do Excel = cadeia de caracteres: <span class="filepath"> .xlsx </span> </p> <p>Extensão do Excel = cadeia de caracteres: <span class="filepath"> .xls </span> (este é o padrão) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fontes </td> 
   <td colname="col2"> <p>Opcional. Vetor que lista as fontes que <span class="keyword"> o Servidor de relatórios </span> deve usar para renderizar caracteres especiais unicode baseados em UTF8. O número de fontes na lista é ilimitado. </p> <p>A primeira fonte deve ser sempre o Console Lucida Sans. Se esse parâmetro não estiver incluído no <span class="filepath"> arquivo Report Server.cfg </span> , <span class="keyword"> o Servidor de relatórios </span> usará somente o console Lucida Sans para exibir o texto. </p> <p> <span class="keyword"> O Servidor de relatórios </span> usa a primeira fonte da lista para renderizar todos os caracteres até encontrar um caractere que não possa ser renderizado. Em seguida, usa a segunda fonte na lista para renderizar esse caractere. Se essa fonte não renderizar o caractere, o <span class="keyword"> Servidor de relatórios </span> usará a terceira fonte na lista para renderizar esse caractere, e assim por diante, até que atinja o final da lista de fontes. Se a fonte correta não estiver listada no vetor, <span class="keyword"> o Servidor de relatórios </span> exibirá o valor hexadecimal do caractere. </p> <p> <p>Observação:  Não faça alterações nesse parâmetro enquanto o Servidor de <span class="keyword"> relatórios </span> estiver em execução. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gama </td> 
   <td colname="col2"> <p> <span class="wintitle"> Configuração de gama </span> para saída de arquivo <span class="filepath"> .png </span> . O valor padrão é 1.6. </p> <p> <p>Observação:  A Adobe não recomenda alterar esse valor. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licenciamento </td> 
   <td colname="col2"> <p>Opcional. É necessário modificar os parâmetros neste vetor somente se você entrar em contato com o servidor de licença da Adobe por meio de um servidor proxy. </p> <p>Identificador de seção para parâmetros que você definiu para entrar em contato com o servidor de licenças da Adobe por meio de um servidor proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço proxy </td> 
   <td colname="col2"> O endereço de um servidor proxy que <span class="keyword"> o Servidor de relatórios </span> deve usar para acessar o servidor de licenças da Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Senha do proxy </td> 
   <td colname="col2"> Opcional. A senha associada ao Nome de usuário do <span class="wintitle"> proxy </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta proxy </td> 
   <td colname="col2"> A porta do servidor proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome do usuário proxy </td> 
   <td colname="col2"> Opcional. O nome de usuário usado para acessar o servidor proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Local da rede </td> 
   <td colname="col2"> O local de rede que <span class="keyword"> o Servidor de relatórios </span> usa para resolver o nome comum do servidor para um endereço IP. Os locais de rede são definidos no arquivo de endereço localizado no diretório Endereços da máquina do servidor análise de big data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidores </td> 
   <td colname="col2"> <p>Identificador de seção para parâmetros que você definiu para configurar quais máquinas do servidor de análise de big data <span class="keyword"> o Servidor de Relatório </span> deve se conectar para gerar relatórios. Isso inclui um número que indica quantos itens estão listados nesse vetor. </p> <p>Para cada servidor, adicione uma entrada serverInfo e preencha os parâmetros conforme necessário. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço </td> 
   <td colname="col2"> Endereço IP da máquina do servidor da análise de big data à qual o Servidor de <span class="keyword"> relatórios </span> deve se conectar para gerar relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> O nome que <span class="keyword"> o Servidor de Relatório </span> usa internamente para identificar o servidor da análise de big data. Este é apenas um rótulo interno, portanto você pode usar qualquer nome que quiser. Para fins de consistência, sugerimos que você use o nome comum conforme listado no certificado digital do servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta </td> 
   <td colname="col2"> Porta pela qual o Servidor de <span class="keyword"> relatórios </span> se comunica com o servidor de análise de big data. Para conexões seguras, esse valor geralmente é 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço proxy </td> 
   <td colname="col2"> O endereço de um servidor proxy que <span class="keyword"> o Servidor de Relatório </span> deve usar para acessar o servidor de análise de big data. Esse parâmetro é necessário somente quando um servidor proxy é necessário para se conectar aos computadores do servidor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Senha do proxy </td> 
   <td colname="col2"> A senha para o servidor proxy. Esse parâmetro é necessário somente quando um servidor proxy é necessário para se conectar às máquinas do servidor do análise de big data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta proxy </td> 
   <td colname="col2"> A porta do servidor proxy. O valor padrão é 8080. Esse parâmetro é necessário somente quando um servidor proxy é necessário para se conectar às máquinas do servidor do análise de big data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome do usuário proxy </td> 
   <td colname="col2"> O nome de usuário para o servidor proxy. Esse parâmetro é necessário somente quando um servidor proxy é necessário para se conectar às máquinas do servidor do análise de big data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificado de cliente SSL </td> 
   <td colname="col2"> Nome do arquivo de certificado SSL para a máquina do Servidor de <span class="keyword"> Relatório </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome comum do servidor SSL </td> 
   <td colname="col2"> <span class="wintitle"> Nome comum do servidor </span> listado no certificado digital do servidor de análise de big data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar SSL </td> 
   <td colname="col2"> Indica se o SSL é usado para comunicação segura entre o servidor da análise de big data e o Servidor <span class="keyword"> de relatórios </span>. As opções são true ou false. O valor padrão é true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de memória de resultado (KB) </td> 
   <td colname="col2"> <p>A quantidade de memória (em KB) que você deseja disponibilizar para relatórios e alertas. O valor padrão é 50000. </p> <p>Ao executar relatórios, <span class="keyword"> o Servidor de relatórios </span> verifica esse valor primeiro e, em seguida, verifica o valor no parâmetro Tamanho máximo da fatia. Por exemplo, se você definir esse parâmetro como 50.000 e o Tamanho máximo da fatia como 50, o Servidor de <span class="keyword"> relatórios </span> executará apenas 50 espaços de trabalho de cada vez, mesmo se houver espaço disponível para executar mais espaços de trabalho. </p> <p> <p>Observação:  Esse limite nunca deve exceder o valor definido no parâmetro de Limite de Memória de Consulta do servidor da análise de big data e, idealmente, deve ser definido um pouco abaixo do Limite de Memória de <span class="wintitle"> Consulta </span> para fornecer alguma margem para outros usuários que possam estar executando relatórios ao mesmo tempo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tamanho máximo da fatia </td> 
   <td colname="col2"> O número máximo de espaços de trabalho de relatório que <span class="keyword"> o Servidor de Relatório </span> pode executar simultaneamente. O valor padrão é 50. Para obter mais informações sobre como o Servidor de <span class="keyword"> relatórios </span> usa essa configuração, consulte a descrição do parâmetro <span class="wintitle"> Limite de memória de resultado (KB) </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Atualizar software </td> 
   <td colname="col2"> <p>Indica se o software deste <span class="keyword"> </span> Servidor de Relatório deve ser atualizado pelo servidor de análise de big data. As opções são true ou false. O valor padrão é true. </p> <p>Veja a seguir um exemplo desse parâmetro que você pode usar como modelo: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usar renderização de hardware OpenGL </td> 
   <td colname="col2"> <p>Controla se <span class="keyword"> o Servidor de Relatório </span> usa renderização de hardware (como a placa gráfica da máquina) para produzir saída de relatório. As opções são true ou false. O valor padrão é true. </p> <p>Esse parâmetro deve ser definido como falso somente quando houver problemas com a sua placa gráfica. Quando definido como falso, <span class="keyword"> o Servidor de Relatório </span> não tenta usar a renderização de hardware e usa a renderização de software por padrão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Relatórios </td> 
   <td colname="col2"> Identificador de seção para parâmetros definidos para configurar relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de mensagem de conclusão </td> 
   <td colname="col2"> <p>A frequência (em segundos) com a qual o Servidor de <span class="keyword"> relatórios </span> imprime mensagens de status de conclusão quando as consultas estão sendo executadas durante a geração de relatórios ou alertas. O valor padrão é 120 segundos. </p> <p>Exemplo: As consultas do Workspace estão 62.145672% concluídas. </p> <p>As mensagens de conclusão são gravadas no <span class="filepath"> reportserver.log </span> e sincronizadas no servidor. Essa configuração controla os arquivos <span class="filepath"> status.txt </span> que são enviados para frente e para trás para cada conjunto de relatórios, para que a porcentagem concluída possa ser mostrada com miniaturas. As mensagens são enviadas sempre que um conjunto de relatórios é concluído ou quando o intervalo é atingido, o que ocorrer primeiro. A configuração desse valor mais alto não afeta a taxa na qual você vê o relatório gerado na interface do cliente pelas miniaturas, mas afeta quantas mensagens provisórias você vê. A especificação de um valor baixo pode fazer com que o sistema gaste uma grande quantidade de tempo sincronizando dados, pois os dados são sincronizados do servidor do <span class="keyword"> Servidor de </span> relatórios para o perfil, em todas as DPUs e para todos os clientes conectados sempre que uma <span class="filepath"> </span> mensagem de status.txt é alterada. </p> <p>O sistema sempre envia um arquivo <span class="filepath"> status.txt </span> quando um conjunto de relatórios é concluído, independentemente da configuração desse parâmetro de configuração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perfis </td> 
   <td colname="col2"> <p>Número que indica quantos itens estão listados nesse vetor. Para cada perfil para o qual os relatórios devem ser criados, adicione uma entrada <span class="wintitle"> ReportProfile </span> ao vetor Perfis e preencha os parâmetros Server e Profile. </p> <p> <span class="wintitle"> Servidor </span> - o nome que <span class="keyword"> o Servidor de Relatório </span> usa internamente para identificar o servidor da análise de big data. Esse nome deve ser o nome comum do servidor listado no certificado SSL do servidor de análise de big data. </p> <p> <span class="wintitle"> Perfil </span> - Nome do perfil para o qual os relatórios devem ser criados. Esse nome deve corresponder ao perfil nomeado na máquina do servidor da análise de big data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para Erros </td> 
   <td colname="col2"> <p>O endereço do servidor SMTP a partir do qual você deseja enviar erros do Servidor de <span class="wintitle"> relatórios por </span> email. </p> <p>Exemplo: <span class="filepath"> mail.mycompany.com </span> </p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para senha de erros </td> 
   <td colname="col2"> <p>A senha para fazer logon no servidor SMTP. Esse parâmetro é opcional, a menos que o logon seja necessário para enviar emails. </p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servidor SMTP para Erros Enviados de </td> 
   <td colname="col2"> O endereço de email do qual você deseja enviar <span class="wintitle"> erros do Servidor de </span> relatórios. </td> 
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
   <td colname="col1"> Intervalo de status </td> 
   <td colname="col2"> <p>A frequência (em segundos) com a qual <span class="wintitle"> o Servidor de Relatório </span> gera e envia informações de status para o servidor da análise de big data a ser exibido em Status <span class="wintitle"> Detalhado </span>. </p> <p>O valor padrão é 120 segundos. Não é recomendável definir isso para um valor pequeno, como dois minutos, pois uma fila de relatórios pode levar horas para ser executada. Nesse caso, você pode considerar uma configuração de 600 a 1200 segundos. </p> <p>Para obter mais informações sobre <span class="wintitle"> Status detalhado </span>, consulte o capítulo Interfaces administrativas do Guia do usuário do <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervalo de atualização </td> 
   <td colname="col2"> <p>A frequência (em minutos) com a qual o Servidor de <span class="keyword"> relatórios </span> monitora todos os perfis listados no vetor Perfis para novos relatórios e alertas. O valor padrão é 10 minutos. </p> <p>O tempo especificado é dividido entre todos os perfis listados. Por exemplo, se seu intervalo estiver definido como 10 minutos e você estiver monitorando dois perfis, cada perfil será monitorado por 5 minutos. Se um perfil estiver sendo monitorado quando um relatório ou alerta novo ou modificado for salvo no perfil, o relatório ou alerta estará disponível imediatamente para geração. </p> <p>Se o Intervalo de <span class="wintitle"> atualização </span> estiver configurado para monitorar mais de um perfil, é importante que essa configuração seja alta o suficiente para carregar todos os perfis dentro do tempo configurado. Em sistemas com muitas grandes dimensões configuradas, por exemplo, onde pode levar vários minutos para recuperar a conexão de dados inicial com todos os nomes de elementos, essa configuração deve ser longa o suficiente para que ocorra essa sincronização completa. Caso contrário, o sistema emitirá um erro de sincronização de perfil. </p> </td> 
  </tr> 
 </tbody> 
</table>

