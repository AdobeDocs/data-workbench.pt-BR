---
description: Esta seção é um guia rápido que fornece as etapas mínimas necessárias para configurar e agendar scripts para reprocessar semanalmente seus arquivos de registro. Isso pode ser usado como guia de referência para configurar ou modificar seus perfis.
title: Script para o Reprocessamento Semanal
uuid: d3cd163d-6129-4883-ac7c-b2f75b5eb247
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Script para o Reprocessamento Semanal{#scripting-to-weekly-reprocess}

Esta seção é um guia rápido que fornece as etapas mínimas necessárias para configurar e agendar scripts para reprocessar semanalmente seus arquivos de registro. Isso pode ser usado como guia de referência para configurar ou modificar seus perfis.

## O que é o Reprocess {#section-7e335aacc199488592e78a835e2649fe}

Carregamento de dados para o DWB com base em alterações nas fontes de dados, fontes de dados offline ou período de tempo. O script reprocessará o parâmetro de data de início no arquivo *Log Processing.cfg* .

## Pré-requisitos {#section-804acce5df4942469c9313535627038a}

ID do conjunto de relatórios, o número de dados mensais deve estar disponível no DWB. A pasta Perl64 deve estar disponível em seu C:\ drive.

## Reprocessar registros {#section-565d3e1f0df14127a97d9beecd14f02f}

Forneça os detalhes acima (pré-requisitos) no script de comando do Windows *Reprocess.bat* disponível na pasta *\scripts\Log Processing* no servidor FSU principal.

Esse script chamará internamente dois scripts específicos do cliente: Um para reprocessar os dados e outro para alertas de e-mail. Esses dois scripts também estão disponíveis na pasta *\scripts\Log Processing* .

O script alterará os parâmetros de reprocessamento no arquivo *Log Processing.cfg* .

## Janela de rolagem para registros {#section-ed5f44d890b34523ab33da7aa0ae3990}

Forneça detalhes (pré-requisitos) no script de comando do Windows *logprocessingdate.bat* disponível na pasta *\scripts\Scripository* no servidor FSU de fabricação. Esse script chamará internamente dois scripts específicos do cliente: Um para configurar a data de início dos registros e outro para alertas de e-mail. Esses dois scripts também estão disponíveis em* \scripts\Scripository*

Forneça a ID do conjunto de relatórios e o número de meses no arquivo* logprocessingdate.bat*.

O script alterará o parâmetro de data de início em *Log Processing.cfg*.

>[!NOTE]
>
>Se a pasta do *Repositório* não estiver disponível, siga o processo abaixo para copiar a pasta do *Repositório* e fazer alterações nos arquivos acima usando detalhes específicos para o cliente. E forneça seu endereço de email para obter um alerta em caso de erro.

## Agendamento de scripts {#section-063cf0c755dc47d28d60947d8d43d0e9}

Siga estas etapas para agendar os scripts no programador de tarefas do Windows.

1. Agende o script no agendador de tarefas do Windows.

   * Abrir Agendador de Tarefas: Clique com o botão direito do mouse na Biblioteca **do Agendador de** Tarefas e clique em **Criar Tarefa**.

   * Na guia **Geral** , forneça um nome de tarefa e selecione **Opções**.

   * Na guia **Acionadores** , clique em **Novo** e uma nova janela será aberta.

   * Na guia **Ações** , clique em **Novo** e uma nova janela será aberta. Em seguida, forneça os detalhes do script e outras opções. (Começar em terá um caminho onde o script é colocado).

1. Validação: Clique com o botão direito do mouse e execute o trabalho e verifique as alterações no arquivo *Log processing.cfg* . Um email será enviado para a ID de email fornecida no script.

