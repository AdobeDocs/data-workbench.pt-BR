---
description: Informações sobre os códigos e formatos de fuso horário.
solution: Analytics
title: Códigos de fuso horário
topic: Data workbench
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Códigos de fuso horário{#time-zone-codes}

Informações sobre os códigos e formatos de fuso horário.

A maioria dos parâmetros baseados em tempo no servidor da análise de big data são especificados no seguinte formato:

* Mês DD , AAAA HH :MM :SS TZone
* Exemplo: 13 de agosto de 2013 22:30:00 EST

Os fusos horários são expressos em um formato de fuso horário independente do sistema (Hora Universal Coordenada) com o seguinte formato:

* Regras UTC + hhmm

O sinal (+) pode ser um sinal de mais (+) ou um sinal de menos (-), e hhmm é o deslocamento de UTC em horas e minutos. As regras de variável opcionais especificam um conjunto de regras para implementar o Horário de verão ou uma política de mudança de relógio semelhante.

Se você especificar regras, um arquivo delimitado por tabulação nomeado [!DNL dstrules.dst] [!DNL Base] deverá estar presente no diretório Dataset\TimeZone do perfil (para arquivos de configuração que não estejam associados a um conjunto de dados específico) ou no perfil do conjunto de dados (para arquivos de configuração que sejam específicos do conjunto de dados). O arquivo especifica um conjunto de regras independente de fuso horário para o Horário de verão. Você pode ter diferentes conjuntos de regras para anos diferentes. O [!DNL DST.dst] arquivo fornecido pela Adobe no [!DNL Base] perfil especifica as regras padrão dos EUA estabelecidas pelo Energy Policy Act de 2005 (em vigor a partir de 2007) e as regras dos EUA para anos anteriores.

As entradas de exemplo de fuso horário estão listadas abaixo:

* Horário de Verão do Leste dos EUA: Fuso horário = string: UTC -0500 DST
* Hora UTC sem deslocamento e sem regras (correspondente ao GMT): Fuso horário = string: UTC -0000

Quando esse formato é usado, o fuso horário do sistema do servidor de análise de big data, da análise de big data e dos computadores de relatório não precisa ser o mesmo que o fuso horário especificado. Além disso, todos os perfis de conjunto de dados ativos em uma máquina de servidor de análise de big data não precisam ter a mesma configuração de fuso horário.

A tabela a seguir contém a lista de códigos que você pode usar para especificar fusos horários nos parâmetros baseados em tempo.

## Tabela de códigos de fuso horário {#section-b4f965b872c543e2ac52a3c94410d076}

Se você estiver implementando o Horário de verão ou uma política de mudança de relógio semelhante, é necessário salvar o [!DNL .dst] arquivo que contém as regras apropriadas no diretório de nome [!DNL \Dataset\Timezone] do perfil na máquina do servidor da análise de big data.

| Código | Fuso Horário | Deslocamento do GMT |
|---|---|---|
| gmt | Greenwich Mean | 0 |
| est | Padrão oriental | 5 |
| edt | Horário de Verão Oriental | 5 |
| custo | Padrão Central | 6 |
| cdt | Luz de Verão Central | 6 |
| mst | Padrão de Montanha | 7 |
| mdt | Hora de Verão das Montanhas | 7 |
| pst | Padrão do Pacífico | 8 |
| pdt | Horário de Verão do Pacífico | 8 |

