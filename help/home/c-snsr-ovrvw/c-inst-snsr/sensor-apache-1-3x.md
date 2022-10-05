---
description: Instruções detalhadas para instalar e configurar o Sensor para um Apache Server 1.3.x no RedHat Linux 7.x ou posterior, SUSE Linux 9.x ou posterior, Sun Solaris SPARC 2.6 ou posterior, Sun Solaris x86 9 ou posterior, FreeBSD 4 ou posterior ou Mac OS X PowerPC.
title: Apache Server 1.3.x no Linux, Sun Solaris, FreeBSD ou Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---

# Apache Server 1.3.x no Linux, Sun Solaris, FreeBSD ou Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

{{eol}}

Instruções detalhadas para instalar e configurar o Sensor para um Apache Server 1.3.x no RedHat Linux 7.x ou posterior, SUSE Linux 9.x ou posterior, Sun Solaris SPARC 2.6 ou posterior, Sun Solaris x86 9 ou posterior, FreeBSD 4 ou posterior ou Mac OS X PowerPC.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação obtido do site de download do Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor da Web específico, baixe-o (ou obtenha-o do representante do Adobe) antes de começar os seguintes procedimentos.

Para instalar e configurar o Sensor, você deve executar as seguintes etapas de alto nível:

## Instalar os arquivos do programa {#section-aae323e252394212bf4096d65fdd280c}

Instruções para extrair e instalar os arquivos de programa do Sensor na máquina do servidor.

1. Faça logon como o usuário raiz ou como um usuário com autoridade raiz.
1. Descomprima e descompacte o arquivo de instalação usando o seguinte comando:

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
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
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
>O pacote de instalação contém um arquivo de planilha chamado TestExperiment.xls. Esta planilha é uma ferramenta que os arquitetos usam para configurar um experimento controlado. O próprio sensor não usa esse arquivo, portanto, não é necessário instalar o arquivo na máquina em que o Sensor está sendo executado (embora você possa optar por fazê-lo). Em vez disso, você pode querer copiar o arquivo para um local onde seus arquitetos possam acessá-lo ou simplesmente extrair o arquivo do pacote de instalação, conforme necessário. Para obter mais informações sobre experimentação controlada, consulte o Guia de experimentos controlados do Insight.

**Permissões nos arquivos do programa**

Permissões incorretas nos arquivos do programa causam a maioria dos problemas encontrados ao instalar o Sensor.

Certifique-se de definir as permissões exatamente como declarado nesta seção.

Por padrão, os arquivos de programa no arquivo tar têm as seguintes permissões. Dependendo de como seu sistema está configurado, essas configurações podem ser alteradas (não mascaradas) ao extrair os arquivos. Para redefinir as permissões para as configurações padrão recomendadas, use os comandos chmod abaixo. Verifique se os diretórios nos quais você instalou os arquivos permitem pelo menos esse nível de acesso.

| Arquivo | Permissões padrão | comando chmod |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Editar o arquivo de configuração do Sensor {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

O [!DNL txlogd.conf] contém os parâmetros de configuração do Sensor.

Você deve editar o arquivo para especificar, entre outras coisas, o tamanho da fila de disco, o endereço do servidor Insight e a ID que será anexada aos dados produzidos por esse sensor.

O arquivo de configuração contém parâmetros obrigatórios e parâmetros opcionais.

* Os parâmetros obrigatórios são configurações que você deve especificar ao instalar o Sensor. Sem essas configurações, o Sensor não é executado com êxito.
* Parâmetros opcionais são configurações padrão para valores predefinidos (que podem ser modificados) ou ativar recursos opcionais.

Para editar o arquivo de configuração do Sensor

1. Abra o arquivo /etc/txlogd.conf em um editor de texto e defina os parâmetros necessários, bem como quaisquer parâmetros opcionais desejados.
1. Salve e feche o arquivo.

## Inicie o transmissor e crie a fila de discos {#section-a453d912ec3d47aa8e40ccacf527119d}

Instruções para criar a fila do disco depois de configurar o arquivo txlogd.conf.

1. Se o diretório em que está a fila de discos ainda não existir, crie-o. Certifique-se de que o diretório forneça o módulo coletor e o programa transmissor com acesso de leitura/gravação ao arquivo.
1. No computador em que o Sensor está instalado, execute o seguinte comando para iniciar o transmissor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * A opção &quot;i&quot; neste comando inicia o transmissor no modo interativo. Esse modo exibe mensagens do transmissor na tela e também permite que você interaja com o transmissor usando comandos do teclado.
   * A opção &quot;c&quot; direciona o transmissor para criar a fila de discos.
   * A opção &quot;f&quot; especifica o local do arquivo de configuração.

1. Verifique se o transmissor criou a fila de discos no local especificado no parâmetro QueueFile e do tamanho especificado no parâmetro QueueSize.
1. Se a fila não tiver sido criada corretamente, digite Ctrl+C para encerrar o transmissor e faça o seguinte:

   1. Examine o arquivo txtlogd.conf e verifique se os parâmetros QueueFile e QueueSize estão definidos corretamente.
   1. Verifique se o dispositivo ao qual a fila de discos está atribuída é operacional e tem espaço suficiente disponível para armazenar um arquivo do tamanho especificado no parâmetro QueueSize .
   1. Faça as correções necessárias e repita este procedimento.

## Adicionar o Coletor ao Servidor Web {#section-a7fb6425956f4f518ae3a7db091b33d2}

Para servidores Apache, o coletor é um objeto compartilhado dinâmico que você carrega no processo do servidor da Web.

Para adicionar o coletor ao seu servidor da Web, edite o arquivo httpd.conf conforme descrito abaixo e reinicie o servidor da Web.

Se o Sensor estiver capturando dados de vários servidores da Web no computador servidor, você deverá executar o seguinte procedimento para cada servidor da Web.

1. Usando um editor de texto, abra o [!DNL httpd.conf] arquivo para o servidor da Web cujos eventos o Sensor captura.
1. Adicione as seguintes linhas ao final do arquivo :

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Essas linhas diferenciam maiúsculas de minúsculas. Digite-os exatamente como aparecem acima.

1. Reinicie o servidor da Web. O coletor é carregado com o servidor da Web e começará a coletar dados do evento e gravá-los na fila do disco.

## Teste o sensor {#section-83d9f60b39a6474f9c76bee3e19b2575}

Inicie o transmissor e verifique se ele pode se conectar com êxito ao Servidor Insight e transmitir dados do evento para ele.

>[!NOTE]
>
>Para verificar se o transmissor pode enviar dados de evento com êxito para o servidor Insight, verifique se o servidor Insight de destino está instalado e em execução antes de iniciar o teste a seguir.

1. Se o transmissor ainda não estiver em execução, reinicie-o usando o seguinte comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Abra um navegador (em qualquer máquina) e solicite uma página do servidor da Web em que o Sensor está sendo executado (certifique-se de selecionar uma página que o Sensor esteja monitorando).
1. Depois de emitir a solicitação, verifique o console do transmissor quanto a mensagens indicando que ele está enviando dados do evento para o servidor Insight de destino.
1. Se o sensor não estiver transmitindo os dados com êxito, verifique se:

   * O Servidor Insight de destino está em execução.
   * O [!DNL ServerAddress] e [!DNL ServerPort] são definidos corretamente em [!DNL txtlogd.conf].

   * Se você especificou [!DNL ServerAddress] usando um nome de servidor, tente usar seu endereço IP numérico. O valor da variável [!DNL CertName] corresponde exatamente ao nome comum que aparece no certificado digital do servidor Insight de destino.

## Adicione o transmissor ao script de inicialização do sistema {#section-4e1ffa6e043941ab91411d91d596477a}

Informações para garantir que o transmissor carregue automaticamente quando a máquina do servidor da Web for reiniciada.

Adicione o seguinte comando (que inicia o transmissor) ao script de inicialização do sistema.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Esse comando inicia o transmissor como um daemon. Mensagens de erro e operacionais geradas pelo transmissor são gravadas no syslog.

>[!NOTE]
>
>Alguns usuários do Solaris podem encontrar um erro &quot;não é possível adquirir mutex&quot;. Para que o Sensor funcione corretamente nesses sistemas, a linha a seguir precisa ser adicionada ou editada no arquivo /etc/system:
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>A configuração padrão do Solaris é 60. Com base nos testes realizados com o Sensor, que usa três semáforos para cada instância, o Adobe recomenda usar 1024 como configuração. Esse número é alto o suficiente para que o Sensor funcione junto com outros aplicativos no servidor que possam exigir semáforos, mas não afeta o desempenho. Para apoiar esta recomendação, por favor note que Adrian Cockcroft declarou o seguinte em seu livro Sun Performance and Tuning (Prentice Hall, outubro de 1994): &quot;Os bancos de dados tendem a usar muita memória compartilhada e configurações de semáforo. Não afetam o desempenho; desde que sejam suficientemente grandes, os programas serão executados.&quot;
