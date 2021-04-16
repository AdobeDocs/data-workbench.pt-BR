---
description: O sensor permite adquirir dados de solicitação da Web (dados de evento ou log), bem como dados de medição estendida.
title: Que tipo de dados posso adquirir?
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
exl-id: 97d87084-cac3-4a94-89e0-f01a66e20324
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# Que tipo de dados posso adquirir?{#what-kind-of-data-can-i-acquire}

O sensor permite adquirir dados de solicitação da Web (dados de evento ou log), bem como dados de medição estendida.

Os dados de medição estendida não estão disponíveis para os servidores da Web como parte de sua operação normal.

Os seguintes tópicos estão descritos:

## Dados de solicitação da Web {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] permite que os dados de solicitação da web (dados de evento ou log) sejam adquiridos e transportados automaticamente para um local central para armazenamento e processamento para análise. A menos que você escolha especificamente filtrar determinados tipos de solicitações e não coletar dados sobre esses tipos de solicitações, [!DNL Sensor] captura dados sobre todas as solicitações do GET feitas dos servidores da Web em que ele está instalado.

[!DNL Sensor] O automatiza esse processo de aquisição de dados para todas as solicitações do GET feitas em seus servidores e tem benefícios significativos de negócios e técnicos em relação a métodos alternativos de aquisição de dados de solicitação de site. Esses benefícios incluem:

* As solicitações desnecessárias para análise e geração de relatórios podem ser filtradas antes de você incorrer em custos para aquisição, transporte, armazenamento e processamento.
* Os administradores de site não precisam girar arquivos de log em lote, manualmente ou por meio de script.
* [!DNL Sensor] agrega arquivos de log em um local central para permitir acesso fácil para processamento.
* [!DNL Sensor] O organiza e armazena arquivos de log em um formato comum de preservação de dados, removendo a necessidade de pré-processá-los antes que possam ser usados para fins de análise e relatórios.
* Instâncias de determinados tipos de conteúdo podem ser incluídas nos arquivos de log, mesmo que a maioria das solicitações de um determinado tipo de conteúdo seja automaticamente filtrada.
* [!DNL Sensor] compacta as entradas do arquivo de log, o que requer significativamente menos espaço de armazenamento, reduzindo custos e permitindo que os dados sejam mantidos disponíveis para análise por períodos mais longos.
* [!DNL Sensor’s] os recursos tolerantes a falhas permitem falhas do sistema e da rede, além de garantir a entrega dos dados de log em um repositório central.
* [!DNL Sensor] permite a implementação de experimentos controlados com conteúdo da Web, processos e campanhas de marketing.
* [!DNL Sensor] carimbos de data e hora registram entradas em unidades de 100ns, permitindo novos tipos de funcionalidade analítica.
* [!DNL Sensor] permite que os proprietários do site adicionem dados (medidas) às entradas de log após a implementação inicial para consideração em análise e relatório.

Para obter mais informações sobre como adquirir dados de medição estendida, consulte [Adquirir medidas de linha de base](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## Dados de medição estendida {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] também suporta o uso de tags de página (ou solicitações de objeto incorporado) para adquirir dados de medição que não estão disponíveis para seus servidores da Web como parte de sua operação normal. Tags de página geralmente são usadas para medir:

* A exibição de uma página lógica em um site dinâmico.
* A visualização de conteúdo ou anúncios em um site controlado por terceiros.
* A visualização do conteúdo veiculado a partir de um cache de navegador ou CDN.
* Informações detalhadas sobre o navegador de um visitante, incluindo medidas como tempo de carregamento de página, resolução de tela, quais campos de formulário o visitante preencheu e assim por diante.
* Outros dados que de outra forma não são enviados pelos navegadores para os servidores da Web.

[!DNL Sensor] coleta informações colocadas em qualquer solicitação do GET feita em um servidor da Web em execução  [!DNL Sensor]. Essas solicitações podem vir de solicitações de objetos incorporados de qualquer tipo, seja para simplesmente medir que a solicitação foi feita em um determinado momento por um determinado navegador ou para passar outros dados de medição para o fluxo de coleta de dados, de modo que possa ser processada para fins de análise e relatórios.

[!DNL Sensor] O oferece o melhor dos mundos de aquisição de dados do lado do cliente e do lado do servidor — ele adquire seus dados de log da Web do lado do servidor e coleta medições do lado do cliente, de terceiros ou de substituição de cache realizadas por solicitações de objetos incorporados. Em outras palavras, [!DNL Sensor] adquire os dados de solicitação normalmente conhecidos dos seus servidores da Web (medições do lado do servidor) e quaisquer dados de medição adicionais que você coleta usando tags de página (medidas do lado do cliente) que enviam seus dados para qualquer servidor da Web que esteja executando [!DNL Sensor]. Esses servidores da Web podem ser dedicados à coleta de medidas do lado do cliente, mas não precisam ser.

Para obter mais informações sobre como adquirir dados de medição estendida, consulte [Adquirir Medições Estendidas](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944).
