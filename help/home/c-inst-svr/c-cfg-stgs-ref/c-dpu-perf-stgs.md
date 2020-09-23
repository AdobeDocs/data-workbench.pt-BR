---
description: Instruções para ajustar o desempenho da DPU.
solution: Analytics
title: Configurações de desempenho da DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---


# Configurações de desempenho da DPU{#dpu-performance-settings}

Instruções para ajustar o desempenho da DPU.

Preencha os seguintes parâmetros no diretório de instalação * [!DNL Insight Server] *\Components\DPU.cfg arquivo.

| Parâmetro | Descrição |
|---|---|
| Contagem de Lotes de Execução | Este é um parâmetro de ajuste. O valor padrão é 65536. É possível especificar arbitrariamente contagens de lote de execução pequena. Entre em contato com a Adobe antes de fazer qualquer alteração nesse valor. |
| Lotes de execução | Este é um parâmetro de ajuste. O valor padrão é 128. Entre em contato com a Adobe antes de fazer qualquer alteração nesse valor. |
| Tempo de execução | Este é um parâmetro de ajuste. O valor padrão é 0,100. Entre em contato com a Adobe antes de fazer qualquer alteração nesse valor. |
| Despejo de campo em erro | Esse parâmetro pode ser definido como true ou false. Se definido como true, [!DNL Insight Server] criará um arquivo nomeado [!DNL Field Dump number.txt] em seu diretório Trace sempre que ocorrerem erros no mecanismo de execução. A [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] é útil para solucionar problemas. |
| Caminho do perfil | Local no qual armazenar arquivos para todos os perfis. O local padrão é Perfis\. |
| Limite de memória do query | Quantidade de memória (em bytes) que [!DNL Insight Server] reserva para armazenar os resultados do query. O valor padrão é 100000000 (100 MB.) Se for necessário mais espaço para os resultados do query (por exemplo, para permitir mais usuários simultâneos), a configuração pode ser aumentada, mas você deve continuar verificando a carga da [!DNL Insight Server’s] memória. |
| Caminho do estado | Localização dos arquivos de estado do sistema. O local padrão é State\. |
| Threads | Um parâmetro de ajuste de desempenho para [!DNL Insight Server] máquinas com vários processadores. Em geral, para qualquer sistema n-core, esse valor deve ser definido como n. O valor padrão é 1. |
| Caminho do usuário | Localização dos arquivos de usuários autorizados. O local padrão é Usuários\. |

