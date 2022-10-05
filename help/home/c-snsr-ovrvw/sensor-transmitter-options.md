---
description: Informações sobre os comandos de inicialização do transmissor do sensor para UNIX e para Windows.
title: Opções de linha de comando do transmissor do sensor
uuid: 8d077d76-a709-494e-a176-07ca3e761662
exl-id: f4b27859-8fab-42cd-bad0-b32f87764668
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 6%

---

# Opções de linha de comando do transmissor do sensor{#sensor-transmitter-command-line-options}

{{eol}}

Informações sobre os comandos de inicialização do transmissor do sensor para UNIX e para Windows.

## Comando de inicialização para UNIX {#section-e8e7a6e62971499ba5f633d896590949}

Para iniciar o transmissor do sensor em um sistema UNIX, use o seguinte comando:

```
txlogd -f configFileName
```

onde configFileName é o nome totalmente qualificado do arquivo de configuração do transmissor (txlogd.conf).

Por padrão, o transmissor é executado como um processo em segundo plano (um daemon) e grava mensagens operacionais no syslog.

Veja a seguir uma lista completa dos switches de linha de comando para txlogd:

| Switch | Descrição |
|---|---|
| -f | Especifica o nome totalmente qualificado do arquivo de configuração (txlogd.conf). Se você não especificar esse switch, o transmissor procura txlogd.conf no diretório atual. |
| -n | Inicia o transmissor no modo interativo (não como um processo em segundo plano). |
| -i | Inicia o transmissor no modo interativo e direciona a saída de depuração para stdout. |
| -d | Inicia o transmissor como um processo em segundo plano e direciona a saída de depuração para txlogd-debug.log no diretório atual. |
| -c | Inicia o transmissor e cria o arquivo de fila de discos se ele não existir. Se a fila de discos já existir, esse parâmetro será ignorado. |
| -x | Inicia o transmissor e faz com que ele saia depois de transmitir o último pacote na fila de discos. Você pode usar essa opção para desenhar a fila em preparação para uma operação administrativa, como criar um novo arquivo de fila. |

## Comando de Inicialização para Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

Para iniciar o Sensor e registrá-lo como um serviço em um sistema Windows, use o seguinte comando:

```
txlog /regserver
```
