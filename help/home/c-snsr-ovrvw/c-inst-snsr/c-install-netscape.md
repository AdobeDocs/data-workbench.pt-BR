---
description: Instruções para instalar e configurar o Sensor na família de servidores da Web que evoluíram do Netscape Enterprise Web Server original em execução em máquinas Linux ou Solaris. Inclui Netscape Enterprise, iPlanet, Sun ONE e Sun Java System Servers no Linux ou Solaris.
title: Netscape Enteprise no Linux ou Solaris
uuid: 47ea614c-d45c-4ab4-a8fe-ed9227da4582
exl-id: bd2e50b9-94fe-4f05-b227-11e83eb0a665
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 1%

---

# Netscape Enteprise no Linux ou Solaris{#netscape-enteprise-on-linux-or-solaris}

{{eol}}

Instruções para instalar e configurar o Sensor na família de servidores da Web que evoluíram do Netscape Enterprise Web Server original em execução em máquinas Linux ou Solaris. Inclui Netscape Enterprise, iPlanet, Sun ONE e Sun Java System Servers no Linux ou Solaris.

Os arquivos de programa do Sensor são empacotados em um arquivo de instalação obtido do site de download do Adobe. Se você ainda não tiver o arquivo de instalação do Sensor para seu servidor da Web específico, baixe-o (ou obtenha-o do representante do Adobe) antes de começar os seguintes procedimentos.

O sensor é compatível com os seguintes servidores em execução no RedHat Linux 7.x ou posterior ou com o Sun Solaris SPARC 2.6 ou posterior:

* Netscape Enterprise Server 3.6 ou posterior
* iPlanet Web Server 4.0 ou posterior

O sensor é compatível com esses servidores em execução no RedHat Linux 7.x ou posterior ou no Sun Solaris 8.x ou posterior:

* Sun ONE Web Server 6.0 ou posterior
* Sun Java System Web Server 6.1 ou posterior

O sensor é compatível com esses servidores em execução no Sun Solaris x86 9 ou posterior:

* Sun Java System Web Server 6.1 ou posterior

>[!NOTE]
>
>O arquivo de instalação dessa família de servidores da Web é listado como &quot;Netscape Solaris Sensor&quot; ou &quot;Netscape LINUX Sensor&quot; no site de download do Adobe.

Para instalar e configurar o Sensor, execute as seguintes etapas:

## Instalar os arquivos do programa {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedimento para extrair e instalar os arquivos de programa do Sensor.

1. Faça logon como o usuário raiz ou como um usuário com autoridade raiz.
1. Descomprima e descompacte o arquivo de instalação usando o seguinte comando:

   ```
   gunzip installationFilename.tar.gz 
   
       tar -xf installationFilename.tar
   ```

1. Copie os arquivos de programa descompactados para os diretórios identificados na tabela a seguir:

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
   <td colname="col1"> aol_visual_sciences.so </td> 
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

**Permissões nos arquivos do programa**

>[!NOTE]
>
>Permissões incorretas nos arquivos do programa causam a maioria dos problemas encontrados ao instalar o Sensor. Certifique-se de definir as permissões exatamente como declarado nesta seção.
>
>Por padrão, os arquivos de programa no arquivo tar têm as seguintes permissões. Dependendo de como seu sistema está configurado, essas configurações podem ser alteradas (não mascaradas) ao extrair os arquivos. Para redefinir as permissões para as configurações padrão recomendadas, use os comandos chmod abaixo. Verifique se os diretórios nos quais você instalou os arquivos permitem pelo menos esse nível de acesso.

| Arquivo | Permissões padrão | comando chmod |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-r— r— | chmod 664 |
| trust_ca_cert.pem | rw-r— r— | chmod 664 |

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

1. Se o diretório em que está a fila de discos ainda não existir, crie-o. Certifique-se de que o diretório forneça o módulo coletor e o programa transmissor com acesso de leitura/gravação ao arquivo.

   Para obter mais informações sobre as permissões necessárias para os arquivos de fila de disco, consulte Permissões de arquivo UNIX do sensor.
1. No computador em que o Sensor está instalado, execute o seguinte comando para iniciar o transmissor:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * A opção &quot;i&quot; neste comando inicia o transmissor no &quot;modo interativo&quot;. Esse modo exibe mensagens do transmissor na tela e também permite que você interaja com o transmissor usando comandos do teclado.
   * A opção &quot;c&quot; direciona o transmissor para criar a fila de discos.
   * A opção &quot;f&quot; especifica o local do arquivo de configuração.

   Para obter informações adicionais sobre as opções que podem ser usadas ao iniciar o transmissor, consulte Opções de linha de comando do transmissor do sensor.

1. Verifique se o transmissor criou a fila de discos no local especificado no parâmetro QueueFile e do tamanho especificado no parâmetro QueueSize.
1. Se a fila não tiver sido criada corretamente, digite Ctrl+C para encerrar o transmissor e faça o seguinte:

   1. Examine o arquivo txtlogd.conf e verifique se os parâmetros QueueFile e QueueSize estão definidos corretamente.
   1. Verifique se o dispositivo ao qual a fila de discos está atribuída é operacional e tem espaço suficiente disponível para armazenar um arquivo do tamanho especificado no parâmetro QueueSize .
   1. Faça as correções necessárias e repita este procedimento.

## Adicionar o coletor ao servidor AOL {#section-c5b83ae4ebce430aa764f951e849b333}

Para o AOLServer, o coletor é um objeto compartilhado dinâmico que você carrega no processo do servidor da Web.

Para adicionar o coletor ao seu servidor AOL, edite o arquivo de configuração do servidor conforme descrito abaixo e reinicie o servidor AOL. Geralmente, o arquivo de configuração do servidor é chamado de nsd.tcl e está localizado no diretório em que o AOL Server está instalado.

1. Abra o arquivo de configuração em um editor de texto e localize a seguinte seção:

   ```
   ns_section "ns/server/${servername}/modules" 
   ```

1. Adicione a seguinte linha. (Adicione como uma única instrução. Ignorar quebra automática de linha mostrada abaixo.)

   ```
   ns_param aol_visual_sciences /usr/local/aolserver/visual_sciences/aol_visual_sciences.so 
   ```

1. Crie uma nova seção da seguinte maneira.

   ```
   ns_section "ns/server/${servername}/module/aol_visual_sciences"
   ```

1. Nesta nova seção, adicione a linha :

   ```
   ns_param    VisualSciencesConfig    /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Essas linhas diferenciam maiúsculas de minúsculas. Digite-os exatamente como aparecem acima.

1. Reinicie o servidor AOL. O coletor é carregado e começará a coletar dados do evento e gravá-los na fila do disco.

## Teste o sensor {#section-0dae181ef8884f10a57f6cfda8500969}

Verifique se o coletor está coletando dados do evento e se o transmissor os está transmitindo ao servidor Insight de destino.

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
   * Os parâmetros ServerAddress e ServerPort são definidos corretamente em txtlogd.conf. Se você especificou ServerAddress usando um nome de servidor, tente usar seu endereço IP numérico.
   * O valor do parâmetro CertName corresponde exatamente ao nome comum que aparece no certificado digital do servidor Insight de destino.

## Adicionar o transmissor ao script de inicialização do sistema {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informações sobre como carregar automaticamente o transmissor para o script de inicialização do sistema.

Para garantir que o transmissor carregue automaticamente quando a máquina do servidor da Web for reiniciada, adicione o seguinte comando (que inicia o transmissor) ao script de inicialização do sistema:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Esse comando inicia o transmissor como um daemon. Mensagens de erro e de operação que o transmissor gera são gravadas em [!DNL syslog].

A configuração padrão do Solaris é 60. Com base nos testes realizados com o Sensor, que usa três semáforos para cada instância, o Adobe recomenda usar 1024 como configuração. Esse número é alto o suficiente para que o Sensor funcione junto com outros aplicativos no servidor que possam exigir semáforos, mas não afeta o desempenho. Para apoiar esta recomendação, por favor note que Adrian Cockcroft declarou o seguinte em seu livro Sun Performance and Tuning (Prentice Hall, outubro de 1994): &quot;Os bancos de dados tendem a usar muita memória compartilhada e configurações de semáforo. Não afetam o desempenho; desde que sejam suficientemente grandes, os programas serão executados.&quot;
