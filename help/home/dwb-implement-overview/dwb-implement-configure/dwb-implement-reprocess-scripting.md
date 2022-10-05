---
description: Esta seção é um guia rápido que fornece as etapas mínimas necessárias para configurar e agendar scripts para reprocessar seus arquivos de log semanalmente. Isso pode ser usado como guia de referência para configurar ou modificar seus perfis.
title: Script para o reprocessamento semanal
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
exl-id: f1b6f12e-629e-47c7-aa15-41f76d1c3192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---

# Script para o reprocessamento semanal{#scripting-to-weekly-reprocess}

{{eol}}

Esta seção é um guia rápido que fornece as etapas mínimas necessárias para configurar e agendar scripts para reprocessar seus arquivos de log semanalmente. Isso pode ser usado como guia de referência para configurar ou modificar seus perfis.

## O que é Reprocessar {#section-7e335aacc199488592e78a835e2649fe}

Carregamento de dados no DWB com base em alterações em fontes de dados, fontes de dados offline ou período de tempo. O script reprocessará o parâmetro da data de início em *Log Processing.cfg* arquivo.

## Pré-requisitos {#section-804acce5df4942469c9313535627038a}

ID do conjunto de relatórios, O número de dados do mês deve estar disponível no DWB. A pasta Perl64 deve estar disponível em sua C:\ drive.

## Reprocessar registros {#section-565d3e1f0df14127a97d9beecd14f02f}

Forneça os detalhes acima (pré-requisitos) no script de comando do windows *Reprocess.bat* disponível na pasta *\scripts\Processamento de log* no servidor FSU principal.

Esse script chamará internamente dois scripts específicos do cliente: Um para reprocessar os dados e outro para alertas de email. Esses dois scripts também estão disponíveis na variável *\scripts\Processamento de log* pasta.

O script alterará os parâmetros de reprocessamento no *Log Processing.cfg* arquivo.

## Janela de Rolagem para Logs {#section-ed5f44d890b34523ab33da7aa0ae3990}

Fornecer detalhes (pré-requisitos) no script de comando do windows *logprocessingdate.bat* disponível na pasta *\scripts\Repositório* no servidor FSU principal. Esse script chamará internamente dois scripts específicos do cliente: Um para configurar a data de início dos registros e outro para alertas de email. Esses dois scripts também estão disponíveis em * \scripts\Scripository*

Forneça a ID do conjunto de relatórios e o número de meses no arquivo* logprocessingdate.bat*.

O script alterará o parâmetro da data de início em *Log Processing.cfg*.

>[!NOTE]
>
>Se a variável *Escritório* não estiver disponível, siga o processo abaixo para copiar o *Escritório* e faça alterações nos arquivos acima usando detalhes específicos do cliente. E forneça seu endereço de email para obter um alerta em caso de erro.

## Agendamento de scripts {#section-063cf0c755dc47d28d60947d8d43d0e9}

Siga estas etapas para agendar os scripts no agendador de tarefas do Windows.

1. Programe o script no agendador de tarefas do Windows.

   * Abrir Programador de Tarefas: Clique com o botão direito do mouse no **Biblioteca do Agendador de Tarefas** e clique em **Criar tarefa**.

   * No **Geral** forneça um nome de tarefa e selecione **Opções**.

   * Em **Triggers** clique em **Novo** e uma nova janela será aberta.

   * Em **Ações** clique em **Novo** e uma nova janela será aberta. Em seguida, forneça os detalhes do script e outras opções. (Começar em terá um caminho onde o script é colocado).

1. Validação: Clique com o botão direito do mouse e execute o trabalho e verifique as alterações no *Log processing.cfg* arquivo. Um email será enviado para a ID de email fornecida no script.
