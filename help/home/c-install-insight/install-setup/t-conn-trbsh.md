---
description: Se o Insight não puder se conectar ao(s) servidor(es) Insight usando as configurações especificadas, um nó vermelho será exibido no Gerenciador de servidores.
title: Solução de problemas de conexão
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
exl-id: 7938d4d6-e1ab-46d9-9ccb-cf79677c5688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# Solução de problemas de conexão{#connection-troubleshooting}

{{eol}}

Se o Insight não puder se conectar ao(s) servidor(es) Insight usando as configurações especificadas, um nó vermelho será exibido no Gerenciador de servidores.

Isso pode ocorrer, por exemplo, se a conexão for configurada incorretamente ou se você não tiver permissão para exibir a variável [!DNL Insight Server’s] status.

**Para determinar por que o Insight não pode estabelecer uma conexão**

1. Clique com o botão direito do mouse no nó red server e clique em **[!UICONTROL Detailed Status]**.
1. No [!DNL Detailed Status] clique em **[!UICONTROL Network Connections]** e expanda os itens numerados. O [!DNL Status] fornece informações sobre por que o Insight não é capaz de estabelecer uma conexão:

   * Um código de status na década de 500 indica um erro de configuração.
   * Um código de status 403 geralmente indica que você não tem permissão para visualizar o status do servidor.

Você pode exibir informações de status adicionais na [!DNL insight.log] arquivo. Este arquivo de log está localizado na [!DNL Trace] no diretório em que você instalou o Insight. Para exibir o arquivo, abra-o em um editor de texto, como o Bloco de notas.

Se precisar de assistência para entender as informações na [!DNL insight.log] , primeiro entre em contato com o administrador do sistema. Se precisar de mais assistência, entre em contato com o Atendimento ao cliente do Adobe.
