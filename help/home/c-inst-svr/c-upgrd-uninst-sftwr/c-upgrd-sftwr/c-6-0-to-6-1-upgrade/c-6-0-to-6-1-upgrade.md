---
description: Siga estas etapas para atualizar para a análise de big data v6.1 a partir da instalação da análise de big data v6.0x.
solution: Analytics
title: Atualização do Análise de big data 6.0 para 6.1
topic: Data workbench
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Atualização do Análise de big data 6.0 para 6.1{#data-workbench-to-upgrade}

Siga estas etapas para atualizar para a análise de big data v6.1 a partir da instalação da análise de big data v6.0x.

**Etapa 1**: Atualização [do servidor](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Etapa 2**: Atualização do Servidor [de relatórios](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Etapa 3**: Atualização [do cliente](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Os componentes servidor, servidor de relatório e cliente são atualizados para serem executados em sistemas operacionais Windows de 64 bits.

## Atualização do servidor {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Siga estas etapas para atualizar os **[!UICONTROL Server v6.1]** componentes:

1. Usando o **[!UICONTROL Software and Docs]** perfil, abra a área de trabalho **[!UICONTROL Start Here]** e baixe todos os pacotes de servidor necessários para uma pasta local.

   * Baixe **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** pastas zip e extraia todos os arquivos.

      O pacote Servidor inclui **[!UICONTROL Lookup]** e **[!UICONTROL Profile]** pastas com **[!UICONTROL Base]** e **[!UICONTROL Transform]** perfis para atualizar o servidor.

      * Baixe as **[!UICONTROL Profiles]** pastas.
      * Baixe as **[!UICONTROL Lookup]** pastas.
      * Baixe o pacote **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** .
      * Baixe arquivos adicionais **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** e **[!UICONTROL Dashboard]** conforme necessário para o seu sistema.

1. Pare o **[!UICONTROL Adobe Insight Server]** serviço.

   ![](assets/install_server_download1.png)

1. Do **[!UICONTROL Server]** pacote baixado:

   1. Substitua a [!DNL Server\Bin] pasta para atualizar os arquivos [!DNL InsightServer64.exe] e os arquivos de suporte.

   1. Substitua a [!DNL Server\Profiles] pasta. É possível substituir todos os arquivos.
   1. Atualize a [!DNL Server\Lookups] pasta. Você desejará adicionar os arquivos recém-baixados aos arquivos personalizados já localizados na pasta.
   1. Substitua a [!DNL Server\Software] pasta para atualizar [!DNL Insight.exe] e [!DNL ReportServer.exe]
   1. Atualize a [!DNL Server\Scripts] pasta a ser atualizada [!DNL TnTSend.exe].

1. Se você usar **[!UICONTROL DeviceAtlas]**, será necessário [atualizar o pacote](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) localizado na [!DNL Server\Lookups] pasta.

1. Configure o [!DNL Profile.cfg] arquivo para garantir que o vetor seja atualizado para refletir o número de itens para cada perfil.

   Por exemplo, para ativar o **[!UICONTROL Predictive Analytics]** perfil, você precisará atualizar essa configuração.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configure e salve o arquivo PAServer.cfg para o recurso Análise preditiva.

   Se você quiser enviar trabalhos do Predictive Analytics para os servidores, será necessário configurar o [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] arquivo para gerenciar envios por clusters do servidor.

   O perfil personalizado deve herdar as configurações do perfil de configuração do Predictive Analytics, permitindo que você configure e salve o [!DNL PAServer.cfg] arquivo com base na implementação do site.

1. Defina as **[!UICONTROL Log Source ID]**.

   O **[!UICONTROL Recording of Rows per Log Source]** foi adicionado **[!UICONTROL v6.04]** e definido no [!DNL Log Processing.cfg] arquivo do perfil personalizado adicionando um nome exclusivo **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Se você não tiver a ID da Fonte de Log definida, você receberá o seguinte erro:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Como o [!DNL EventMessages.dll] foi atualizado, é necessário cancelar o registro e, em seguida, registrá-lo **[!UICONTROL Adobe Insight Server]** no cluster.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Inicie o **[!UICONTROL Adobe Insight Server]** serviço no cluster.

A instalação do servidor agora está concluída.

## Atualização do Servidor de Relatório {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Antes de atualizar para **[!UICONTROL Report Server v6.1]**, é necessário primeiro atualizar para **[!UICONTROL Server v6.1]**.

1. Usando o **[!UICONTROL Software and Docs]** perfil, baixe **[!UICONTROL v6.1]** do **[!UICONTROL Report Server]** pacote para uma pasta local.

1. Copie **[!UICONTROL Report Server 6.1]** do pacote baixado e substitua os pacotes de perfil.

   >[!NOTE]
   >
   >O [!DNL Insight.zbin] arquivo na [!DNL install] pasta é um arquivo de backup usado para localização e deve estar presente no [!DNL install] diretório. Esse arquivo ou outros [!DNL .zbin] arquivos serão usados dependendo das configurações de linha de comando passadas ao iniciar.

1. (opcional) A análise de big data suporta atualmente inglês (-en-us) e chinês (-zh-cn). É necessário definir uma fonte para suportar caracteres de byte único e duplo:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   O sistema operacional Windows também deve ter as fontes listadas instaladas.

1. Configurar [!DNL Report Server v6.1] para localização.

   1. Pare o **[!UICONTROL Adobe Insight Report Server]** serviço.
   1. Inicie um prompt de comando como um &quot;Administrador&quot;.
   1. Navegue até a [!DNL install] pasta Servidor de relatórios.
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

A instalação do servidor de relatórios está concluída.

## Atualização do cliente {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Antes de atualizar para **[!UICONTROL Client v6.1]**, o administrador deve primeiro atualizar para **[!UICONTROL Insight Server v6.1.]**

1. Inicie [!DNL Insight.exe] mas não se conecte a nenhum perfil.
1. Edite o [!DNL Insight.cfg] arquivo.

   ```
   Update Software = bool: true
   ```

1. Conecte-se ao seu perfil.

   Permita que o cliente sincronize com o servidor e seu cliente será atualizado com os perfis de cliente v6.1mais recentes, executáveis e arquivos de configuração.

   >[!NOTE]
   >
   >O [!DNL Insight.zbin] arquivo na [!DNL install] pasta é um arquivo de backup usado para localização e deve estar presente. Esse arquivo ou outros [!DNL .zbin] arquivos serão usados dependendo das configurações de linha de comando passadas ao iniciar.

   Consulte [configuração de idiomas](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) localizados para adicionar um [!DNL insight.zbin] arquivo necessário para configurações localizadas.

**Configurações adicionais do cliente**

Antes de configurar [!DNL Insight.exe] e suportar arquivos, você deve sair do aplicativo cliente.

Para instalar o chinês simplificado:

1. Crie um atalho que passe na configuração da linha de comando para o [!DNL Insight.exe] arquivo.

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] para suportar caracteres de fonte de byte único e duplo.

   Atualmente, a análise de big data suporta inglês e chinês simplificado. Você pode selecionar fontes para suportar ambos os idiomas:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   O sistema operacional Windows também deve ter as fontes solicitadas instaladas.

1. Inicie o atalho que você criou para sincronizar perfis e a atualização. [!DNL zbin] arquivo.

Para usar o Editor de método de entrada (IME).

O IME permite inserir caracteres internacionais.

1. Atualize o [!DNL Insight.cfg] arquivo com estas configurações:

   ```
   Localized IME = bool: true
   ```

1. Inicie o atalho criado para sincronizar perfis e o [!DNL .zbin] arquivo atualizado.

A instalação do cliente está concluída.