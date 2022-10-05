---
description: 'O sensor consiste em três componentes principais: Coletor de dados, Fila de disco e Transmissor de dados.'
title: O que são componentes básicos
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
exl-id: aee6a601-590a-43e0-aeeb-42a4522e55c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 0%

---

# O que são componentes básicos{#what-are-basic-components}

{{eol}}

O sensor consiste em três componentes principais: Coletor de dados, fila de disco e transmissor de dados.

![](assets/Visual-Sensor.png)

## Coletor de dados {#section-f970eaff30364a3c8106d5ec9c1b5caa}

O coletor de dados (coletor) é um NSAPI, ISAPI, servlet de filtro J2EE ou módulo Apache que é executado no processo do servidor da Web.

Ele captura os dados brutos do evento sobre cada solicitação HTTP que o servidor da Web processa e deposita essas informações na fila de discos. Se você executar várias instâncias de um servidor da Web na mesma máquina, cada instância carregará sua própria instância do módulo coletor; no entanto, todas as instâncias do coletor gravam seus dados de evento na mesma fila do disco.

## Fila de disco {#section-41aac77ab30e48478d1b31eac288df05}

A fila de discos (fila) é um arquivo de fila com mapeamento de memória FIFO (primeiro a entrar, primeiro a sair) que armazena em buffer os dados brutos do evento que o Sensor coleta, fornecendo armazenamento temporário para os dados do evento coletados no servidor da Web em que está instalado.

Para impedir que a fila se expanda sem restrições (e, portanto, consumindo todo o espaço em disco disponível), ela é mantida em um arquivo de tamanho fixo, o que significa que ela retém apenas tantos dados de evento quanto a capacidade de retenção que lhe foi dada. O tamanho do arquivo de fila é configurado no parâmetro QueueSize do arquivo de configuração do Sensor, txlogd.conf, quando o Sensor é instalado. Para obter informações sobre os parâmetros txlogd.conf, consulte Parâmetros do arquivo Txlogd.conf do sensor.

Depois de estabelecido, o comprimento físico do arquivo não aumenta ou diminui. O coletor simplesmente deposita novos dados de evento na fila e o transmissor extrai eventos dela. Se o coletor atingir o fim do arquivo, ele para de gravar no arquivo da fila.

Geralmente, o transmissor extrai eventos da fila assim que o coletor os deposita. No entanto, se a conexão entre o transmissor e o servidor Insight for lenta ou indisponível, a fila poderá preencher com eventos não transmitidos. Nesse caso, o coletor para de coletar dados até que o transmissor desenha a fila. As informações sobre solicitações que o servidor da Web processa durante esse período são perdidas permanentemente.

**Determinando o tamanho da fila**

Antes de instalar o Sensor, é necessário determinar o tamanho da fila. Para evitar a perda permanente de dados, é importante criar uma fila grande o suficiente para acomodar o número de eventos que podem ser acumulados durante a interrupção mais longa provável da conexão com o Insight Server (ou seja, armazenamento suficiente para vários dias de atividade de pico). A fila deve ser configurada para conter dados de evento suficientes para que os administradores do sistema tenham tempo para restaurar a acessibilidade da rede para o Servidor Insight de destino, ou reparar ou substituir o Servidor Insight sem perder dados. Se o sensor tiver falhado e um arquivo de fila válido e acessível não estiver disponível para armazenar os dados do evento, os dados subsequentes serão perdidos.

>[!NOTE]
>
>É importante que os administradores de cada máquina na qual o Sensor é executado entendam a natureza exclusiva do arquivo de fila local para garantir que eles não o tratem como um arquivo de log comum que pode ser excluído, arquivado ou compactado.

O Adobe recomenda que a fila seja configurada para conter pelo menos dez (10) dias de pico de dados do evento produzidos pelo servidor onde o Sensor está instalado. Ou seja, pegue a quantidade de dados do evento de qualquer dia de pico no último ano e multiplique-a por dez.

Essa recomendação pressupõe o seguinte:

* A equipe de Tecnologia da Informação de sua empresa está monitorando cada Sensor da maneira detalhada no Sensor de administração deste guia e está fazendo isso pelo menos uma vez por dia. Se tal não for o caso, esse prazo deve ser prorrogado de forma adequada.
* A equipe de Tecnologia da Informação de sua empresa pode restaurar a acessibilidade da rede ou substituir ou reparar quaisquer Servidores Insight instalados dentro de 72 horas. Se tal não for o caso, esse prazo deve ser prorrogado de forma adequada.
* A configuração do Sensor permanece a mesma.
* Nenhum evento externo (por exemplo, uma grande campanha de marketing) fará com que a quantidade de dados do evento gerados pelos servidores da Web aumente significativamente.

Sua escolha do tamanho da fila depende, em grande parte, do nível desejado de monitoramento do sistema, à luz das práticas e políticas de sua empresa relacionadas aos tempos de resposta e à administração do sistema de fim de semana/feriado. À medida que os tamanhos de fila maiores forem melhores, o Adobe recomenda que sua empresa torne a fila o maior possível.

>[!NOTE]
>
>Os tamanhos maiores dos arquivos da fila não afetam o desempenho.

Para obter mais recomendações sobre como dimensionar a fila, entre em contato com os Serviços de consultoria da Adobe.

## Transmissor de dados {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

O transmissor é um processo independente (por exemplo, um daemon em um computador baseado em UNIX ou um serviço em um computador Windows) que é executado na mesma máquina que o servidor Web.

O transmissor lê os dados do evento da fila do disco, compacta-os e os envia via HTTP/S para o Servidor Insight especificado, onde são processados e armazenados em **.vsl** arquivos.
