---
description: Instruções para ajustar o desempenho da DPU.
title: Configurações de desempenho da DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---

# Configurações de desempenho da DPU{#dpu-performance-settings}

Instruções para ajustar o desempenho da DPU.

Preencha os seguintes parâmetros no diretório de instalação * [!DNL Insight Server]*\Components\DPU.cfg .

| Parâmetro | Descrição |
|---|---|
| Contagem de Lotes de Execução | Este é um parâmetro de ajuste. O valor padrão é 65536. Você pode especificar arbitrariamente contagens de lotes de execução pequena. Entre em contato com o Adobe antes de fazer qualquer alteração nesse valor. |
| Lotes de execução | Este é um parâmetro de ajuste. O valor padrão é 128. Entre em contato com o Adobe antes de fazer qualquer alteração nesse valor. |
| Tempo de execução | Este é um parâmetro de ajuste. O valor padrão é 0,100. Entre em contato com o Adobe antes de fazer qualquer alteração nesse valor. |
| Despejo de campo em erro | Esse parâmetro pode ser definido como verdadeiro ou falso. Se definido como true, [!DNL Insight Server] criará um arquivo chamado [!DNL Field Dump number.txt] em seu diretório Trace sempre que ocorrerem erros no mecanismo de execução. O [!DNL Field Dump] &lt; [!DNL number] [!DNL .txt] é útil para solucionar problemas. |
| Caminho do perfil | Local no qual armazenar arquivos para todos os perfis. O local padrão é Perfis\. |
| Limite de Memória de Consulta | Quantidade de memória (em bytes) que [!DNL Insight Server] reserva para armazenar os resultados da consulta. O valor padrão é 100000000 (100MB.) Se for necessário mais espaço para os resultados da consulta (por exemplo, para permitir mais usuários simultâneos), a configuração poderá ser aumentada, mas você deverá continuar verificando a carga de memória [!DNL Insight Server’s]. |
| Caminho do estado | Localização dos arquivos de estado do sistema. O local padrão é State\. |
| Threads | Um parâmetro de ajuste de desempenho para máquinas [!DNL Insight Server] com vários processadores. Em geral, para qualquer sistema n-core, esse valor deve ser definido como n. O valor padrão é 1. |
| Caminho do usuário | Localização dos arquivos de usuários autorizados. O local padrão é Usuários\. |
