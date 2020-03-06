---
description: 'O sensor consiste em três componentes principais: Coletor de dados, Fila de disco e Transmissor de dados.'
title: O que são componentes básicos
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# O que são componentes básicos{#what-are-basic-components}

O sensor consiste em três componentes principais: Coletor de dados, Fila de disco e Transmissor de dados.

![](assets/Visual-Sensor.png)

## Coletor de dados {#section-f970eaff30364a3c8106d5ec9c1b5caa}

O coletor de dados (coletor) é um servidor de filtro NSAPI, ISAPI, J2EE ou módulo Apache que é executado no processo do servidor da Web.

Ele captura os dados brutos do evento sobre cada solicitação HTTP que o servidor da Web processa e deposita essas informações na fila de discos. Se você executar várias instâncias de um servidor da Web na mesma máquina, cada instância carregará sua própria instância do módulo coletor; no entanto, todas as instâncias do coletor gravam seus dados de evento na mesma fila de discos.

## Fila de disco {#section-41aac77ab30e48478d1b31eac288df05}

A fila de discos (fila) é tolerante a falhas, o FIFO (primeira entrada, primeira saída) arquivo de fila mapeado por memória que armazena em buffer os dados brutos do evento que o Sensor coleta, fornecendo armazenamento temporário para os dados coletados do evento no servidor da Web em que está instalado.

Para impedir que a fila se expanda sem restrições (consumindo, assim, todo o espaço em disco disponível), a fila é mantida em um arquivo de tamanho fixo, o que significa que ela armazena apenas a quantidade de dados do evento que lhe foi dada capacidade de retenção. O tamanho do arquivo de fila é configurado no parâmetro QueueSize do arquivo de configuração do Sensor, txlogd.conf, quando o Sensor é instalado. Para obter informações sobre os parâmetros txlogd.conf, consulte Parâmetros de arquivo Txlogd.conf do sensor.

Uma vez estabelecida, a duração física do arquivo não aumenta nem diminui. O coletor simplesmente deposita novos dados de eventos na fila e o transmissor retira os eventos dela. Se o coletor chegar ao final do arquivo, ele interrompe a gravação no arquivo da fila.

Geralmente, o transmissor retira eventos da fila tão rápido quanto o coletor os deposita. No entanto, se a conexão entre o transmissor e o Insight Server for lenta ou indisponível, a fila poderá preencher com eventos não transmitidos. Nesse caso, o coletor para de coletar dados até que o transmissor desenha a fila. As informações sobre solicitações que o servidor da Web processa durante esse tempo são perdidas permanentemente.

**Determinando o tamanho da fila**

Antes de instalar o Sensor, é necessário determinar o tamanho da fila. Para evitar perda permanente de dados, é importante criar uma fila grande o suficiente para acomodar o número de eventos que podem ser acumulados durante a interrupção mais longa provável da conexão com o Insight Server (ou seja, armazenamento suficiente para vários dias de atividade de pico). A fila deve ser configurada para conter dados de evento suficientes para que os administradores do sistema tenham tempo para restaurar a acessibilidade da rede para o Insight Server de destino, ou reparar ou substituir o Insight Server sem perder dados. Se o sensor falhar e um arquivo de fila válido e acessível não estiver disponível para reter os dados do evento, os dados subsequentes serão perdidos.

>[!NOTE]
>
>É importante que os administradores de cada máquina em que o Sensor é executado entendam a natureza exclusiva do arquivo de fila local para garantir que eles não o tratem como um arquivo de log comum que pode ser excluído, arquivado ou compactado.

A Adobe recomenda que a fila seja configurada para conter pelo menos dez (10) dias de pico de dados de eventos produzidos pelo servidor em que o sensor está instalado. Ou seja, pegue a quantidade de dados de eventos de qualquer dia de pico no último ano e multiplique-os em dez.

Essa recomendação presume o seguinte:

* A equipe de Tecnologia da Informação de sua empresa está monitorando cada Sensor da maneira detalhada em Administrando o Sensor deste guia e está fazendo isso pelo menos uma vez por dia. Se tal não for o caso, este prazo deverá ser prorrogado de forma adequada.
* A equipe de Tecnologia da Informação de sua empresa pode restaurar a acessibilidade da rede ou substituir ou reparar qualquer servidor Insight instalado em até 72 horas. Se tal não for o caso, este prazo deverá ser prorrogado de forma adequada.
* A configuração do sensor continua a mesma.
* Nenhum evento externo (por exemplo, uma grande campanha de marketing) fará com que a quantidade de dados de evento que está sendo gerada pelos servidores da Web aumente significativamente.

A escolha do tamanho da fila depende, em grande parte, do nível desejado de monitoramento do sistema, à luz das práticas e políticas da sua empresa relacionadas aos tempos de resposta e administração do sistema de fim de semana/feriado. Como os tamanhos maiores de fila são melhores, a Adobe recomenda que sua empresa torne a fila o maior possível.

>[!NOTE]
>
>Os tamanhos maiores de arquivos de fila não afetam o desempenho.

Para obter mais recomendações sobre como dimensionar a fila, entre em contato com os Serviços de consultoria da Adobe.

## Transmissor de dados {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

O transmissor é um processo independente (por exemplo, um daemon em um computador baseado em UNIX ou um serviço em um computador Windows) que é executado na mesma máquina que o servidor da Web.

O transmissor lê os dados do evento da fila de discos, os compacta e os envia via HTTP/S para o Insight Server que você especificou, onde são processados e armazenados em arquivos **.vsl** .
