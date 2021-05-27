---
description: Siga estas etapas para atualizar para o Data Workbench v6.1 a partir da sua instalação do Data Workbench v6.0x.
title: Atualização do Data Workbench 6.0 para 6.1
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 1%

---

# Atualização do Data Workbench 6.0 para 6.1{#data-workbench-to-upgrade}

Siga estas etapas para atualizar para o Data Workbench v6.1 a partir da sua instalação do Data Workbench v6.0x.

**Etapa 1**:  [Atualização do servidor](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Etapa 2**:  [Atualização do servidor de relatórios](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Etapa 3**:  [Atualização do cliente](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Os componentes servidor, servidor de relatórios e cliente são atualizados para serem executados em sistemas operacionais Windows de 64 bits.

## Atualização do servidor {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Siga estas etapas para atualizar os componentes **[!UICONTROL Server v6.1]**:

1. Usando o perfil **[!UICONTROL Software and Docs]**, abra o espaço de trabalho **[!UICONTROL Start Here]** e baixe todos os pacotes de servidor necessários para uma pasta local.

   * Baixe **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** as pastas zip e extraia todos os arquivos.

      O pacote Server inclui **[!UICONTROL Lookup]** e **[!UICONTROL Profile]** pastas com perfis **[!UICONTROL Base]** e **[!UICONTROL Transform]** para atualizar o servidor.

      * Baixe as pastas **[!UICONTROL Profiles]**.
      * Baixe as pastas **[!UICONTROL Lookup]**.
      * Baixe o pacote **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]**.
      * Baixe arquivos adicionais **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** e **[!UICONTROL Dashboard]** conforme necessário para seu sistema.

1. Pare o serviço **[!UICONTROL Adobe Insight Server]**.

   ![](assets/install_server_download1.png)

1. No pacote baixado **[!UICONTROL Server]**:

   1. Substitua a pasta [!DNL Server\Bin] para atualizar o [!DNL InsightServer64.exe] e os arquivos de suporte.

   1. Substitua a pasta [!DNL Server\Profiles]. Você pode substituir todos os arquivos.
   1. Atualize a pasta [!DNL Server\Lookups]. Você desejará adicionar os arquivos recém-baixados aos arquivos personalizados já localizados na pasta .
   1. Substitua a pasta [!DNL Server\Software] para atualizar [!DNL Insight.exe] e [!DNL ReportServer.exe]
   1. Atualize a pasta [!DNL Server\Scripts] para atualizar [!DNL TnTSend.exe].

1. Se você usar **[!UICONTROL DeviceAtlas]**, será necessário [atualizar o pacote](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) localizado na pasta [!DNL Server\Lookups].

1. Configure o arquivo [!DNL Profile.cfg] para garantir que o vetor seja atualizado para refletir o número de itens para cada perfil.

   Por exemplo, para ativar o perfil **[!UICONTROL Predictive Analytics]**, será necessário atualizar essa configuração.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configure e salve o arquivo PAServer.cfg para o recurso de Análise preditiva.

   Caso deseje enviar trabalhos do Predictive Analytics para os servidores, será necessário configurar o arquivo [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] para gerenciar os envios de cluster do lado do servidor.

   O perfil personalizado deve herdar as configurações do perfil de configuração do Predictive Analytics, permitindo configurar e salvar o arquivo [!DNL PAServer.cfg] com base na implementação do site.

1. Defina as **[!UICONTROL Log Source ID]**.

   O **[!UICONTROL Recording of Rows per Log Source]** foi adicionado em **[!UICONTROL v6.04]** e definido no arquivo [!DNL Log Processing.cfg] do perfil personalizado ao adicionar um nome exclusivo **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Se você não tiver a ID da fonte de log definida, aparecerá o seguinte erro:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Como o [!DNL EventMessages.dll] foi atualizado, é necessário cancelar o registro e, em seguida, registrar o **[!UICONTROL Adobe Insight Server]** no cluster.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Inicie o serviço **[!UICONTROL Adobe Insight Server]** no cluster.

A instalação do servidor foi concluída.

## Atualização do servidor de relatórios {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Antes de atualizar para **[!UICONTROL Report Server v6.1]**, primeiro atualize para **[!UICONTROL Server v6.1]**.

1. Usando o perfil **[!UICONTROL Software and Docs]**, baixe **[!UICONTROL v6.1]** do pacote **[!UICONTROL Report Server]** para uma pasta local.

1. Copie **[!UICONTROL Report Server 6.1]** do pacote baixado e substitua os pacotes de perfil.

   >[!NOTE]
   >
   >O arquivo [!DNL Insight.zbin] na pasta [!DNL install] é um arquivo de backup usado para localização e deve estar presente no diretório [!DNL install]. Esse arquivo ou outros arquivos [!DNL .zbin] serão usados dependendo das configurações da linha de comando passadas ao iniciar.

1. (opcional) No momento, o Data Workbench suporta inglês (-en-us) e chinês (-zh-cn). É necessário definir uma fonte para suportar caracteres de byte único e duplo:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   O sistema operacional Windows também deve ter as fontes listadas instaladas.

1. Configure [!DNL Report Server v6.1] para localização.

   1. Pare o serviço **[!UICONTROL Adobe Insight Report Server]**.
   1. Inicie um prompt de comando como um &quot;Administrador&quot;.
   1. Navegue até a pasta [!DNL install] do Servidor de Relatórios.
   1. Exclua o serviço Servidor de relatórios usando o seguinte comando:

      ```
      ReportServer.exe /unregserver
      ```

   1. Inicie o serviço com base nas configurações de idioma:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Para verificar se o Servidor de relatórios está sendo executado com as configurações corretas, abra **[!UICONTROL Windows Service Manager]** e clique com o botão direito do mouse em **[!UICONTROL Adobe Insight Report Server - Properties]**. O caminho para o executável exibirá as configurações atualizadas da linha de comando.

A instalação do servidor de relatórios foi concluída.

## Atualização do cliente {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Antes de atualizar para **[!UICONTROL Client v6.1]**, o administrador deve primeiro atualizar para **[!UICONTROL Insight Server v6.1.]**

1. Inicie [!DNL Insight.exe], mas não se conecte a nenhum perfil.
1. Edite o arquivo [!DNL Insight.cfg].

   ```
   Update Software = bool: true
   ```

1. Conecte-se ao seu perfil.

   Permitir que o cliente sincronize com o servidor e seu cliente será atualizado com os perfis de cliente v6.1mais recentes, executáveis e arquivos de configuração.

   >[!NOTE]
   >
   >O arquivo [!DNL Insight.zbin] na pasta [!DNL install] é um arquivo de backup usado para localização e deve estar presente. Esse arquivo ou outros arquivos [!DNL .zbin] serão usados dependendo das configurações da linha de comando passadas ao iniciar.

   Consulte [configuração de idiomas localizados](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) para adicionar um arquivo [!DNL insight.zbin] necessário para configurações localizadas.

**Configurações adicionais do cliente**

Antes de configurar [!DNL Insight.exe] e arquivos de suporte, você deve sair do aplicativo cliente.

Para instalar o idioma chinês simplificado:

1. Crie um atalho que passe na configuração da linha de comando para o arquivo [!DNL Insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] para suportar caracteres de fonte de um e dois bytes.

   Atualmente, o Data Workbench oferece suporte para inglês e chinês simplificado. Você pode selecionar fontes para oferecer suporte a ambos os idiomas:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   O sistema operacional Windows também deve ter as fontes solicitadas instaladas.

1. Inicie o atalho criado para sincronizar perfis e o atualizado . [!DNL zbin] arquivo.

Para usar o Editor de método de entrada (IME).

O IME permite inserir caracteres internacionais.

1. Atualize o arquivo [!DNL Insight.cfg] com estas configurações:

   ```
   Localized IME = bool: true
   ```

1. Inicie o atalho criado para sincronizar perfis e o arquivo [!DNL .zbin] atualizado.

A instalação do cliente está concluída.
