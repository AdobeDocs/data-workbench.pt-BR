---
description: A opção Configuração abre seu arquivo Insight.cfg, que controla suas conexões com vários servidores.
solution: Analytics
title: Opção de configuração
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Opção de configuração{#configuration-option}

A opção Configuração abre seu arquivo Insight.cfg, que controla suas conexões com vários servidores.

![](assets/cfg_Workstation.png)

**Para editar o arquivo Insight.cfg**

1. Na [!DNL Insight.cfg] janela, modifique os parâmetros conforme desejado. Para obter descrições detalhadas dos parâmetros no [!DNL Insight.cfg] arquivo, consulte Parâmetros [de configuração do](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)Insight.
1. Para salvar as configurações, clique com o botão direito do mouse **[!UICONTROL Insight.cfg (modified)]** na parte superior da janela e clique em **[!UICONTROL Save as Insight.cfg]**.

**Para adicionar novos servidores**

1. Na [!DNL Insight.cfg] janela, clique com o botão direito do mouse **[!UICONTROL Servers]** e clique em **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Conclua ou modifique os parâmetros do servidor para fornecer ao Análise de big data acesso ao servidor desejado. Para obter descrições detalhadas dos parâmetros no [!DNL Insight.cfg] arquivo, consulte Parâmetros [de configuração do](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)Insight.
1. Repita a Etapa 1 e a Etapa 2 para cada servidor para o qual você deseja configurar uma conexão.
1. Para salvar as configurações, clique com o botão direito do mouse **[!UICONTROL Insight.cfg (modified)]** na parte superior da janela e clique em **[!UICONTROL Save as Insight.cfg]**.

A Análise de big data tenta se conectar aos servidores usando as configurações especificadas. Se uma conexão for estabelecida, um nó verde aparecerá na tela [!DNL Servers Manager] , como mostrado abaixo. Se o Análise de big data não conseguir se conectar ao servidor, um nó vermelho será exibido.

![](assets/vis_SysStat_RedGreenDots.png)

