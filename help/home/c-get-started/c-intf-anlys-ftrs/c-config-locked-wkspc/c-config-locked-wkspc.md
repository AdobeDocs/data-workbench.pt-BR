---
description: A Data Workbench pode ser configurada para permitir que somente determinados usuários alterem determinados espaços de trabalho.
title: Configurar um espaço de trabalho bloqueado
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# Configurar um espaço de trabalho bloqueado{#configure-a-locked-workspace}

{{eol}}

A Data Workbench pode ser configurada para permitir que somente determinados usuários alterem determinados espaços de trabalho.

Embora um espaço de trabalho esteja bloqueado, os usuários podem fazer seleções na maioria das visualizações e classificar os dados em tabelas, mas não podem alterar o espaço de trabalho. Essa funcionalidade impede que os usuários façam alterações não intencionais nos espaços de trabalho.

Os três elementos a seguir trabalham juntos para controlar o bloqueio de espaços de trabalho:

* **Um folder.lock ou *nome do espaço de trabalho*Arquivo .lock:** A [!DNL folder.lock] arquivo especifica se os espaços de trabalho em uma pasta específica estão bloqueados, enquanto um espaço de trabalho [!DNL name.lock] especifica se um espaço de trabalho específico está bloqueado.

* **O parâmetro Desbloquear no [!DNL Insight.cfg] arquivo:** Esse parâmetro especifica se o usuário pode desbloquear temporariamente espaços de trabalho bloqueados.
* **A opção de menu Desbloquear temporariamente:** Quando o parâmetro Desbloquear no [!DNL Insight.cfg] for definida como true, essa opção aparecerá automaticamente no menu da barra de título de cada espaço de trabalho bloqueado para fornecer uma maneira de o usuário desbloqueá-la.

Para obter informações sobre [!DNL folder.lock] e espaço de trabalho [!DNL name.lock] arquivos, consulte a seção a seguir. Para obter informações sobre como definir o parâmetro Desbloquear , consulte [Definir o parâmetro de desbloqueio](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Para obter informações sobre o [!DNL Temporarily Unlock menu] consulte [Desbloquear um espaço de trabalho](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
