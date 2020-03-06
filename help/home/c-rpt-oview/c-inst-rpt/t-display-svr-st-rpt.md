---
description: A interface de Status Detalhado no análise de big data é útil para solucionar erros ou outros problemas com as máquinas do Servidor do Análise de big data e do Servidor de relatórios clientes do Servidor do Análise de big data.
solution: Analytics
title: Exibindo o Status do Servidor de Relatório
topic: Data workbench
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exibindo o Status do Servidor de Relatório{#displaying-report-server-status}

A interface de Status Detalhado no análise de big data é útil para solucionar erros ou outros problemas com as máquinas do Servidor do Análise de big data e do Servidor de relatórios clientes do Servidor do Análise de big data.

Para exibir o status do Relatório na [!DNL Master Server Detailed Status] interface, é necessário adicionar um servidor de status de relatório ao [!DNL Servers] vetor no arquivo do servidor do análise de big data [!DNL Communications.cfg] . O procedimento a seguir descreve como adicionar o servidor de status do relatório ao [!DNL Communications.cfg] arquivo:

Para obter mais informações sobre [!DNL Detailed Status] interfaces, consulte o capítulo Interfaces administrativas do Guia *do usuário da Análise de* big data.

**Para adicionar uma[!DNL Report Status Server]**

1. Navegue até a pasta Componentes no diretório em que você instalou o servidor da análise de big data (InsightServer64.exe).

   Exemplo: [!DNL C:\Adobe\Server\Components]
1. Abra [!DNL Communications.cfg] em um editor de texto, como o Bloco de notas.
1. Localize o [!DNL Servers] vetor e adicione o servidor de status de relatório a esse vetor, como destacado no seguinte fragmento de arquivo.

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

1. Atualize a contagem de itens para o [!DNL Servers] vetor (ou seja, aumente o valor de itens em um), como realçado no fragmento de arquivo na etapa anterior.
1. Salve o arquivo.
