---
description: O Sensor automatiza a aquisição de dados do seu canal de Internet, eliminando a maior parte da mão de obra humana tradicionalmente envolvida na coleta de dados.
solution: Insight
title: Como funciona o processo de coleta de dados?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como funciona o processo de coleta de dados?{#how-does-the-data-collection-process-work}

O Sensor automatiza a aquisição de dados do seu canal de Internet, eliminando a maior parte da mão de obra humana tradicionalmente envolvida na coleta de dados.

Em muitos casos, o uso [!DNL Sensor] pode simplificar muito seu processo de gerenciamento de dados.

Os grandes sites da Internet, da extranet e da intranet de hoje em dia são executados em uma matriz de servidores da Web. Os registros e dados produzidos podem ser muito grandes e complicados de gerenciar. Por exemplo, se seu site estiver executando 30 servidores da Web, normalmente um dos seus funcionários (ou funcionários do provedor de serviços terceirizado) obteria e consolidaria cada arquivo de log em cada um dos 30 servidores e, em seguida, executaria relatórios sobre eles. A instalação [!DNL Sensor] em cada um dos seus servidores web automatiza todo esse processo, reduzindo suas despesas e disponibilizando os dados em tempo real.

Para automatizar esse processo, [!DNL Sensor] coleta informações brutas sobre o tráfego em um site diretamente de cada servidor da Web. Os dados brutos que [!DNL Sensor] capturam são chamados de dados de evento e são semelhantes ao tipo de dados que seu servidor da Web registra em seus arquivos de log.

Para capturar esses dados, a instrumentação em [!DNL Sensor] registros registra informações sobre cada solicitação HTTP processada pelo servidor da Web. [!DNL Sensor] em seguida, armazena as informações em buffer para protegê-las contra falhas de rede e transmite com segurança as informações via HTTP/S para o [!DNL data workbench server] que você especificar.

Após a [!DNL data workbench server] recepção dos dados, ele processa e armazena seus arquivos de registro em arquivos de [!DNL .vsl] formato altamente compactados, permitindo que você mantenha facilmente grandes quantidades de dados em hardware barato.

Para obter informações sobre os campos de dados do evento coletados [!DNL Sensor] em [!DNL .vsl] arquivos, consulte Campos [de registro de dados do](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)evento.
