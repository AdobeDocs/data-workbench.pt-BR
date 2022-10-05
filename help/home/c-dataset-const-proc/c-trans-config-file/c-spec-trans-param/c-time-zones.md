---
description: O parâmetro Fuso horário no arquivo Transformation.cfg controla as dimensões de tempo, as conversões de tempo (por exemplo, definindo o campo x-local-timestring) e a formatação de todas as horas locais no perfil do conjunto de dados.
title: Fusos horários
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Fusos horários{#time-zones}

{{eol}}

O parâmetro Fuso horário no arquivo Transformation.cfg controla as dimensões de tempo, as conversões de tempo (por exemplo, definindo o campo x-local-timestring) e a formatação de todas as horas locais no perfil do conjunto de dados.

>[!NOTE]
>
>O parâmetro Fuso horário não afeta a funcionalidade no nível do sistema, como carimbos de data e hora em logs de status e eventos, que são expressos em horário local do sistema.

O parâmetro Fuso Horário suporta um formato de fuso horário independente do sistema (&quot;Hora Universal Coordenada&quot;) com o seguinte formato:

Fuso Horário = string: UTC +hhmm

O sinal (+) pode ser um sinal de mais (+) ou um sinal de menos (-) e *hhmm* é o deslocamento do UTC em horas e minutos. A variável opcional *regras* especifica um conjunto de regras para implementar o Horário de verão ou uma política de mudança de relógio semelhante.

Se você especificar *regras*, um arquivo delimitado por tabulação chamado [!DNL dstrules .dst] deve estar presente no subdiretório Dataset\TimeZone do perfil do conjunto de dados. O arquivo especifica um conjunto de regras independente de fuso horário para o horário de verão. Você pode ter diferentes conjuntos de regras para anos diferentes. O [!DNL DST.dst] O arquivo fornecido pelo Adobe no perfil Base especifica as regras padrão dos EUA estabelecidas pelo Energy Policy Act de 2005 (em vigor a partir de 2007) e as regras dos EUA para anos anteriores.

As entradas de fuso horário de exemplo são listadas abaixo:

* Hora de Verão do Leste dos EUA: Fuso Horário = string: UTC -0500 DST
* Hora UTC sem deslocamento e sem regras : Fuso Horário = string: UTC -0000

Quando esse formato é usado, o fuso horário do sistema do servidor do Data Workbench, do Data Workbench e [!DNL Report] máquinas não precisam ser iguais ao fuso horário especificado. Além disso, todos os perfis de conjunto de dados ativos em uma máquina de servidor do Data Workbench não precisam ter a mesma configuração de fuso horário.

O Adobe não recomenda executar mais de um perfil de conjunto de dados em uma única máquina de servidor do Data Workbench ou cluster de servidores do Data Workbench.

Os usuários do Data Workbench verão os dados no fuso horário do perfil do conjunto de dados, em vez do fuso horário do sistema. O Adobe recomenda que o fuso horário do sistema de uma máquina de servidor do Data Workbench seja o mesmo usado em seus conjuntos de dados.

>[!NOTE]
>
>Você pode especificar um parâmetro de Fuso horário na [!DNL Log Processing.cfg] , onde é usado para conversões de tempo durante o processamento do log. Para obter informações sobre o parâmetro Fuso horário na [!DNL Log Processing.cfg] arquivo, consulte [Arquivo de configuração de processamento de log](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
