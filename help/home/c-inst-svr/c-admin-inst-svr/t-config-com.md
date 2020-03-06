---
description: O arquivo de configuração Comunicações, Communications.cfg, contém as configurações de rede do Insight Server e o caminho para o arquivo Access Control.cfg.
solution: Insight
title: Configurando Comunicações
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurando Comunicações{#configuring-communications}

O arquivo de configuração Comunicações, Communications.cfg, contém as configurações de rede do Insight Server e o caminho para o arquivo Access Control.cfg.

Essas configurações ajudam a se conectar a [!DNL Insight Server].

**Frequência recomendada:** Somente quando necessário

**Para exibir e modificar as configurações de comunicação em[!DNL Insight]**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Communications.cfg] arquivo está localizado dentro deste diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor para [!DNL Communications.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Communications.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Na [!DNL Communications.cfg] janela, clique **[!UICONTROL component]** para exibir seu conteúdo.
1. Altere as configurações, conforme necessário. Para obter informações sobre os parâmetros disponíveis neste arquivo, consulte Configurações [de](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)comunicações.

   ![Informações da etapa](assets/cfg_communications_examplevalues.png)

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

