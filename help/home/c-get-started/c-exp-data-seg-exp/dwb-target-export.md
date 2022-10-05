---
description: Exporte os dados da Data Workbench para o Adobe Target usando TargetBulkUpload.exe da Tabela de detalhes.
title: Exportar para o Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
exl-id: 41e885bb-182a-4983-98e8-65eec1da9fe9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---

# Exportar para o Adobe Target{#export-to-adobe-target}

{{eol}}

Exporte os dados da Data Workbench para o Adobe Target usando TargetBulkUpload.exe da Tabela de detalhes.

O Data Workbench permite exportar arquivos para integração com o Adobe Target como parte de um Adobe Experience Cloud integrado.

O **[!DNL TargetBulkUpload]** é encontrado no *Servidor\Scripts* nos arquivos de instalação do servidor. O executável tem lógica de repetição, bem como lógica adicional para otimizar o desempenho.

Você pode modificar o `TargetBulkUpload.cfg` e mova-o para *Servidor/Administrador/Exportar* pasta antes de executar o script de upload. Por exemplo, é possível definir um Intervalo de tempo limite máximo como 720 minutos (padrão) para atingir o tempo limite do upload após o período especificado.

**Como funciona**

Depois que os dados são enviados com sucesso ao Target, o status do upload é continuamente monitorado. Se o upload for bem-sucedido, uma mensagem de sucesso será registrada. Se o upload falhar ou estiver pendente, o monitoramento continuará. Você pode configurar o intervalo de tempo limite no `TargetBulkUpload.cfg` arquivo. Se o upload ficar travado no Target, uma mensagem será registrada e o status ainda poderá ser monitorado.

Há dois arquivos de log gerados no rastreamento para a exportação acionada em [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

O `targetbulkuploadexportname.log` O arquivo tem o status detalhado de todos os registros de vários lotes, o servidor de borda ao qual eles irão e o status (bem-sucedido, com falha, perfil não encontrado, status desconhecido e preso). Caso se verifique que algum lote está preso, o lote não é processado. Um URL de lote travado está disponível para rastrear o status. Veja os seguintes exemplos de dados da `targetbulkuploadexportname.log.completed` arquivo:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

O valor de status paralisado é incrementado com o tamanho total do lote travado, independentemente de quantos uploads são bem-sucedidos ou falharam. O valor total de linhas também é incrementado pelo mesmo número de tamanhos de lote presos.

>[!NOTE]
>
>Anteriormente, os dados do DWB eram exportados usando o [!DNL ExportIntegration.exe]. Atualmente, apenas as exportações MMP, CRS e S/FTP são usadas com esse executável. A integração do Adobe Target agora usa a variável [!DNL TargetBulkUpload.exe] no Data Workbench.
