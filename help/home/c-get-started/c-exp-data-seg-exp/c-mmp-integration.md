---
description: O Data Workbench permite exportar arquivos para integração com a Exportação de perfis e públicos como parte de um Adobe Experience Cloud integrado.
title: Exportação de perfil de marketing principal
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
exl-id: 9fc89815-d31d-41a7-a0c0-de1e84b24baa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 3%

---

# Exportação de perfil de marketing principal{#master-marketing-profile-export}

{{eol}}

O Data Workbench permite exportar arquivos para integração com Perfis e públicos-alvo como parte de uma Adobe Experience Cloud integrada.

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

Perfis e públicos-alvo fazem parte do [Serviço de identidade do Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR), um serviço central da [!DNL Adobe Experience Cloud]. A exportação de Perfis e públicos-alvo permite que os públicos-alvo sejam compartilhados no Experience Cloud usando uma ID de Experience Cloud exclusiva (ECID) que é atribuída a cada visitante e, em seguida, usada por [Audience Manager](https://docs.adobe.com/content/help/pt-BR/experience-cloud/user-guides/home.html). O [!DNL ExportIntegration.exe] pedido ( [!DNL E:\Server\Scripts]) é empregado para gerar exportações de MMP e Adobe Target.

**Configuração do servidor FSU para usar perfis e públicos-alvo**

1. Acesse seu servidor FSU.
1. Abra o arquivo MPExport.cfg . `Server/Admin/Export/MMPExport.cfg`.
1. Insira valores em todos os campos, conforme necessário. Por exemplo:

   >[!NOTE]
   >
   >A integração MMP/AAM depende do bucket s3 da Amazon para transferência de dados.
   >
   >
   >As informações s3 necessárias para a transferência de MMP (s3) podem ser obtidas da equipe de Audience Manager.

   ```
   Sample MMPExport.cfg
   MMP Export Configuration = MMPExportConfiguration: 
   s3 Bucket = string: aws_bucket_for_mmp 
   s3 Object Directory = string: test/files/ 
   s3 Region = string: us-east-1 
   s3 Access Key = string: ZZKI62OO5YBA 
   s3 Secret Key = string: ioqwa3OpNE5 
   data Provider Name = string: 895 
   client ID = string: mcprofile2-test 
   client Secret = string: saea1287617212987q 
   username = string: mmptest 
   password = string: pass 
   numRecordsPerChunk = int:  
   numThreads = int:  
   maxRetriesOnSendFailure = unsigned int:
   ```

   >[!NOTE]
   >
   >O [!DNL MMPExport.cfg]também permite que você pegue todos os registros, divida-os em conjuntos e crie partes de registros. As partes dos registros são então exportadas para o Amazon S3. Três parâmetros obrigatórios são necessários para criar partes de registros: [!DNL numRecordsPerChunk], [!DNL numThreads]e [!DNL maxRetriesOnSendFailure].

**Definição dos parâmetros**

<table id="table_DDEFBC45895A4663973F9C2EB9052FEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Definição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Bucket s3</i> </td> 
   <td colname="col2"> O bucket do AWS S3 para o qual a exportação é transferida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Diretório de objetos s3</i> </td> 
   <td colname="col2"> Um caminho para salvar arquivos s3. Isso é compatível com subdiretórios. <p> <p>Importante: Caracteres de espaço e multibyte não são permitidos no caminho e criarão erros na exportação. (O hífen é permitido). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Região s3</i> </td> 
   <td colname="col2"> A Região do AWS s3 para a qual a exportação é enviada. Ex. us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Chave de acesso s3</i> </td> 
   <td colname="col2"> Chave de acesso do AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3 Chave Secreta</i> </td> 
   <td colname="col2"> Chave secreta do AWS s3 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Nome do provedor de dados</i> </td> 
   <td colname="col2"> Esse será o nome da pasta usado para armazenar segmentos e características em AAM, respectivamente. Isso deve ser exclusivo por cliente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>client ID</i> </td> 
   <td colname="col2"> Esta é uma ID de cliente exclusiva fornecida a um cliente quando provisionada para MMP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>segredo do cliente</i> </td> 
   <td colname="col2"> <p><i></i>Este é um segredo de cliente exclusivo fornecido a um cliente quando ele/ela é provisionado para MMP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>username</i> </td> 
   <td colname="col2"> Nome de usuário do MMP </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>password</i> </td> 
   <td colname="col2"> Senha MMP </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numRecordsPerChunk</i> </td> 
   <td colname="col2"> <p>Determina o tamanho do bloco em termos de número de registros. </p> <p>A implementação corta o valor especificado pelo usuário para mín = 1000 registros &amp; nbsp;(~50 KB chunks) &amp; nbsp; e máx = 50000 registros (~2,5 MB chunks).&amp;nbsp;Um valor padrão de 10000 é usado caso o usuário não especifique essa propriedade de configuração. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThreads</i> </td> 
   <td colname="col2"> <p>Determina o paralelismo da parte de envio do segmento. Ele aceita um valor entre 1 e 24 threads e seu valor padrão é 12 threads. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailure</i> </td> 
   <td colname="col2"> <p>Determina o número de tentativas a serem feitas no caso de falhas de envio de fragmento. O valor padrão é 0, sem nenhuma tentativa. </p> <p>Intervalo de repouso de 2 segundos é usado entre tentativas. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Gerando exportação de MMP do cliente**

1. No cliente, abra um espaço de trabalho e clique com o botão direito do mouse **[!UICONTROL Tools]**> **[!UICONTROL Detail Table]**.
1. Adicionar **Nível**.
1. Clique com o botão direito do mouse no cabeçalho e selecione **Adicionar atributos**.
1. Clique com o botão direito do mouse no cabeçalho e selecione **Nova exportação de perfil de marketing Principal**. ![](assets/mmp_mmp_export.png)
1. Expandir **Query**.

   ![](assets/mmp_mmp_query.png)

1. Expandir **Configuração MMP**.
1. (obrigatório) Informe o **Nome do segmento MMP** e **Campo de ID de visitante MMP**. Esses parâmetros não podem ser deixados em branco.
1. O **Nome do segmento MMP** deve corresponder à ID do segmento definida no MMP.
1. O **ID de visitante MMP** é a coluna de atributo definida na etapa 4 que corresponde ao **ID de visitante**.
1. Depois que esses campos forem inseridos, poderá salvar a exportação clicando com o botão direito do mouse no cabeçalho da exportação e escolha **Salvar** como &quot;User\.export&quot;.
1. Abrir **Administrador** > **Gerenciador de perfis** e salve a exportação para o perfil.

   Se todos os dados forem inseridos corretamente, isso gerará um arquivo de exportação no FSU ([!DNL Server/Exports]) e também transferirá a exportação para a AWS usando as informações em [!DNL MMPExport.cfg]. O log para isso é fornecido em [!DNL Server/Trace/]. por exemplo, [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

```
Query = SegmentExportQuery: 
Command = string: ExportIntegration.exe 
Command Arguments = string: \"%file%.cfg\" \"%file%\" 
Filter = string: 
Level = string: Page View 
MMP Configuration = MMPConfiguration: 
MMP Segment Name = string: 12345 
MMP Visitor ID Field = string: Tracking ID 
Oneshot = bool: true 
Output Fields = vector: 3 items 
0 = ColumnDefinition: 
Column Name = string: 
Field Name = string: Tracking ID 
1 = ColumnDefinition: 
Column Name = string: 
Field Name = string: PID 
2 = ColumnDefinition: 
Column Name = string: 
Field Name = string: SID 
Output File = string: MMPTest.txt 
Output Format = string: %1%\t%2%\t%3%\r\n 
Schedule End Time = string: 
Schedule Every = string: 
Schedule Start Time = string: 
Time Limit (sec) = double: 1800 
```

| Detalhes da configuração | Descrição |
|---|---|
| ID do segmento MMP | Obrigatório. Este é um identificador que você definiria primeiro no Audience Manager. |
| Campo de ID de visitante MMP | Mapeie a ECID. |
