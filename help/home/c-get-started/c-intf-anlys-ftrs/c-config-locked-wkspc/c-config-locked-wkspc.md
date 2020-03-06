---
description: A Análise de big data pode ser configurada para permitir que somente determinados usuários alterem determinados espaços de trabalho.
solution: Analytics
title: Configurar um espaço de trabalho bloqueado
topic: Data workbench
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar um espaço de trabalho bloqueado{#configure-a-locked-workspace}

A Análise de big data pode ser configurada para permitir que somente determinados usuários alterem determinados espaços de trabalho.

Embora um espaço de trabalho esteja bloqueado, os usuários podem fazer seleções na maioria das visualizações e classificar os dados em tabelas, mas de outra forma não podem alterar o espaço de trabalho. Essa funcionalidade impede que os usuários façam alterações não intencionais nos espaços de trabalho.

Os três elementos a seguir trabalham em conjunto para controlar o bloqueio de espaços de trabalho:

* **Um arquivo folder.lock ou *workspace name*.lock:** Um [!DNL folder.lock] arquivo especifica se os espaços de trabalho em uma pasta específica estão bloqueados, enquanto um [!DNL name.lock] arquivo de espaço de trabalho especifica se um espaço de trabalho específico está bloqueado.

* **O parâmetro Desbloquear no arquivo do usuário[!DNL Insight.cfg]:** Esse parâmetro especifica se o usuário pode desbloquear temporariamente espaços de trabalho bloqueados.
* **A opção de menu Desbloquear temporariamente:** Quando o parâmetro Desbloquear no do usuário [!DNL Insight.cfg] estiver definido como true, essa opção aparecerá automaticamente no menu da barra de título de cada espaço de trabalho bloqueado para fornecer uma maneira de o usuário desbloqueá-la.

Para obter informações sobre [!DNL folder.lock] arquivos e [!DNL name.lock] arquivos de espaço de trabalho, consulte a seção a seguir. Para obter informações sobre como configurar o parâmetro Desbloquear, consulte [Configuração do parâmetro](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)Desbloquear. Para obter informações sobre a [!DNL Temporarily Unlock menu] opção, consulte [Desbloquear um espaço de trabalho](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
