---
description: O arquivo de configuração Comunicações, Communications.cfg, contém as configurações de rede do Insight Server e o caminho para o arquivo Access Control.cfg.
title: Configurar comunicações
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Configurar comunicações{#configuring-communications}

{{eol}}

O arquivo de configuração Comunicações, Communications.cfg, contém as configurações de rede do Insight Server e o caminho para o arquivo Access Control.cfg.

Estas configurações ajudam você a se conectar [!DNL Insight Server].

**Frequência recomendada:** Apenas quando necessário

**Para exibir e modificar as configurações de comunicação em[!DNL Insight]**

1. Em [!DNL Insight], no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] você deseja configurar e clicar em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O [!DNL Communications.cfg] O arquivo está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção no *nome do servidor* coluna para [!DNL Communications.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece no [!DNL Temp] coluna para [!DNL Communications.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. No [!DNL Communications.cfg] , clique em **[!UICONTROL component]** para visualizar seu conteúdo.
1. Altere as configurações, conforme necessário. Para obter informações sobre os parâmetros disponíveis neste arquivo, consulte [Configurações de comunicações](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Informações da etapa](assets/cfg_communications_examplevalues.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
