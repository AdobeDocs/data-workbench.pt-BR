---
description: Instruções sobre como instalar e configurar o Sensor para Serviços de Informações da Internet (IIS) 5.x ou 6.x em execução no Microsoft Windows Server 2000 ou posterior.
title: Microsoft IIS no Windows Server 2000 ou posterior
uuid: 26da0638-82c8-424f-9f00-aab3a940e5a9
exl-id: e4b5ac44-b0ac-43be-9b9c-180a64354081
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1718'
ht-degree: 1%

---

# Microsoft IIS no Windows Server 2000 ou posterior{#microsoft-iis-on-windows-server-or-later}

{{eol}}

Instruções sobre como instalar e configurar o Sensor para Serviços de Informações da Internet (IIS) 5.x ou 6.x em execução no Microsoft Windows Server 2000 ou posterior.

Ao usar o IIS 6.x, o registro deve ser ativado para que o Sensor funcione corretamente. Se você tiver desativado o registro para reduzir a E/S do disco, poderá ativar o registro sem gravar dados nos registros. Para fazer isso, ative o registro e, em seguida, limpe todos os campos na guia Advanced das Properties para o W3C Extended Log File Format. Se precisar de assistência, entre em contato com os Serviços de consultoria da Adobe.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação obtido do site de download do Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor da Web específico, baixe-o (ou obtenha-o do representante do Adobe) antes de começar os seguintes procedimentos.

Para instalar e configurar o Sensor, você deve executar as seguintes etapas de alto nível:

## 1. Instale os arquivos de programa {#section-9ef8c4e38c244b7d8b6d4bc6c0ad53fd}

Ao executar o Sensor no Windows IIS, os arquivos do programa e o arquivo da fila do disco devem residir no mesmo diretório.

Portanto, antes de instalar os arquivos do programa, você deve determinar onde deseja manter a fila do disco, pois é também onde você deve instalar os arquivos do programa.

Use o procedimento a seguir para extrair e instalar os arquivos de programa do Sensor.

1. Na máquina Windows, crie um diretório no qual os arquivos de programa Sensor serão instalados. Lembre-se de que sua fila de discos também reside nesse diretório, portanto, verifique se o dispositivo escolhido tem espaço suficiente para manter uma fila do tamanho necessário.

   Por exemplo: C:\VisualSensor

1. Extraia o conteúdo do arquivo de instalação para o diretório que acabou de criar. Durante essa etapa, o Sensor instala os seguintes arquivos:

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
   <td colname="col2"> Mensagens do Visualizador de Eventos. </td>
  </tr>
  <tr>
   <td colname="col1"> qlog.dll </td>
   <td colname="col2"> O módulo coletor (um filtro ISAPI). </td>
  </tr>
  <tr>
   <td colname="col1"> TestExperiment.xls </td>
   <td colname="col2"> <p>Um arquivo de planilha do Excel que os arquitetos podem usar para configurar um experimento controlado. </p> <p>O sensor não usa esse arquivo. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> trust_ca_cert.pem </td>
   <td colname="col2"> O certificado usado para validar o certificado digital que o Insight Server apresenta durante o processo de conexão. </td>
  </tr>
  <tr>
   <td colname="col1"> TXLog.exe </td>
   <td colname="col2"> O programa transmissor. </td>
  </tr>
  <tr>
   <td colname="col1"> txlogd.conf </td>
   <td colname="col2"> O arquivo de configuração do Sensor. </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, você pode querer copiar o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extrair o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre experimentação controlada, consulte o Guia de experimentos controlados do Insight.

## 2. Edite o arquivo de configuração {#section-206daf855e664f16af9a96a5cd3e62b1}

O arquivo txlogd.conf contém os parâmetros de configuração do Sensor.

Você deve editar o arquivo para especificar, entre outras coisas, o tamanho da fila de disco, o endereço do servidor Insight e a ID que será anexada aos dados produzidos por esse sensor. O arquivo de configuração contém parâmetros obrigatórios e parâmetros opcionais.

* **Parâmetros obrigatórios** são configurações que você deve especificar ao instalar o Sensor. Sem essas configurações, o Sensor não é executado com êxito.
* **Parâmetros opcionais** são configurações que assumem o padrão de valores predefinidos (que podem ser modificados) ou ativam recursos opcionais.

**Para editar o arquivo de configuração do Sensor**

1. Abra o `<SensorDirectory>/txlogd.conf` em um editor de texto e defina os parâmetros obrigatórios, bem como quaisquer parâmetros opcionais desejados.

   Para obter descrições dos parâmetros txlogd.conf, consulte Parâmetros do arquivo Txlogd.conf do sensor.

   Para obter exemplos de arquivos de configuração concluídos, consulte Arquivos de configuração de amostra do sensor.

1. Salve e feche o arquivo.

## 3. Inicie o transmissor e crie a fila de discos {#section-a0af390ee1954109bcff5d9f09798683}

Após configurar o arquivo txlogd.conf, você pode iniciar o programa transmissor, registrá-lo como um serviço do Windows e criar a fila de disco.

1. No menu Iniciar do Windows, selecione Acessórios > Prompt de comando.
1. Na janela da tela de comandos, navegue até o diretório em que o Sensor foi instalado e execute o seguinte comando:

   ```
   txlog /regserver
   ```

   Esse comando inicia o transmissor, cria a fila de disco e registra o Sensor como um serviço do Windows.

1. Para confirmar que o transmissor está sendo executado corretamente, clique em Iniciar > Painel de controle > Ferramentas administrativas > Serviços.

   >[!NOTE]
   >
   >Essa sequência de comando pode variar dependendo da versão do Windows que você estiver usando.

   1. Na lista de serviços, localize a entrada do Sensor e confirme se seu status é Iniciado e se seu tipo de inicialização é Automático.
   1. Feche o painel de controle Serviços .

1. Para verificar se o transmissor apresentou algum erro durante a inicialização, clique em Iniciar > Painel de controle > Ferramentas administrativas > Visualizador de eventos para abrir o Visualizador de eventos.

   >[!NOTE]
   >
   >Essa sequência de comando pode variar dependendo da versão do Windows que você estiver usando.

   1. No painel esquerdo da janela Visualizador de Eventos, selecione o log de Aplicativos.
   1. No painel direito, procure por eventos com &quot;Adobe&quot; na coluna Origem.
   1. Se você encontrar um erro de &quot;Adobe&quot;, clique duas vezes no erro para exibir a janela Propriedades do evento. Esta janela fornece informações detalhadas sobre o erro.

1. Quando terminar de examinar o log de Aplicativos, feche o Visualizador de Eventos.
1. Verifique se o transmissor criou a fila de discos (Diskq2000.log) no diretório onde você instalou os arquivos de programa do Sensor e se é o tamanho especificado no parâmetro QueueSize no arquivo txlogd.conf.

   Se a fila não tiver sido criada corretamente:

   1. Examine o arquivo txtlogd.conf e verifique se o parâmetro QueueSize está definido corretamente.
   1. Verifique se o dispositivo no qual você instalou o Sensor tem espaço suficiente disponível para armazenar um arquivo do tamanho especificado no parâmetro QueueSize .
   1. Usando o painel de controle Serviços no Windows, pare o transmissor.
   1. Exclua o arquivo da fila.
   1. Registre novamente o Sensor como um serviço do Windows: no menu Iniciar do Windows, selecione Acessórios > Prompt de comando. Na janela da tela de comandos, navegue até o diretório em que o Sensor foi instalado e execute o seguinte comando:

      ```
      txlog /regserver
      ```

O transmissor foi projetado para funcionar continuamente. Se você reiniciar a máquina, o transmissor será reiniciado automaticamente. Se precisar iniciar e parar o transmissor manualmente, faça isso usando o Painel de controle dos Serviços no Windows.

## Adicionar o Coletor ao Servidor Web {#section-682dc480e5574791ac18da104daf7906}

Para o IIS, o coletor é um filtro ISAPI adicionado ao servidor da Web no IIS.

1. Abra o Gerenciador do IIS usando Iniciar > Ferramentas Administrativas > Gerenciador dos Serviços de Informações da Internet (IIS).
1. Expanda os nós Computador local e Sites da Web .
1. Clique com o botão direito do mouse no site ao qual deseja adicionar o coletor e selecione Propriedades.
1. Selecione a guia Filtros de ISAPI e clique em Adicionar.
1. No campo Nome do filtro , insira um nome de exibição para o filtro. O nome do filtro sugerido é &quot;Sensor&quot;.
1. Clique em Procurar, selecione o arquivo qlog.dll (localizado no diretório onde você instalou o Sensor) e clique em OK.
1. Clique em OK para adicionar o filtro.

   Após adicionar o filtro, o coletor fica operacional imediatamente e pronto para coletar os dados. Uma seta verde para cima deve aparecer na coluna Status da guia Filtros de ISAPI do Gerenciador do IIS. Talvez você não veja a seta verde até que o tráfego flua pelo filtro. Nesse caso, você precisa enviar uma solicitação ao servidor da Web para confirmar que o coletor está funcionando corretamente.

Se a seta verde não aparecer depois que o tráfego fluir para o coletor, conclua as seguintes etapas:

1. Clique em Iniciar > Ferramentas administrativas > Visualizador de eventos para verificar se há erros no Visualizador de eventos.

   >[!NOTE]
   >
   >Essa sequência de comando pode variar dependendo da versão do Windows que você estiver usando.

1. No painel esquerdo da janela Visualizador de eventos, selecione o log de aplicativos.
1. No painel direito, procure por eventos com &quot;Adobe&quot; na coluna Origem.
1. Se você encontrar um erro, clique duas vezes no erro para exibir a janela Propriedades do evento.

## Capturando dados adicionais {#section-dcd10073eb1947a5928e4f9b9fa99e3a}

As páginas da Web geralmente são estruturadas usando a linguagem de programação ASP (Ative Server Pages).

ASP é uma tecnologia Microsoft que funciona dentro do IIS. Quando um navegador solicita um arquivo ASP, o IIS transmite a solicitação para o mecanismo ASP. O mecanismo ASP lê o arquivo ASP, linha por linha, e executa os scripts no arquivo. Finalmente, o arquivo ASP é retornado ao navegador como HTML simples. O ASP fornece objetos RESPOND ou REQUEST que, além de outras utilizações, permitem a resposta ou a solicitação de consultas de usuários ou dados enviados de formulários HTML.

Em certos casos, talvez você não queira anexar os valores inseridos nos formulários ao URL exibido na barra de endereços do navegador do usuário ou que seja visível no próprio código HTML. O script ASP simples do lado do servidor permite anexar nomes de campos de formulário e seus respectivos valores ao arquivo de log sem disponibilizá-los no navegador do usuário ou incorporá-los ao arquivo HTML. Para capturar os valores de formulário reais inseridos em formulários específicos dentro do site, algumas linhas de código devem ser adicionadas para anexar os valores do formulário à solicitação de log.

Na página de processamento de um formulário, inclua o seguinte código para anexar os valores de formulário inseridos aos dados da solicitação (além de gravar os valores de formulário enviados em um banco de dados externo ou outro local):

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

Esse processo anexaria os valores do formulário, conforme definido para os dados da solicitação para a página de Processamento de formulário. Nos dados de log, os valores anexados estariam disponíveis como sequências de consulta da página Processamento de formulário, conforme ilustrado abaixo. Por exemplo, v_1, v_2, v_3 e v_4 agora seriam cadeias de caracteres de consulta contendo os dados inseridos nos campos de formulário apropriados. A sintaxe descrita no exemplo anterior pode ser duplicada para quaisquer campos e valores de formulário adicionais que você deseja capturar:

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Se quiser que cada campo de formulário e valor sejam capturados e disponibilizados para análise, use a seguinte sintaxe:

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

Esse exemplo usaria todos os campos de formulário presentes no HTML, juntamente com seus respectivos valores e os anexaria como cadeias de caracteres de consulta à entrada de log da página Processamento de formulário. Observe que isso incluiria quaisquer campos ocultos presentes no formulário.

Os dados de log seriam aumentados conforme detalhado na tabela a seguir:

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_1 | Valor associado à sequência de consulta NAME | v_1=John Smith |
| v_2 | Valor associado à sequência de consulta CITY | v_2=Los Angeles |
| v_3 | Valor associado à sequência de consulta STATE | v_3=Califórnia |
| v_4 | Valor associado à sequência de consulta ZIP | v_4=90210 |
