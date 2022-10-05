---
description: Formatar instruções sobre parâmetros com base no tempo no servidor Insight.
title: Códigos de fuso horário (servidor Insight)
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 4%

---

# Códigos de fuso horário{#time-zone-codes}

{{eol}}

Formatar instruções sobre parâmetros com base no tempo no servidor Insight.

A maioria dos parâmetros baseados em tempo em [!DNL Insight Server] são especificadas no seguinte formato:

*Mês DD, AAAA HH:MM:Fuso HorárioSS*

Exemplo: 13 de agosto de 2013 22:30:00 EST

Os fusos horários são expressos em um formato de fuso horário independente do sistema (Hora Universal Coordenada) com o seguinte formato:

UTC +hmm *regras*

O sinal (+) pode ser um sinal de mais (+) ou um sinal de menos (-) e *hhmm* é o deslocamento do UTC em horas e minutos. A variável opcional *regras* especifica um conjunto de regras para implementar o Horário de verão ou uma política de mudança de relógio semelhante.

Se você especificar *regras*, um arquivo delimitado por tabulação chamado *&lt; [!DNL dstrules]>* [!DNL .dst] deve estar presente no diretório Dataset\TimeZone do perfil Base (para arquivos de configuração que não estão associados a um conjunto de dados específico) ou no perfil do conjunto de dados (para arquivos de configuração que são específicos do conjunto de dados). O arquivo especifica um conjunto de regras independente de fuso horário para o horário de verão. Você pode ter diferentes conjuntos de regras para anos diferentes. O [!DNL DST.dst] O arquivo fornecido pelo Adobe no perfil Base especifica as regras padrão dos EUA estabelecidas pelo Energy Policy Act de 2005 (em vigor a partir de 2007) e as regras dos EUA para anos anteriores.

As entradas de fuso horário de exemplo são listadas abaixo:

* Hora de Verão do Leste dos EUA: Fuso Horário = string: UTC -0500 DST
* Hora UTC sem deslocamento e sem *regras* (correspondente a GMT): Fuso Horário = string: UTC -0000

Quando esse formato é usado, o fuso horário do sistema de [!DNL Insight Server], [!DNL Insight]e [!DNL Report] máquinas não precisam ser iguais ao fuso horário especificado. Além disso, todos os perfis do conjunto de dados ativos em um [!DNL Insight Server] a máquina não precisa ter a mesma configuração de fuso horário.

A tabela a seguir contém a lista de códigos que podem ser usados para especificar fusos horários em parâmetros baseados em tempo.

## Tabela de códigos do fuso horário {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Se estiver implementando o Horário de verão ou uma política de mudança de relógio semelhante, você deverá salvar o [!DNL .dst] arquivo contendo as regras apropriadas na *nome do perfil*\Dataset\Timezone diretório [!DNL Insight Server] máquina.

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
