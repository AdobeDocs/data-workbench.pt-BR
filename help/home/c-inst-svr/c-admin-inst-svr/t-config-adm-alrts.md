---
description: Os alertas administrativos enviam notificações por email para os endereços de email especificados quando erros são detectados pelo servidor Insight durante o curso normal da operação.
title: Configurar alertas administrativos
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# Configurar alertas administrativos{#configuring-administrative-alerts}

Os alertas administrativos enviam notificações por email para os endereços de email especificados quando erros são detectados pelo servidor Insight durante o curso normal da operação.

**Frequência recomendada:** antes da produção

>[!NOTE]
>
>O uso de alertas administrativos exige que [!DNL Insight Server] tenha acesso a um servidor SMTP de encaminhamento para enviar alertas por email.

Os destinatários das notificações por e-mail devem ser o pessoal-chave da administração de sistemas e os principais interessados.

O arquivo de Alertas Administrativos, [!DNL Administrative Alerts.cfg], é usado para configurar os alertas administrativos para [!DNL Insight Server].

>[!NOTE]
>
>Se você estiver executando um cluster, deverá criar ou modificar alertas no [!DNL Insight Server] principal no cluster.

**Para criar ou modificar um alerta administrativo**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O arquivo [!DNL Administrative Alerts.cfg] está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna *nome do servidor *para [!DNL Administrative Alerts.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Administrative Alerts.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Na janela [!DNL Administrative Alerts.cfg], clique em **[!UICONTROL component]** para visualizar seu conteúdo.
1. Preencha os parâmetros conforme desejado. Para obter uma lista dos parâmetros disponíveis neste arquivo, consulte [Configurações de Alertas Administrativos](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Informações da etapa](assets/cfg_adminalerts_examplevalues.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

1. (Opcional) Se você estiver trabalhando em um cluster e quiser que os mesmos alertas administrativos sejam aplicados a cada Unidade de processamento de dados, é necessário copiar e colar o arquivo [!DNL Administrative Alerts.cfg] atualizado na pasta [!DNL Components for Processing Servers] no diretório de instalação principal [!DNL Insight Server].
