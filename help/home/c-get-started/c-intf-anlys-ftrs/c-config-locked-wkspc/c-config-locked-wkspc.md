---
description: A Data Workbench pode ser configurada para permitir que somente determinados usuários alterem determinados espaços de trabalho.
title: Configurar um espaço de trabalho bloqueado
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# Configurar um espaço de trabalho bloqueado{#configure-a-locked-workspace}

A Data Workbench pode ser configurada para permitir que somente determinados usuários alterem determinados espaços de trabalho.

Embora um espaço de trabalho esteja bloqueado, os usuários podem fazer seleções na maioria das visualizações e classificar os dados em tabelas, mas não podem alterar o espaço de trabalho. Essa funcionalidade impede que os usuários façam alterações não intencionais nos espaços de trabalho.

Os três elementos a seguir trabalham juntos para controlar o bloqueio de espaços de trabalho:

* **Um arquivo folder.lock ou  *workspace name*.lock:** Um  [!DNL folder.lock] arquivo especifica se os espaços de trabalho em uma determinada pasta estão bloqueados, enquanto um  [!DNL name.lock] arquivo de espaço de trabalho especifica se um espaço de trabalho específico está bloqueado.

* **O parâmetro Unlock no  [!DNL Insight.cfg] arquivo de um usuário:** Esse parâmetro especifica se esse usuário pode desbloquear temporariamente os espaços de trabalho bloqueados.
* **A opção de menu Desbloquear temporariamente:** quando o parâmetro Desbloquear no do usuário  [!DNL Insight.cfg] estiver definido como verdadeiro, essa opção aparecerá automaticamente no menu da barra de título de cada espaço de trabalho bloqueado para fornecer uma maneira de o usuário desbloqueá-lo.

Para obter informações sobre arquivos [!DNL folder.lock] e espaço de trabalho [!DNL name.lock], consulte a seguinte seção. Para obter informações sobre como definir o parâmetro Desbloquear , consulte [Definir o parâmetro Desbloquear](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Para obter informações sobre a opção [!DNL Temporarily Unlock menu], consulte [Desbloquear um espaço de trabalho](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
