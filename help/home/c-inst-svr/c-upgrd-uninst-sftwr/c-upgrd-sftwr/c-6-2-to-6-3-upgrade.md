---
description: Atualização de componentes do servidor para o Data Workbench 6.3.
title: Atualização do servidor DWB 6.2 para 6.3
uuid: e12b6cc1-070e-4bc7-bc64-203d11cfeae9
exl-id: 5106d9a3-179a-49f1-915a-c03b36ed5257
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Atualização do servidor DWB: 6.2 para 6.3{#dwb-server-upgrade-to}

{{eol}}

Atualização de componentes do servidor para o Data Workbench 6.3.

**Atualizar servidor**

Se você tiver personalizado perfis que tenham precedência sobre os arquivos padrão fornecidos no [!DNL Base] , será necessário atualizar esses arquivos personalizados:

* **Atualizar o arquivo Meta.cfg** ( [!DNL E:\..\Profiles\<your custom profile>\Context\meta.cfg)]para definir a criptografia de senha atualizada para a Unidade de Sistema de Arquivos (servidor FSU) e adicionar entradas para as transformações do Par de Valor do Nome para aproveitar [Grupos de sequência de consulta](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md#concept-42f74911b5714219a359b719badac8e0).

   1. Abra o [!DNL meta.cfg] no FSU.
   1. Alterar o tipo de dados para **[!UICONTROL Proxy Password]** de &quot; [!DNL string"] para &quot; [!DNL EncryptedString]&quot; na *Configuração da estação de trabalho* seção.

      ```
        Proxy User Name = string:
        Proxy Password = EncryptedString:   (
        from Proxy Password = String)
        Use Address File = bool: true
      ```

   1. Adicione novas entradas para ativar as novas transformações do Par de Valor de Nome: *ParValorDoNomeDeBuild* e *ExtractNameValuePairs*.

      Abra um espaço de trabalho e clique com o botão direito do mouse **Administrador** > **Gerenciador de perfis**.

      Em **Contexto**, clique no botão **meta.cfg** no **Base** e clique em **Tornar local**. Na coluna User table , clique com o botão direito do mouse e selecione **Abrir** > **na estação de trabalho**.

      ![](assets/meta_cfg.png)

      * Na nova janela, clique em **metadados** e adicionar modelos filhos aceitáveis.

         ![](assets/meta_cfg_child.png)

      * Abrir **transformação** e adicionar novos modelos.

         ![](assets/meta_cfg_template.png)

* **Atualização para melhorias na Fast Merge**. Adicione parâmetros ou altere valores para os seguintes arquivos de configuração para aproveitar as melhorias de velocidade no Data Workbench durante uma transformação.

   * **Communications.cfg** ( [!DNL E:\Server\Components\Communications.cfg])

      ```
      18 = SourceListServer:
          URI = string: /SourceListServer/
          Listing Interval = int: 10 (
      <new>)
      ```

   * **Arquivos de disco.cfg** a [!DNL E:\Server\Components] e [!DNL E:\Server\Components for Processing Servers])

      ```
      Disk Cache Size (MB) = double: 1024
      <(from double: 256)>
      Disk Cache Read Limit (MB) = double: 768
      <(new)>
      ```

   * **Log Processing Mode.cfg** ( [!DNL E:\Server\Profiles\<your profile>\Dataset\Log Processing Mode.cfg])

      ```
      <(changed)
      Batch Bytes = int: 268435456
      Cloud Bytes = int: 268435456
      Real Time FIFO Bytes = int: 268435456
      ```

      ```
      (
      <new>)
      Cache Bytes = int: 32000000
      Fast Input Decision Ratio = double: 200
      Fast Input FIFO Bytes = int: 268435456
      FIFO Hash Mask = int: 16383
      Fast Merge Buffer Bytes = int: 536870912
      Slow Merge Buffer Bytes = int: 268435456
      Fast Merge Fan In = int: 64
      Key Cache Size Logarithm = int: 21
      Max Seeks = int: 512
      Output Old Buffer Bytes = int: 536870912
      Overflow FIFO Bytes = int: 67108864
      Paused = bool: false
      ```
   >[!NOTE]
   >
   >Para aproveitar os aprimoramentos de Fast Merge, verifique se você tem pelo menos 8 GB de RAM por DPU.

* **Atualização de integração do Adobe Target com DWB**. Um novo arquivo de exportação, [!DNL ExportIntegration.exe], substitui [!DNL TnTSend.exe] no servidor Insight (`E:\Server\Scripts\TnTSend.exe`). Este novo arquivo de exportação suporta ambos [Adobe Target](https://www.adobe.com/marketing/target.html) integração e coordenação com o novo Perfil de Marketing Principal (MMP) e [Adobe Audience Manager](https://www.adobe.com/analytics/audience-manager.html).

   Você precisará atualizar os seguintes comandos para exportações do Adobe Target.

   `Command = string: TnTSend.exe`

   para

   ```
   <filepath>
   Command = string: ExportIntegration.exe
   </filepath>
   ```

   >[!NOTE]
   >
   >Isso só afetará as exportações criadas antes da versão 6.3.

   Você também pode tentar o seguinte para utilizar o processo de exportação antigo:

   * Crie uma nova exportação de Test&amp;Target na estação de trabalho.
   * Modifique a exportação antiga do Test e Target encontrada em [!DNL Server/Profiles/`<your profile>`/Export.]

* **Atualize o perfil do Adobe SC.** Alterações à [!DNL Exclude Hit.cfg] O arquivo requer que um campo seja declarado no [!DNL Decoding Instructions.cfg] arquivo.

   >[!NOTE]
   >
   >Se o seu perfil Adobe SC incluir um [!DNL Decoding Instructions.cfg] , será necessário incluir um [!DNL DelimitedDecoder] para seu arquivo personalizado.

   ```
   0 = DelimitedDecoder:
      Delimiter = string: \t
      Fields = vector: x items
      …
         5 = string:
   Changed to:
   
   5 = string: x-hit_source
   ```

   Adicionar a [!DNL DelimitedDecoder] permite aproveitar as atualizações de recursos e evitar possíveis problemas de processamento de log resultantes dessas atualizações.
