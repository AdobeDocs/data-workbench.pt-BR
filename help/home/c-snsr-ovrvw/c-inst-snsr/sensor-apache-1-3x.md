---
description: Instruções detalhadas para instalar e configurar o Sensor para um Apache Server 1.3.x no RedHat Linux 7.x ou posterior, SUSE Linux 9.x ou posterior, Sun Solaris SPARC 2.6 ou posterior, Sun Solaris x86 9 ou posterior, FreeBSD 4 ou posterior ou Mac OS X PowerPC.
title: Apache Server 1.3.x em Linux, Sun Solaris, FreeBSD ou Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 1.3.x em Linux, Sun Solaris, FreeBSD ou Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

Instruções detalhadas para instalar e configurar o Sensor para um Apache Server 1.3.x no RedHat Linux 7.x ou posterior, SUSE Linux 9.x ou posterior, Sun Solaris SPARC 2.6 ou posterior, Sun Solaris x86 9 ou posterior, FreeBSD 4 ou posterior ou Mac OS X PowerPC.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação que você obtém do site de download da Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor Web específico, baixe-o (ou obtenha-o do seu representante da Adobe) antes de começar os procedimentos a seguir.

Para instalar e configurar o Sensor, execute as seguintes etapas de alto nível:

## Instale os arquivos de programa {#section-aae323e252394212bf4096d65fdd280c}

Instruções para extrair e instalar os arquivos de programa do Sensor na máquina do servidor.

1. Faça logon como o usuário raiz ou como um usuário com autoridade raiz.
1. Descompacte e descompacte o arquivo de instalação usando o seguinte comando:

   * No Linux:

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * No Solaris:

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. Copie os arquivos de programa descompactados para os diretórios identificados na tabela a seguir:

<table id="table_A97CF630633C4543A742D96C302D1138"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Arquivo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
   <th colname="col3" class="entry"> Diretório de destino </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> O módulo de carregamento do coletor </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> O programa transmissor </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OU-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> O arquivo de configuração do sensor </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> O certificado usado para validar o certificado digital que o Insight Server apresenta durante o processo de conexão </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, copie o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extraia o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre a experimentação controlada, consulte o Guia de Experimentos Controlados Insight.

**Permissões nos arquivos de programas**

Permissões incorretas nos arquivos de programa causam a maioria dos problemas encontrados ao instalar o Sensor.

Certifique-se de definir as permissões exatamente como está indicado nesta seção.

Por padrão, os arquivos de programa no arquivo tar têm as seguintes permissões. Dependendo de como seu sistema está configurado, essas configurações podem ser alteradas (não mascaradas) ao extrair os arquivos. Para redefinir as permissões para as configurações padrão recomendadas, use os comandos chmod abaixo. Verifique se os diretórios nos quais você instalou os arquivos permitem pelo menos esse nível de acesso.

| Arquivo | Permissões padrão | comando chmod |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Editar o arquivo de configuração do sensor {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

O [!DNL txlogd.conf] arquivo contém os parâmetros de configuração do Sensor.

Você deve editar o arquivo para especificar, entre outras coisas, o tamanho da fila de discos, o endereço do Insight Server e a ID que será anexada aos dados produzidos por esse sensor.

O arquivo de configuração contém parâmetros obrigatórios e opcionais.

* Parâmetros obrigatórios são configurações que você deve especificar ao instalar o Sensor. Sem essas configurações, o sensor não é executado com êxito.
* Parâmetros opcionais são configurações padrão para valores predefinidos (que podem ser modificados) ou habilitam recursos opcionais.

Para editar o arquivo de configuração do sensor

1. Abra o arquivo /etc/txlogd.conf em um editor de texto e defina os parâmetros necessários, bem como quaisquer parâmetros opcionais desejados.
1. Salve e feche o arquivo.

## Inicie o transmissor e crie a fila de discos {#section-a453d912ec3d47aa8e40ccacf527119d}

Instruções para criar a fila de discos depois de configurar o arquivo txlogd.conf.

1. Se o diretório no qual a fila de discos reside ainda não existir, crie-o. Certifique-se de que o diretório fornece ao módulo coletor e ao programa transmissor acesso de leitura/gravação ao arquivo.
1. No computador em que o Sensor está instalado, execute o seguinte comando para iniciar o transmissor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * A opção &quot;i&quot; neste comando inicia o transmissor no modo interativo. Esse modo exibe mensagens do transmissor na tela e também permite que você interaja com o transmissor usando comandos do teclado.
   * A opção &quot;c&quot; direciona o transmissor para criar a fila de discos.
   * A opção &quot;f&quot; especifica o local do arquivo de configuração.

1. Verifique se o transmissor criou a fila de discos no local especificado no parâmetro QueueFile e no tamanho especificado no parâmetro QueueSize.
1. Se a fila não tiver sido criada corretamente, digite Ctrl+C para encerrar o transmissor e faça o seguinte:

   1. Examine o arquivo txtlogd.conf e verifique se os parâmetros QueueFile e QueueSize estão definidos corretamente.
   1. Verifique se o dispositivo ao qual a fila de discos está atribuída está operacional e tem espaço suficiente disponível para reter um arquivo do tamanho especificado no parâmetro QueueSize.
   1. Faça as correções necessárias e repita este procedimento.

## Adicionar o Coletor ao Servidor Web {#section-a7fb6425956f4f518ae3a7db091b33d2}

Para servidores Apache, o coletor é um objeto compartilhado dinâmico que você carrega no processo do servidor Web.

Para adicionar o coletor ao servidor da Web, edite o arquivo httpd.conf como descrito abaixo e reinicie o servidor da Web.

Se o Sensor estiver capturando dados para vários servidores da Web no computador servidor, você deverá executar o seguinte procedimento para cada servidor da Web.

1. Usando um editor de texto, abra o [!DNL httpd.conf] arquivo para o servidor da Web cujos eventos o Sensor captura.
1. Adicione as seguintes linhas ao final do arquivo:

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Essas linhas fazem distinção entre maiúsculas e minúsculas. Digite-os exatamente como aparecem acima.

1. Reinicie o servidor da Web. O coletor é carregado com o servidor da Web e começará a coletar dados de eventos e gravá-los na fila de discos.

## Teste o sensor {#section-83d9f60b39a6474f9c76bee3e19b2575}

Inicie o transmissor e verifique se ele consegue se conectar com êxito ao Insight Server e transmitir dados do evento para ele.

>[!NOTE]
>
>Para verificar se o transmissor pode enviar dados de evento com êxito ao Insight Server, verifique se o Insight Server de destino está instalado e em execução antes de iniciar o seguinte teste.

1. Se o transmissor ainda não estiver em execução, reinicie-o usando o seguinte comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Abra um navegador (em qualquer máquina) e solicite uma página do servidor da Web no qual o Sensor está sendo executado (certifique-se de selecionar uma página que o Sensor esteja monitorando).
1. Depois de emitir a solicitação, verifique se há mensagens no console do transmissor indicando que ele está enviando dados do evento para o Insight Server de destino.
1. Se o sensor não estiver transmitindo os dados com êxito, verifique se:

   * O Servidor Insight de destino está em execução.
   * Os parâmetros [!DNL ServerAddress] e [!DNL ServerPort] estão definidos corretamente em [!DNL txtlogd.conf].

   * Se você especificou [!DNL ServerAddress] usando um nome de servidor, tente usar seu endereço IP numérico. O valor do [!DNL CertName] parâmetro corresponde exatamente ao nome comum que aparece no certificado digital do Insight Server de destino.

## Adicione o transmissor ao script de inicialização do sistema {#section-4e1ffa6e043941ab91411d91d596477a}

Informações para garantir que o transmissor seja carregado automaticamente quando a máquina do servidor da Web for reiniciada.

Adicione o seguinte comando (que inicia o transmissor) ao script de inicialização do sistema.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Esse comando inicia o transmissor como um daemon. As mensagens de erro e de operação geradas pelo transmissor são gravadas no syslog.

>[!NOTE]
>
>Alguns usuários do Solaris podem encontrar um erro &quot;não é possível adquirir mutex&quot;. Para que o Sensor funcione corretamente nesses sistemas, a seguinte linha precisa ser adicionada ou editada no arquivo /etc/system: >
>
```>
>semsys:seminfo_semmnu=1024
>```>
>The default Solaris setting is 60. Based on tests conducted with Sensor, which uses three semaphores for each instance, Adobe recommends that you use 1024 as your setting. This number is high enough for Sensor to function along with any other applications on the server that may require semaphores, but does not affect performance. To support this recommendation, please note that Adrian Cockcroft stated the following in his book Sun Performance and Tuning (Prentice Hall, October 1994): “Databases tend to use lots of shared memory and semaphore settings. These do not affect performance; as long as they are big enough, the programs will run.”



