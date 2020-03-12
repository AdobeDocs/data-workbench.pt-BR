---
description: Siga estas etapas para atualizar para a análise de big data v6.1 a partir da instalação do Insight v5.5x.
solution: Analytics
title: Atualização do Análise de big data 5.5 para 6.1
topic: Data workbench
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Atualização do Análise de big data 5.5 para 6.1{#data-workbench-to-upgrade}

Siga estas etapas para atualizar para a análise de big data v6.1 a partir da instalação do Insight v5.5x.

**Etapa 1**: Atualização [do servidor](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Etapa 2**: Atualização do Servidor [de Relatórios](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Etapa 3**: Atualização do [cliente](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Os componentes servidor, servidor de relatório e cliente são atualizados para serem executados em sistemas operacionais Windows de 64 bits.

## Atualização do servidor {#section-08bd6fe3da8740fcb19688e8cac6f223}

Siga estas etapas para atualizar os **[!UICONTROL Server v6.1]** componentes:

1. Usando o **[!UICONTROL Software and Docs]** perfil, abra a área de trabalho **[!UICONTROL Start Here]** e baixe todos os pacotes de servidor necessários para uma pasta local.

   * Baixe **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** pastas zip e extraia todos os arquivos.

      O **[!UICONTROL Server]** pacote inclui **[!UICONTROL Lookup]** e **[!UICONTROL Profile]** pastas com os arquivos **[!UICONTROL Base]** e de **[!UICONTROL Transform]** pesquisa a serem adicionados e substituídos para atualizar o servidor.

   * Baixe novas **[!UICONTROL Profiles]** pastas.
   * Baixar **[!UICONTROL Lookup]** pastas atualizadas.
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
1. Defina [!DNL Directories] no [!DNL Profile.cfg] arquivo para garantir que o vetor seja atualizado para refletir o número de itens para cada perfil.

   Por exemplo, para ativar o **[!UICONTROL Predictive Analytics]** perfil, você precisará atualizar essa configuração.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Configure e salve o [!DNL PAServer.cfg] arquivo para atualizar o recurso Análises preditivas.

   Se você quiser enviar trabalhos do Predictive Analytics para os servidores, será necessário configurar o [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] arquivo para gerenciar envios por clusters do servidor.

   O perfil personalizado deve herdar as configurações do perfil de configuração do Predictive Analytics, permitindo que você configure e salve o perfil com [!DNL PAServer.cfg] base na implementação do site.

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

1. (opcional) Modifique o arquivo de configuração do servidor de relatório para suportar caracteres de byte duplo.

   Atualmente, a análise de big data suporta inglês (-en-us) e chinês (-zh-cn). É necessário definir uma fonte para suportar caracteres de byte único e duplo:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   O sistema operacional Windows também deve ter as fontes listadas instaladas.

1. Configurar [!DNL Report Server v6.1].

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
>Antes de atualizar para **[!UICONTROL Client v6.1]**, o administrador deve primeiro atualizar para **[!UICONTROL Server v6.1.]**

1. Inicie [!DNL Insight.exe] , mas NÃO se conecte a nenhum perfil.
1. Edite o [!DNL Insight.cfg] arquivo para não atualizar o software automaticamente.

   ```
   Update Software = bool: false
   ```

1. Conecte-se ao **[!UICONTROL Software and Docs]** perfil (softdocs).
1. Baixar [!DNL Software\Insight Client\v6.10].
1. (opcional) Modifique [!DNL insight.cfg] para suportar caracteres de byte duplo.

   Atualmente, a análise de big data suporta inglês e chinês simplificado. Selecione as fontes para suportar ambos os idiomas:

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Saia do cliente.
1. Copie os arquivos no pacote do cliente **v6.1** baixado para a [!DNL Install] pasta.

   >[!NOTE]
   >
   >O [!DNL Insight.zbin] arquivo na pasta de instalação é um arquivo de backup usado para localização e deve estar presente no diretório de instalação. Esse arquivo ou outros [!DNL .zbin] arquivos serão usados dependendo das configurações de linha de comando passadas ao iniciar.
   >
   >Por exemplo, para iniciar o chinês simplificado, crie um atalho que passe na configuração da linha de comando.
   >
   >```
   >Insight.exe -zh-cn
   >```
   >
   >Se você quiser iniciar em inglês (padrão), nenhuma alteração na linha de comando será necessária.

1. Inicie [!DNL Insight.exe] para inglês ou o atalho criado para outro idioma.
1. Conecte-se ao seu perfil e permita que o cliente sincronize com o servidor.
1. (opcional) Para usar o IME, faça as seguintes alterações no [!DNL Insight.cfg] arquivo:

   ```
   Localized IME = bool: true
   ```

   O Editor de método de entrada (IME) permite inserir caracteres internacionais.

1. (opcional) Edite o [!DNL Insight.cfg] arquivo para atualizar automaticamente o software:

   ```
   Update Software = bool: true
   ```

   Consulte as instruções para implementar o IME.
1. Reinicie novamente após a sincronização do perfil para empregar o [!DNL .zbin] arquivo mais recente.

A instalação do cliente está concluída.
