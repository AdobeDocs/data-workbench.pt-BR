---
description: Instale e configure o Sensor para Microsoft IIS 7.x ou 8.x em execução no Microsoft Windows Server 2008 ou posterior.
title: Microsoft IIS no Windows Server 2008 ou posterior
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Microsoft IIS no Windows Server 2008 ou posterior{#microsoft-iis-on-windows-server-or-later}

Instale e configure o Sensor para Microsoft IIS 7.x ou 8.x em execução no Microsoft Windows Server 2008 ou posterior.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação que você obtém do site de download da Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor Web específico, baixe-o (ou obtenha-o do seu representante da Adobe) antes de começar os procedimentos a seguir.

Para instalar e configurar o Sensor, execute as seguintes etapas de alto nível:

1. [Instale os arquivos de programa](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [Editar o arquivo de configuração do sensor](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [Inicie o transmissor e crie a fila de discos](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [Adicionar o coletor ao servidor da Web](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [Capturar dados adicionais](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## Instale os arquivos de programa {#section-cb51e5932a6d40c5b00758a7a51b7578}

Ao executar o Sensor no Windows IIS, os arquivos de programa e o arquivo de fila de disco devem residir no mesmo diretório.

Antes de instalar os arquivos do programa, primeiro determine onde deseja manter a fila de discos, pois é onde você deve instalar os arquivos do programa.

Use o procedimento a seguir para extrair e instalar os arquivos de programa do Sensor.

1. No computador Windows, crie um diretório no qual os arquivos de programa Sensor serão instalados. Lembre-se de que sua fila de discos também reside neste diretório, portanto, verifique se o dispositivo escolhido tem espaço suficiente para manter uma fila do tamanho necessário.

   Por exemplo: C:\VisualSensor

1. Extraia o conteúdo do arquivo de instalação para o diretório que você acabou de criar. Durante esta etapa, o Sensor instala os seguintes arquivos:

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Mensagens do Visualizador de eventos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> qlog.dll </td> 
   <td colname="col2"> O módulo coletor (um filtro ISAPI). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TestExperiment.xls </td> 
   <td colname="col2"> <p>Um arquivo de planilha do Excel que os arquitetos podem usar para configurar um experimento controlado. </p> <p>O sensor não usa este arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> O certificado usado para validar o certificado digital que o Insight Server apresenta durante o processo de conexão. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> O programa do transmissor. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> O arquivo de configuração do sensor. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, copie o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extraia o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre a experimentação controlada, consulte o Guia de Experimentos Controlados Insight.

## Editar o arquivo de configuração do sensor {#section-1e1590a92222430e92066292512ae0df}

O arquivo txlogd.conf contém os parâmetros de configuração do Sensor.

Você deve editar o arquivo para especificar, entre outras coisas, o tamanho da fila de discos, o endereço do Insight Server e a ID que será anexada aos dados produzidos por esse sensor. O arquivo de configuração contém parâmetros obrigatórios e opcionais.

* **Parâmetros** obrigatórios são configurações que você deve especificar ao instalar o Sensor. Sem essas configurações, o sensor não é executado com êxito.
* **Parâmetros** opcionais são configurações padrão para valores predefinidos (que podem ser modificados) ou habilitam recursos opcionais.

**Para editar o arquivo de configuração do sensor**

1. Abra o `<SensorDirectory>/txlogd.conf` arquivo em um editor de texto e defina os parâmetros necessários, bem como quaisquer parâmetros opcionais desejados.

   Para obter descrições de [!DNL txlogd.conf] parâmetros, consulte Parâmetros [de arquivo Txlogd.conf do](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed)sensor.

1. Salve e feche o arquivo.

## Inicie o transmissor e crie a fila de discos {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

Depois de configurar o [!DNL txlogd.conf]arquivo, você pode iniciar o programa transmissor, registrá-lo como um serviço do Windows e criar a fila de discos.

1. No menu Iniciar do Windows, selecione Acessórios > Prompt de comando.
1. Na janela da tela de comandos, navegue até o diretório no qual você instalou o Sensor e execute o seguinte comando:

   ```
   txlog /regserver
   ```

   Esse comando inicia o transmissor, cria a fila de discos e registra o Sensor como um serviço do Windows.

1. Para confirmar se o transmissor está sendo executado corretamente, clique em Iniciar > Painel de controle > Ferramentas administrativas > Serviços.

   >[!NOTE]
   >
   >Essa sequência de comando pode variar dependendo da versão do Windows que você está usando.

   1. Na lista de serviços, localize a entrada Sensor e confirme se seu status é Iniciado e seu tipo de inicialização é Automático.
   1. Feche o painel de controle Serviços.

1. Para verificar se o transmissor apresentou erros durante a inicialização, clique em Iniciar > Painel de controle > Ferramentas administrativas > Visualizador de eventos para abrir o Visualizador de eventos.

   >[!NOTE]
   >
   >Essa sequência de comando pode variar dependendo da versão do Windows que você está usando.

   1. No painel esquerdo da janela Visualizador de eventos, selecione o registro Aplicativos.
   1. No painel direito, procure eventos com &quot;Adobe&quot; na coluna Origem.
   1. Se encontrar um erro em &quot;Adobe&quot;, clique duas vezes no erro para exibir a janela Propriedades do evento. Esta janela fornece informações detalhadas sobre o erro.

1. Quando terminar de examinar o log de Aplicativos, feche o Visualizador de Eventos.
1. Verifique se o transmissor criou a fila de discos (Diskq2008.log) no diretório onde você instalou os arquivos de programa do Sensor e se é do tamanho especificado no parâmetro QueueSize no arquivo txlogd.conf.

   Se a fila não tiver sido criada corretamente:

   1. Examine o arquivo txtlogd.conf e verifique se o parâmetro QueueSize está definido corretamente.
   1. Verifique se o dispositivo no qual você instalou o Sensor tem espaço suficiente disponível para manter um arquivo do tamanho especificado no parâmetro QueueSize.
   1. Usando o painel de controle de serviços no Windows, pare o transmissor.
   1. Exclua o arquivo da fila.
   1. Registre novamente o Sensor como um serviço do Windows: no menu Iniciar do Windows, selecione Acessórios > Prompt de comando. Na janela da tela de comandos, navegue até o diretório no qual você instalou o Sensor e execute o seguinte comando:

      ```
      txlog /regserver
      ```

O transmissor foi projetado para funcionar continuamente. Se você reiniciar a máquina, o transmissor será reiniciado automaticamente. Se você precisar iniciar e parar o transmissor manualmente, poderá fazê-lo usando o painel de controle Serviços no Windows.

## Adicionar o coletor ao servidor da Web {#section-088960c986cf449cb712152298b3518d}

Para o IIS, o coletor é um filtro ISAPI que você adiciona ao seu servidor Web no IIS.

1. Abra o Gerenciador do IIS usando **Iniciar > Ferramentas administrativas > Gerenciador** do IIS (Internet Information Services).
1. Expanda os nós Computador **** local e **Sites** .
1. Selecione o site e, no painel direito, clique duas vezes em Filtros **** ISAPI.
1. No painel **Ações** , clique em **Adicionar**.

1. No campo Nome **do** filtro, digite um nome para exibição para o filtro. O nome do filtro sugerido é &quot;Sensor&quot;.
1. Clique em **Procurar**, selecione o arquivo qlog.dll (localizado no diretório onde você instalou o Sensor) e clique em **OK**.

1. Clique em **OK** para adicionar o filtro.

   Depois de adicionar o filtro, o coletor estará imediatamente operacional e pronto para coletar dados.

Se a seta verde não aparecer depois que o tráfego fluir para o coletor, conclua as seguintes etapas:

1. Clique em Iniciar > Ferramentas administrativas > Visualizador de eventos para verificar se há erros no Visualizador de eventos.

   >[!NOTE]
   >
   >Essa sequência de comando pode variar dependendo da versão do Windows que você está usando.

1. No painel esquerdo da janela Visualizador de eventos, selecione o log de **aplicativos** .
1. No painel direito, procure eventos com &quot;Adobe&quot; na coluna **Origem** .
1. Se encontrar um erro, clique duas vezes no erro para exibir a janela Propriedades **do** evento.

## Capturar dados adicionais {#section-98db9625efdc4b60bfd76f7adf4af74d}

Geralmente, as páginas da Web são estruturadas usando a linguagem de programação ASP (Ative Server Pages).

ASP é uma tecnologia da Microsoft que funciona dentro do IIS. Quando um navegador solicita um arquivo ASP, o IIS transmite a solicitação para o mecanismo ASP. O mecanismo ASP lê o arquivo ASP, linha por linha, e executa os scripts no arquivo. Por fim, o arquivo ASP é retornado ao navegador como HTML simples. O ASP fornece objetos RESPOND ou REQUEST que, além de outras utilizações, permitem a resposta ou solicitação de consultas de usuários ou dados enviados de formulários HTML.

Em certos casos, talvez você não queira anexar os valores inseridos nos formulários ao URL que é exibido na barra de endereços do navegador de um usuário ou que é visível no próprio código HTML. O script ASP simples do lado do servidor permite anexar nomes de campos de formulário e seus respectivos valores ao arquivo de log sem disponibilizá-los no navegador do usuário ou incorporá-los ao arquivo HTML. Para capturar os valores de formulário reais inseridos em formulários específicos dentro do site, algumas linhas de código devem ser adicionadas para anexar os valores de formulário à solicitação de log.

Na página de processamento de um formulário, inclua o seguinte código para anexar os valores de formulário inseridos aos dados de solicitação (além de gravar os valores de formulário enviados em um banco de dados externo ou em outro local):

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

Esse processo anexaria os valores do formulário, conforme definido para os dados da solicitação para a página Processamento de formulário. Nos dados de log, os valores anexados estariam disponíveis como sequências de consulta da página Processamento de formulário, conforme ilustrado abaixo. Por exemplo, v_1, v_2, v_3 e v_4 agora são strings de consulta que contêm os dados inseridos nos campos de formulário apropriados. A sintaxe descrita no exemplo anterior pode ser duplicada para quaisquer campos de formulário e valores adicionais que você deseja capturar:

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Se quiser que todos os campos e valores de formulário sejam capturados e disponibilizados para análise, use a seguinte sintaxe:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues);
```

Este exemplo utilizaria todos os campos de formulário presentes no HTML junto com seus respectivos valores e os anexaria como sequências de consulta à entrada de registro da página Processamento de formulário. Observe que isso incluiria quaisquer campos ocultos presentes no formulário.

Os dados de log seriam aumentados conforme detalhado na tabela a seguir:

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_1 | Valor associado à string de consulta NAME | v_1=John Smith |
| v_2 | Valor associado à string de consulta CITY | v_2=Los Angeles |
| v_3 | Valor associado à string de consulta STATE | v_3=Califórnia |
| v_4 | Valor associado à string de consulta ZIP | v_4=90210 |

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->

