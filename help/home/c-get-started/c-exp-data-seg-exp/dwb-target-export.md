---
description: Exporte dados do Análise de big data para o Adobe Target usando TargetBulkUpload.exe da Tabela de detalhes.
title: Exportar para o Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportar para o Adobe Target{#export-to-adobe-target}

Exporte dados do Análise de big data para o Adobe Target usando TargetBulkUpload.exe da Tabela de detalhes.

A análise de big data permite exportar arquivos para integração com o Adobe Target como parte de uma Adobe Experience Cloud integrada.

O **[!DNL TargetBulkUpload]** arquivo é encontrado na pasta *Server\Scripts* nos arquivos de instalação do servidor. O executável tem lógica de repetição, bem como lógica adicional para otimizar o desempenho.

Você pode modificar o `TargetBulkUpload.cfg` arquivo e movê-lo para a pasta *Servidor/Admin/Exportar* antes de executar o script de upload. Por exemplo, é possível definir um Intervalo de tempo limite máximo como 720 minutos (padrão) para o tempo limite de carregamento após o período especificado.

**Como funciona**

Depois que os dados são enviados com êxito para o Target, o status do upload é monitorado continuamente. Se o upload for bem-sucedido, uma mensagem de sucesso será registrada. Se o upload falhar ou estiver pendente, o monitoramento continuará. Você pode configurar o intervalo de tempo limite no `TargetBulkUpload.cfg` arquivo. Se o upload ficar travado no Target, uma mensagem será registrada e o status ainda poderá ser monitorado.

Há dois arquivos de log gerados no rastreamento para a exportação acionada em [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

O `targetbulkuploadexportname.log` arquivo tem o status detalhado para todos os registros de vários lotes, o servidor de borda para o qual eles estão indo e o status (bem-sucedido, com falha, perfil não encontrado, status desconhecido e travado). Caso se verifique que algum lote está emperrado, o lote não é processado. Um URL de lote travado está disponível para rastrear o status. Consulte os seguintes dados de exemplo do `targetbulkuploadexportname.log.completed` arquivo:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

O valor de status travado é incrementado com o tamanho total do lote travado, independentemente de quantos uploads forem bem-sucedidos ou falharem. O valor total de linhas também é incrementado pelo mesmo número de tamanhos de lote travados.

>[!NOTE]
>
>Anteriormente, os dados do DWB eram exportados usando o [!DNL ExportIntegration.exe]. Atualmente, somente as exportações MMP, CRS e S/FTP são usadas com esse executável. A integração do Adobe Target agora usa o [!DNL TargetBulkUpload.exe] em Análise de big data.

