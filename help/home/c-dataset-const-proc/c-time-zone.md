---
description: Informações sobre os códigos e formatos de Fuso Horário.
title: Códigos e formatos de fuso horário
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 4%

---

# Códigos de fuso horário{#time-zone-codes}

{{eol}}

Informações sobre os códigos e formatos de Fuso Horário.

A maioria dos parâmetros baseados em tempo no servidor do Data Workbench são especificados no seguinte formato:

* Mês DD , AAAA HH :MM :SS TZone
* Exemplo: 13 de agosto de 2013 22:30:00 EST

Os fusos horários são expressos em um formato de fuso horário independente do sistema (Hora Universal Coordenada) com o seguinte formato:

* UTC +hhmm

O sinal (+) pode ser um sinal de mais (+) ou um sinal de menos (-), e hhmm é o deslocamento do UTC em horas e minutos. As regras de variável opcionais especificam um conjunto de regras para implementar o Horário de verão ou uma política de mudança de relógio semelhante.

Se você especificar regras, um arquivo delimitado por tabulação chamado [!DNL dstrules.dst] deve estar presente no diretório Dataset\TimeZone do [!DNL Base] perfil (para arquivos de configuração que não estão associados a um conjunto de dados específico) ou o perfil do conjunto de dados (para arquivos de configuração que são específicos do conjunto de dados). O arquivo especifica um conjunto de regras independente de fuso horário para o horário de verão. Você pode ter diferentes conjuntos de regras para anos diferentes. O [!DNL DST.dst] arquivo fornecido pelo Adobe na [!DNL Base] O perfil especifica as regras padrão dos EUA estabelecidas pelo Energy Policy Act de 2005 (em vigor a partir de 2007) e as regras dos EUA para anos anteriores.

As entradas de fuso horário de exemplo são listadas abaixo:

* Hora de Verão do Leste dos EUA: Fuso Horário = string: UTC -0500 DST
* Horário UTC sem deslocamento e sem desvios (correspondente a GMT): Fuso Horário = string: UTC -0000

Quando esse formato é usado, o fuso horário do sistema do servidor do Data Workbench, do Data Workbench e das máquinas de Relatório não precisa ser o mesmo que o fuso horário especificado. Além disso, todos os perfis de conjunto de dados ativos em uma máquina de servidor do Data Workbench não precisam ter a mesma configuração de fuso horário.

A tabela a seguir contém a lista de códigos que podem ser usados para especificar fusos horários em parâmetros baseados em tempo.

## Tabela de códigos do fuso horário {#section-b4f965b872c543e2ac52a3c94410d076}

Se estiver implementando o Horário de verão ou uma política de mudança de relógio semelhante, você deverá salvar o [!DNL .dst] arquivo contendo as regras apropriadas no nome do perfil [!DNL \Dataset\Timezone] na máquina do servidor do Data Workbench.

| Código | Fuso horário | Deslocamento do GMT |
|---|---|---|
| gmt | Greenwich Mean | 0 |
| est | Padrão oriental | 5 |
| edt | Horário de Verão do Leste | 5 |
| cst | Padrão central | 6 |
| cdt | Horário de Verão Central | 6 |
| mst | Padrão das Montanhas | 7 |
| mdt | Hora de Verão das Montanhas | 7 |
| pst | Padrão do Pacífico | 8 |
| pdt | Horário de Verão do Pacífico | 8 |
