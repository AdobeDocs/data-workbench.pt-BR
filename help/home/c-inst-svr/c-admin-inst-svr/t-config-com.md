---
description: O arquivo de configuração Comunicações, Communications.cfg, contém as configurações de rede do Insight Server e o caminho para o arquivo Access Control.cfg.
title: Configurar comunicações
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Configurar comunicações{#configuring-communications}

O arquivo de configuração Comunicações, Communications.cfg, contém as configurações de rede do Insight Server e o caminho para o arquivo Access Control.cfg.

Essas configurações ajudam você a se conectar a [!DNL Insight Server].

**Frequência recomendada:** somente quando necessário

**Para exibir e modificar as configurações de comunicação em[!DNL Insight]**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL Communications.cfg] está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* para [!DNL Communications.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Communications.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Na janela [!DNL Communications.cfg], clique em **[!UICONTROL component]** para visualizar seu conteúdo.
1. Altere as configurações, conforme necessário. Para obter informações sobre os parâmetros disponíveis neste arquivo, consulte [Configurações de Comunicação](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![Informações da etapa](assets/cfg_communications_examplevalues.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
