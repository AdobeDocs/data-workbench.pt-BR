---
description: A opção Configuração abre seu arquivo Insight.cfg, que controla suas conexões com vários servidores.
title: Opção de configuração
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# Opção de configuração{#configuration-option}

{{eol}}

A opção Configuração abre seu arquivo Insight.cfg, que controla suas conexões com vários servidores.

![](assets/cfg_Workstation.png)

**Para editar o arquivo Insight.cfg**

1. No [!DNL Insight.cfg] modifique os parâmetros conforme desejado. Para obter descrições detalhadas dos parâmetros no [!DNL Insight.cfg] arquivo, consulte [Parâmetros de configuração do Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Para salvar as configurações, clique com o botão direito do mouse em **[!UICONTROL Insight.cfg (modified)]** na parte superior da janela e clique em **[!UICONTROL Save as Insight.cfg]**.

**Para adicionar novos servidores**

1. No [!DNL Insight.cfg] , clique com o botão direito do mouse **[!UICONTROL Servers]** e clique em **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. Conclua ou modifique os parâmetros do servidor para fornecer ao Data Workbench acesso ao servidor desejado. Para obter descrições detalhadas dos parâmetros no [!DNL Insight.cfg] arquivo, consulte [Parâmetros de configuração do Insight](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. Repita as Etapa 1 e 2 para cada servidor ao qual deseja configurar uma conexão.
1. Para salvar as configurações, clique com o botão direito do mouse em **[!UICONTROL Insight.cfg (modified)]** na parte superior da janela e clique em **[!UICONTROL Save as Insight.cfg]**.

O Data Workbench tenta se conectar aos servidores usando as configurações especificadas. Se uma conexão for estabelecida, um nó verde aparecerá no nó [!DNL Servers Manager] conforme mostrado abaixo. Se o Data Workbench não conseguir se conectar ao servidor, um nó vermelho será exibido.

![](assets/vis_SysStat_RedGreenDots.png)
