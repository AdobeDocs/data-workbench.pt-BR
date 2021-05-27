---
description: A interface de Status Detalhado no Data Workbench é útil para solucionar erros ou outros problemas com as máquinas do Servidor do Data Workbench e do Servidor de Relatório que são clientes do Servidor do Data Workbench.
title: Exibir o status do servidor de relatórios
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Exibir o status do servidor de relatórios{#displaying-report-server-status}

A interface de Status Detalhado no Data Workbench é útil para solucionar erros ou outros problemas com as máquinas do Servidor do Data Workbench e do Servidor de Relatório que são clientes do Servidor do Data Workbench.

Para visualizar o status do Relatório na interface [!DNL Master Server Detailed Status], é necessário adicionar um servidor de status de relatório ao vetor [!DNL Servers] no arquivo [!DNL Communications.cfg] do servidor do Data Workbench. O procedimento a seguir descreve como adicionar o servidor de status do relatório ao arquivo [!DNL Communications.cfg] :

Para obter mais informações sobre as interfaces [!DNL Detailed Status], consulte o capítulo Interfaces Administrativas do *Guia do Usuário do Data Workbench*.

**Para adicionar uma[!DNL Report Status Server]**

1. Navegue até a pasta Componentes no diretório em que você instalou o servidor do Data Workbench (InsightServer64.exe).

   Exemplo: [!DNL C:\Adobe\Server\Components]
1. Abra [!DNL Communications.cfg] em um editor de texto, como o Bloco de notas.
1. Localize o vetor [!DNL Servers] e adicione o servidor de status do relatório a esse vetor, como destacado no fragmento de arquivo a seguir.

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

1. Atualize a contagem de itens para o vetor [!DNL Servers] (ou seja, incremente o valor de itens por um), conforme realçado no fragmento de arquivo na etapa anterior.
1. Salve o arquivo.
