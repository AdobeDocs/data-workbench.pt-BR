---
description: Instruções para instalar e configurar o Sensor para o Sun Java System Application Server Standard Edition 7 em execução no Windows Server 2000 ou posterior.
title: Sun Java Server no Windows Server 2000 ou posterior
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
exl-id: 33f24073-8eff-4bf6-8f83-7a122d1505d8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%

---

# Sun Java Server no Windows Server 2000 ou posterior{#sun-java-server-on-windows-server-or-later}

{{eol}}

Instruções para instalar e configurar o Sensor para o Sun Java System Application Server Standard Edition 7 em execução no Windows Server 2000 ou posterior.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação obtido do site de download do Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor da Web específico, baixe-o (ou obtenha-o do representante do Adobe) antes de começar os seguintes procedimentos.

O sensor é compatível com os seguintes servidores em execução no RedHat Linux 7.x ou posterior ou com o Sun Solaris SPARC 2.6 ou posterior:

Para instalar e configurar o Sensor, execute as seguintes etapas:

## Instalar os arquivos do programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedimento para extrair e instalar os arquivos de programa do Sensor no servidor.

1. Em seu Netscape Enterprise, iPlanet, Sun ONE ou Sun Java System Server, crie um diretório no qual instalar os arquivos de programa Sensor. Lembre-se de que sua fila de discos reside nesse diretório, portanto, verifique se o dispositivo escolhido tem espaço suficiente para manter uma fila do tamanho necessário.

   ```
   C:\VisualSensor
   ```

1. Extraia o conteúdo do arquivo de instalação para o diretório que acabou de criar. Durante essa etapa, o Sensor instala os seguintes arquivos:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Diretório de destino </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> saf_visual_sciences.dll </td> 
   <td colname="col2"> O módulo de carregamento do coletor. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/ visual_sciences</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> O programa transmissor. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> O arquivo de configuração do Sensor. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> O certificado usado para validar o certificado digital que o Insight Server apresenta durante o processo de conexão </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, você pode querer copiar o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extrair o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre experimentação controlada, consulte o Guia de experimentos controlados do Insight.

## Editar o arquivo de configuração do sensor {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

O [!DNL txlogd.conf] contém os parâmetros de configuração do Sensor.

É necessário editar esse arquivo para especificar, entre outras coisas, o tamanho e o local do arquivo da fila de discos, o endereço do servidor Insight e a ID que será anexada aos dados do evento produzidos por esse sensor.

O arquivo de configuração contém parâmetros obrigatórios e parâmetros opcionais.

* **Parâmetros obrigatórios** são configurações que você deve especificar ao instalar o Sensor. Sem essas configurações, o Sensor não é executado com êxito.
* **Parâmetros opcionais** são configurações que assumem o padrão de valores predefinidos (que podem ser modificados) ou ativam recursos opcionais.

**Para editar o arquivo de configuração do Sensor**

* Abra o [!DNL /etc/txlogd.conf] em um editor de texto e defina os parâmetros obrigatórios, bem como quaisquer parâmetros opcionais desejados.
* Salve e feche o arquivo.

**Para editar o arquivo de configuração do Sensor**

1. Abra o [!DNL /etc/txlogd.conf] em um editor de texto e defina os parâmetros obrigatórios, bem como quaisquer parâmetros opcionais desejados.
1. Salve e feche o arquivo.

## Inicie o transmissor e crie a fila de discos {#section-55630de65f264274aefd771da2002852}

Após configurar o arquivo txlogd.conf, você pode iniciar o programa transmissor, registrá-lo como um serviço do Windows e criar a fila de disco.

1. No menu Iniciar do Windows, selecione Acessórios > Prompt de comando.
1. Na janela da tela de comandos, navegue até o diretório em que o Sensor foi instalado e execute o seguinte comando:

   ```
   txlog /regserver
   ```

   Esse comando inicia o transmissor, cria a fila de disco e registra o Sensor como um serviço do Windows.

1. Para confirmar que o transmissor está sendo executado corretamente, clique em Iniciar > Painel de controle > Ferramentas administrativas > Serviços. Na lista de serviços, localize a entrada do Sensor e confirme se seu status é Iniciado e se seu tipo de inicialização é Automático. Em seguida, feche o painel de controle Serviços .
1. Para verificar se o transmissor apresentou algum erro durante a inicialização, clique em Iniciar > Painel de controle > Ferramentas administrativas > Visualizador de eventos para abrir o Visualizador de eventos.

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

## Modificar o script de inicialização {#section-19a38f27c9f44adf88f8910f5ed483a3}

No arquivo init.conf (por exemplo, C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf), adicione as seguintes linhas no final do arquivo:

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

No arquivo obj.conf (por exemplo, C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.conf), adicione as seguintes linhas logo abaixo das linhas existentes `<Object name="default">` linha:

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```
