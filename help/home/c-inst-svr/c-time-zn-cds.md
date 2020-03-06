---
description: Instruções de formato sobre parâmetros baseados em tempo no Insight Server.
solution: Insight
title: Códigos de fuso horário
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Códigos de fuso horário{#time-zone-codes}

Instruções de formato sobre parâmetros baseados em tempo no Insight Server.

A maioria dos parâmetros baseados em tempo em [!DNL Insight Server] são especificados no seguinte formato:

*Mês DD, AAAA HH:MM:SS Fuso horário*

Exemplo: 13 de agosto de 2013 22:30:00 EST

Os fusos horários são expressos em um formato de fuso horário independente do sistema (Hora Universal Coordenada) com o seguinte formato:

UTC + *hmm*

O sinal (+) pode ser um sinal de mais (+) ou um sinal de menos (-), e *hhmm* é o deslocamento de UTC em horas e minutos. Os *padrões* de variável opcionais especificam um conjunto de regras para implementar o Horário de verão ou uma política de mudança de relógio semelhante.

Se você especificar *os documentos*, um arquivo delimitado por tabulação chamado *&lt;[!DNL dstrules]>* [!DNL .dst] deverá estar presente no diretório Dataset\TimeZone do perfil Base (para arquivos de configuração que não estejam associados a um conjunto de dados específico) ou no perfil do conjunto de dados (para arquivos de configuração que sejam específicos do conjunto de dados). O arquivo especifica um conjunto de regras independente de fuso horário para o Horário de verão. Você pode ter diferentes conjuntos de regras para anos diferentes. O [!DNL DST.dst] arquivo fornecido pela Adobe no perfil básico especifica as regras padrão dos EUA estabelecidas pelo Energy Policy Act de 2005 (em vigor a partir de 2007) e as regras dos EUA para anos anteriores.

As entradas de exemplo de fuso horário estão listadas abaixo:

* Horário de Verão do Leste dos EUA: Fuso horário = string: UTC -0500 DST
* Hora UTC sem deslocamento e sem *regras* (correspondente ao GMT): Fuso horário = string: UTC -0000

Quando esse formato é usado, o fuso horário do sistema de [!DNL Insight Server], [!DNL Insight]e [!DNL Report] máquinas não precisa ser o mesmo que o fuso horário especificado. Além disso, todos os perfis de conjunto de dados ativos em um [!DNL Insight Server] computador não precisam ter a mesma configuração de fuso horário.

A tabela a seguir contém a lista de códigos que você pode usar para especificar fusos horários nos parâmetros baseados em tempo.

## Tabela de códigos de fuso horário {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>Se você estiver implementando o Horário de verão ou uma política de mudança de relógio semelhante, salve o [!DNL .dst] arquivo que contém as regras apropriadas no nome *\Dataset\Timezone directory on the* do [!DNL Insight Server] perfil.

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

