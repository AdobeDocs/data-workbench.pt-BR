---
description: O parâmetro Fuso horário no arquivo Transformation.cfg controla as dimensões de tempo, as conversões de tempo (por exemplo, definindo o campo x-local-timestring) e a formatação de todas as horas locais no perfil do conjunto de dados.
solution: Analytics
title: Fusos horários
topic: Data workbench
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Fusos horários{#time-zones}

O parâmetro Fuso horário no arquivo Transformation.cfg controla as dimensões de tempo, as conversões de tempo (por exemplo, definindo o campo x-local-timestring) e a formatação de todas as horas locais no perfil do conjunto de dados.

>[!NOTE]
>
>O parâmetro Fuso horário não afeta a funcionalidade no nível do sistema, como carimbos de data e hora em registros de status e eventos, que são expressos no horário local do sistema.

O parâmetro Fuso horário suporta um formato de fuso horário independente do sistema (&quot;Tempo Universal Coordenado&quot;) com o seguinte formato:

Fuso horário = string: Regras UTC + hhmm

O sinal (+) pode ser um sinal de mais (+) ou um sinal de menos (-), e *hhmm* é o deslocamento de UTC em horas e minutos. Os *padrões* de variável opcionais especificam um conjunto de regras para implementar o Horário de verão ou uma política de mudança de relógio semelhante.

Se você especificar *os documentos*, um arquivo delimitado por tabulação chamado [!DNL dstrules .dst] deverá estar presente no subdiretório Dataset\TimeZone do perfil do conjunto de dados. O arquivo especifica um conjunto de regras independente de fuso horário para o Horário de verão. Você pode ter diferentes conjuntos de regras para anos diferentes. O [!DNL DST.dst] arquivo fornecido pela Adobe no perfil básico especifica as regras padrão dos EUA estabelecidas pelo Energy Policy Act de 2005 (em vigor a partir de 2007) e as regras dos EUA para anos anteriores.

As entradas de exemplo de fuso horário estão listadas abaixo:

* Horário de Verão do Leste dos EUA: Fuso horário = string: UTC -0500 DST
* Hora UTC sem deslocamento e sem regras: Fuso horário = string: UTC -0000

Quando esse formato é usado, o fuso horário do sistema do servidor da análise de big data, da análise de big data e das [!DNL Report] máquinas não precisa ser o mesmo que o fuso horário especificado. Além disso, todos os perfis de conjunto de dados ativos em uma máquina de servidor de análise de big data não precisam ter a mesma configuração de fuso horário.

A Adobe não recomenda executar mais de um perfil de conjunto de dados em uma única máquina do servidor de análise de big data ou cluster do servidor de análise de big data.

Os usuários da análise de big data verão os dados no fuso horário do perfil do conjunto de dados em vez do fuso horário do sistema. A Adobe recomenda que o fuso horário do sistema para uma máquina de servidor análise de big data seja o mesmo que o fuso horário usado em seus conjuntos de dados.

>[!NOTE]
>
>Você pode especificar um parâmetro de Fuso horário no [!DNL Log Processing.cfg] arquivo, onde ele é usado para conversões de tempo durante o processamento do log. Para obter informações sobre o parâmetro Fuso horário no [!DNL Log Processing.cfg] arquivo, consulte Arquivo [de configuração de processamento de](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)log.

