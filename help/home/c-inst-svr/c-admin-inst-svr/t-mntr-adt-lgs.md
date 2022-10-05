---
description: Os arquivos de log de auditoria rastreiam todas as conexões tentadas com o servidor Insight e as desconexões dele, cada uma delas registrada no <yyyymmdd>Arquivos -access.txt localizados por padrão na pasta Audit no diretório de instalação do Insight Server.
title: Monitorar logs de auditoria
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# Monitorar logs de auditoria{#monitoring-audit-logs}

{{eol}}

Os arquivos de log de auditoria rastreiam todas as conexões tentadas com o servidor Insight e as desconexões dele, cada uma delas registrada no `<YYYYMMDD>-access.txt` arquivos localizados por padrão na pasta Audit no diretório de instalação do Insight Server.

**Frequência recomendada:** Diariamente ou conforme necessário para solução de problemas

Os logs de auditoria podem ser muito úteis ao solucionar problemas de conexão com o [!DNL Insight Server]. Você pode monitorar esses logs usando sua ferramenta de gerenciamento automatizado ou visualizando o [!DNL access.txt] arquivos diretamente.

**Para exibir os arquivos access.txt por meio do[!DNL Server Files Manager]**

1. Em [!DNL Insight], no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone de um [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Audit]** para visualizar seu conteúdo.
1. Clique com o botão direito do mouse na marca de seleção no *nome do servidor* ao lado do arquivo desejado e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida ao lado do nome do arquivo na [!DNL Temp] coluna.
1. Clique com o botão direito do mouse na nova marca de seleção no [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O log de auditoria é exibido em uma nova janela Microsoft Windows Notepad .

   ![Informações da etapa](assets/cfg_accesscontrol_accessFile.png)
