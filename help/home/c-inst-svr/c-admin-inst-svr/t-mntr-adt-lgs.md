---
description: Os arquivos de log de auditoria rastreiam todas as conexões tentadas com o servidor Insight e as desconexões dele, cada uma delas registrada nos arquivos <YYYMMDD>-access.txt, localizados por padrão na pasta Audit no diretório de instalação do servidor Insight.
title: Monitorar logs de auditoria
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# Monitorar logs de auditoria{#monitoring-audit-logs}

Os arquivos de log de auditoria rastreiam todas as conexões tentadas com o servidor Insight e as desconexões dele, cada uma delas registrada nos arquivos `<YYYYMMDD>-access.txt` localizados por padrão na pasta Auditoria no diretório de instalação do servidor Insight.

**Frequência recomendada:** diariamente ou conforme necessário para a solução de problemas

Os logs de auditoria podem ser muito úteis ao solucionar problemas de conexão a [!DNL Insight Server]. Você pode monitorar esses registros usando sua ferramenta de gerenciamento automatizado ou visualizando os arquivos [!DNL access.txt] diretamente.

**Para exibir os arquivos access.txt por meio do[!DNL Server Files Manager]**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone de um [!DNL Insight Server] ativo e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Audit]** para visualizar seu conteúdo.
1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* ao lado do arquivo desejado e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece ao lado do nome do arquivo na coluna [!DNL Temp].
1. Clique com o botão direito do mouse na nova marca de seleção na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O log de auditoria é exibido em uma nova janela do Bloco de Notas do Microsoft Windows.

   ![Informações da etapa](assets/cfg_accesscontrol_accessFile.png)
