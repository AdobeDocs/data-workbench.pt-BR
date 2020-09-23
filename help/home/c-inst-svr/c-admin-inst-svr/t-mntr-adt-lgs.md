---
description: Os arquivos de log de auditoria rastreiam todas as tentativas de conexão e desconexões do Insight Server, cada uma delas conectada aos arquivos <AAAMMDD>-access.txt, localizados por padrão na pasta Auditoria, dentro do diretório de instalação do Insight Server.
solution: Analytics
title: Monitorar logs de auditoria
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---


# Monitorar logs de auditoria{#monitoring-audit-logs}

Os arquivos de log de auditoria rastreiam todas as tentativas de conexão e desconexões do Insight Server, cada uma delas conectada aos `<YYYYMMDD>-access.txt` arquivos localizados por padrão na pasta Auditoria no diretório de instalação do Insight Server.

**Frequência recomendada:** Diariamente ou conforme necessário para solução de problemas

Os registros de auditoria podem ser muito úteis ao solucionar problemas de conexão com [!DNL Insight Server]. Você pode monitorar esses registros usando sua ferramenta de gerenciamento automatizado ou visualizando os [!DNL access.txt] arquivos diretamente.

**Para visualização dos arquivos access.txt por meio do[!DNL Server Files Manager]**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone de um ativo [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique **[!UICONTROL Audit]** para visualização do conteúdo.
1. Clique com o botão direito do mouse na marca de seleção na coluna nome *do* servidor ao lado do arquivo desejado e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida ao lado do nome do arquivo na [!DNL Temp] coluna.
1. Clique com o botão direito do mouse na nova marca de seleção na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O log de auditoria é exibido em uma nova janela do Bloco de Notas do Microsoft Windows.

   ![Informações da etapa](assets/cfg_accesscontrol_accessFile.png)

