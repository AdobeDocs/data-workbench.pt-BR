---
description: O Sensor automatiza a aquisição de dados do seu canal de Internet, eliminando a maior parte da mão de obra humana tradicionalmente envolvida na coleta de dados.
title: Como funciona o processo de coleta de dados?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# Como funciona o processo de coleta de dados?{#how-does-the-data-collection-process-work}

{{eol}}

O Sensor automatiza a aquisição de dados do seu canal de Internet, eliminando a maior parte da mão de obra humana tradicionalmente envolvida na coleta de dados.

Em muitos casos, usando [!DNL Sensor] O pode simplificar muito seu processo de gerenciamento de dados.

Os grandes sites da Internet, da extranet e da intranet de hoje em dia geralmente são executados em uma matriz de servidores da Web. Os registros e dados produzidos podem ser muito grandes e pesados para gerenciar. Por exemplo, se seu site estiver executando 30 servidores da Web, normalmente um dos seus funcionários (ou funcionários de provedores de serviços terceirizados) obteria e consolidaria cada arquivo de log em cada um dos 30 servidores e, em seguida, executaria relatórios sobre eles. Instalar [!DNL Sensor] em cada um dos servidores da Web automatiza todo esse processo, reduzindo suas despesas e disponibilizando dados em tempo real.

Para automatizar esse processo, [!DNL Sensor] coleta informações brutas sobre o tráfego em um site diretamente de cada servidor da Web. Os dados brutos que [!DNL Sensor] captures é chamado de dados de evento e é semelhante ao tipo de dados que seu servidor da Web registra em seus arquivos de log.

Para capturar esses dados, a instrumentação do [!DNL Sensor] registra informações sobre cada solicitação HTTP que o servidor da Web processa. [!DNL Sensor] em seguida, armazena em buffer as informações para proteção contra falha de rede e transmite com segurança as informações via HTTP/S para o [!DNL data workbench server] que você especificar.

Depois que a variável [!DNL data workbench server] O recebe os dados, processa e armazena seus arquivos de log em arquivos altamente compactados [!DNL .vsl] formatar arquivos, permitindo que você mantenha facilmente grandes quantidades de dados em hardware barato.

Para obter informações sobre os campos de dados do evento coletados por [!DNL Sensor] em [!DNL .vsl] arquivos, consulte [Campos de registro de dados do evento](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
