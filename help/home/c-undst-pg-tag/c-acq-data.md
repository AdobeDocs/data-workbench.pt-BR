---
description: O sensor permite que você adquira dados de solicitação da Web (dados de evento ou registro), bem como dados de medição estendidos.
solution: Analytics
title: Que tipo de dados posso adquirir?
topic: Data workbench
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Que tipo de dados posso adquirir?{#what-kind-of-data-can-i-acquire}

O sensor permite que você adquira dados de solicitação da Web (dados de evento ou registro), bem como dados de medição estendidos.

Os dados de medição estendida não estão disponíveis para seus servidores da Web como parte de sua operação normal.

Os seguintes tópicos estão descritos:

## Dados de solicitação da Web {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] permite que os dados de solicitação da Web (dados de evento ou registro) sejam adquiridos e transportados automaticamente para um local central para armazenamento e processamento para análise. A menos que você escolha filtrar especificamente certos tipos de solicitações e não coletar dados sobre esses tipos de solicitação, [!DNL Sensor] captura dados sobre todas as solicitações GET feitas dos servidores da Web nos quais ele está instalado.

[!DNL Sensor] automatiza esse processo de aquisição de dados para todas as solicitações GET que são feitas em seus servidores e têm benefícios comerciais e técnicos significativos em relação a métodos alternativos de aquisição de dados de solicitação de site. Esses benefícios incluem:

* As solicitações desnecessárias para análise e geração de relatórios podem ser filtradas antes que você incorra em custos para aquisição, transporte, armazenamento e processamento.
* Os administradores do site não precisam girar arquivos de log em lote, manualmente ou por meio de script.
* [!DNL Sensor] agrega arquivos de registro em um local central para permitir acesso fácil para processamento.
* [!DNL Sensor] organiza e armazena arquivos de log em um formato comum de conservação de dados, removendo a necessidade de pré-processá-los antes que possam ser usados para fins de análise e relatório.
* Instâncias de certos tipos de conteúdo podem ser incluídas nos arquivos de log, mesmo que a maioria das solicitações de um determinado tipo de conteúdo sejam filtradas automaticamente.
* [!DNL Sensor] compacta as entradas do arquivo de log, o que requer significativamente menos espaço de armazenamento, reduzindo os custos e permitindo que os dados sejam mantidos disponíveis para análise por períodos de tempo mais longos.
* [!DNL Sensor’s] os recursos tolerantes a falhas permitem falhas no sistema e na rede, ao mesmo tempo em que garantem a entrega dos dados de log para um repositório central.
* [!DNL Sensor] permite a implementação de experimentos controlados com conteúdo da Web, processos e campanhas de marketing.
* [!DNL Sensor] carimbos de data e hora registram entradas em unidades de 100ns, permitindo novos tipos de funcionalidade analítica.
* [!DNL Sensor] permite que os proprietários do site adicionem dados (medidas) às entradas do log após a implementação inicial para consideração na análise e nos relatórios.

Para obter mais informações sobre como adquirir dados de medição estendida, consulte [Aquisição de Medidas](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe)de Linha de Base.

## Dados de medição estendida {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] também suporta o uso de tags de página (ou solicitações de objetos incorporados) para adquirir dados de medição que não estão disponíveis para seus servidores da Web como parte de sua operação normal. As tags de página são normalmente usadas para medir:

* A exibição de uma página lógica em um site dinâmico.
* A exibição de conteúdo ou anúncios em um site controlado por terceiros.
* A exibição do conteúdo que é disponibilizado a partir de um cache do navegador ou CDN.
* Informações detalhadas sobre o navegador de um visitante, incluindo medidas como tempo de carregamento da página, resolução da tela, quais campos de formulário o visitante preencheu e assim por diante.
* Outros dados que não são enviados pelos navegadores para os servidores da Web.

[!DNL Sensor] coleta todas as informações colocadas em qualquer solicitação GET feita em um servidor da Web em execução [!DNL Sensor]. Essas solicitações podem vir de solicitações de objetos incorporados de qualquer tipo, seja para medir simplesmente que a solicitação foi feita em um determinado momento por um determinado navegador ou para passar outros dados de medição para o fluxo de coleta de dados, de modo que possam ser processados para fins de análise e de relatório.

[!DNL Sensor] fornece o melhor dos mundos de aquisição de dados tanto do lado do cliente quanto do lado do servidor — ele adquire seus dados de log da Web do lado do servidor e coleta medidas do lado do cliente, do site de terceiros ou do cache busting obtidas por solicitações de objetos incorporados. Em outras palavras, [!DNL Sensor] adquire os dados de solicitação normalmente conhecidos pelos servidores da Web (medidas do lado do servidor) e quaisquer dados de medição adicionais coletados por meio do uso de tags de página (medidas do lado do cliente) que enviam seus dados para quaisquer servidores da Web em execução [!DNL Sensor]. Esses servidores Web podem ser dedicados à coleta de medidas do lado do cliente, mas não precisam ser.

Para obter mais informações sobre como adquirir dados de medição estendida, consulte [Aquisição de Medidas](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944)Estendidas.
