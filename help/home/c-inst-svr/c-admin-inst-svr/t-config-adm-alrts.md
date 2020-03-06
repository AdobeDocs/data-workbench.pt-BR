---
description: Os alertas administrativos enviam notificações por email para os endereços de email especificados quando erros são detectados pelo Insight Server durante o curso normal da operação.
solution: Insight
title: Configuração de alertas administrativos
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuração de alertas administrativos{#configuring-administrative-alerts}

Os alertas administrativos enviam notificações por email para os endereços de email especificados quando erros são detectados pelo Insight Server durante o curso normal da operação.

**Frequência recomendada:** Antes da produção

>[!NOTE]
>
>O uso de alertas administrativos exige que o usuário tenha acesso a um servidor SMTP de encaminhamento para enviar alertas por email. [!DNL Insight Server]

Os destinatários das notificações por e-mail devem ser os principais funcionários da administração de sistemas e as principais partes interessadas.

O arquivo Alertas Administrativos, [!DNL Administrative Alerts.cfg], é usado para configurar os alertas administrativos para [!DNL Insight Server].

>[!NOTE]
>
>Se estiver executando um cluster, você deverá criar ou modificar alertas no mestre [!DNL Insight Server] do cluster.

**Para criar ou modificar um alerta administrativo**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para exibir o conteúdo. O [!DNL Administrative Alerts.cfg] arquivo está localizado dentro deste diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna *nome do servidor *para [!DNL Administrative Alerts.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Administrative Alerts.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Na [!DNL Administrative Alerts.cfg] janela, clique **[!UICONTROL component]** para exibir seu conteúdo.
1. Preencha os parâmetros conforme desejado. Para obter uma lista dos parâmetros disponíveis neste arquivo, consulte Configurações [de alertas](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)administrativos.

   ![Informações da etapa](assets/cfg_adminalerts_examplevalues.png)

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Opcional) Se você estiver trabalhando em um cluster e quiser que os mesmos alertas administrativos sejam aplicados a cada unidade de processamento de dados, copie e cole o arquivo atualizado na [!DNL Administrative Alerts.cfg] pasta no diretório de [!DNL Components for Processing Servers] [!DNL Insight Server] instalação mestre.
