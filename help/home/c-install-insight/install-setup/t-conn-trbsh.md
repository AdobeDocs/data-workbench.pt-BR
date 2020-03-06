---
description: Se o Insight não conseguir se conectar aos Servidores Insight usando as configurações especificadas, um nó vermelho será exibido no Gerenciador de Servidores.
title: Solução de problemas de conexão
uuid: 17190cee-da5c-449f-aca5-8e9e35e0a5fd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Solução de problemas de conexão{#connection-troubleshooting}

Se o Insight não conseguir se conectar aos Servidores Insight usando as configurações especificadas, um nó vermelho será exibido no Gerenciador de Servidores.

Isso pode ocorrer, por exemplo, se você configurar a conexão incorretamente ou se não tiver permissão para exibir o [!DNL Insight Server’s] status.

**Para determinar por que o Insight não é capaz de estabelecer uma conexão**

1. Clique com o botão direito do mouse no nó vermelho do servidor e clique em **[!UICONTROL Detailed Status]**.
1. Na [!DNL Detailed Status] interface, clique **[!UICONTROL Network Connections]** e expanda os itens numerados. O [!DNL Status] parâmetro fornece informações sobre por que o Insight não é capaz de estabelecer uma conexão:

   * Um código de status na 500s indica um erro de configuração.
   * Um código de status 403 geralmente indica que você não tem permissão para exibir o status do servidor.

É possível exibir informações adicionais de status no [!DNL insight.log] arquivo. Esse arquivo de log está localizado na [!DNL Trace] pasta no diretório em que você instalou o Insight. Para exibir o arquivo, abra-o em um editor de texto, como o Bloco de notas.

Se precisar de ajuda para entender as informações no [!DNL insight.log] arquivo, entre em contato primeiro com o administrador do sistema. Se precisar de mais assistência, entre em contato com o Atendimento ao cliente da Adobe.
