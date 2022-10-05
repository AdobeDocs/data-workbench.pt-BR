---
description: A interface de Status Detalhado no Data Workbench é útil para solucionar erros ou outros problemas com as máquinas do Servidor do Data Workbench e do Servidor de Relatório que são clientes do Servidor do Data Workbench.
title: Exibir o status do servidor de relatórios
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Exibir o status do servidor de relatórios{#displaying-report-server-status}

{{eol}}

A interface de Status Detalhado no Data Workbench é útil para solucionar erros ou outros problemas com as máquinas do Servidor do Data Workbench e do Servidor de Relatório que são clientes do Servidor do Data Workbench.

Para exibir o status do Relatório na [!DNL Master Server Detailed Status] você deve adicionar um servidor de status de relatório à [!DNL Servers] vetor no servidor do Data Workbench [!DNL Communications.cfg] arquivo. O procedimento a seguir descreve como adicionar o servidor de status do relatório ao [!DNL Communications.cfg] arquivo:

Para obter mais informações sobre [!DNL Detailed Status] interfaces, consulte o capítulo Interfaces administrativas do *Guia do usuário do Data Workbench*.

**Para adicionar uma[!DNL Report Status Server]**

1. Navegue até a pasta Componentes no diretório em que você instalou o servidor do Data Workbench (InsightServer64.exe).

   Exemplo: [!DNL C:\Adobe\Server\Components]
1. Abrir [!DNL Communications.cfg] em um editor de texto como o Bloco de notas.
1. Localize a variável [!DNL Servers] e adicione o servidor de status do relatório a esse vetor, como destacado no fragmento de arquivo a seguir.

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. Atualize a contagem de itens para a [!DNL Servers] vetor (ou seja, incremente o valor dos itens por um), conforme destacado no fragmento de arquivo na etapa anterior.
1. Salve o arquivo.
