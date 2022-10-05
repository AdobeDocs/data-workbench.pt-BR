---
description: Siga estas etapas para atualizar para o Data Workbench v6.1 a partir da sua instalação do Insight v5.5x.
title: Atualização do Data Workbench 5.5 para 6.1
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---

# Atualização do Data Workbench 5.5 para 6.1{#data-workbench-to-upgrade}

{{eol}}

Siga estas etapas para atualizar para o Data Workbench v6.1 a partir da sua instalação do Insight v5.5x.

**Etapa 1**: [Atualização do servidor](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Etapa 2**: [Atualização do servidor de relatórios](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Etapa 3**: [Atualização do cliente](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Os componentes servidor, servidor de relatórios e cliente são atualizados para serem executados em sistemas operacionais Windows de 64 bits.

## Atualização do servidor {#section-08bd6fe3da8740fcb19688e8cac6f223}

Siga estas etapas para atualizar o **[!UICONTROL Server v6.1]** componentes:

1. Usar o **[!UICONTROL Software and Docs]** , abra o **[!UICONTROL Start Here]** e faça o download de todos os pacotes de servidor necessários para uma pasta local.

   * Baixar **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** compacte as pastas e extraia todos os arquivos.

      O **[!UICONTROL Server]** pacote inclui **[!UICONTROL Lookup]** e **[!UICONTROL Profile]** com **[!UICONTROL Base]** e **[!UICONTROL Transform]** arquivos de pesquisa para adicionar e substituir para atualizar o servidor.

   * Baixar novo **[!UICONTROL Profiles]** pastas.
   * Download atualizado **[!UICONTROL Lookup]** pastas.
   * Baixe o **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** pacote.
   * Baixar mais **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]** e **[!UICONTROL Dashboard]** arquivos conforme necessário para seu sistema.

1. Pare o **[!UICONTROL Adobe Insight Server]** serviço.

   ![](assets/install_server_download1.png)

1. A partir do download **[!UICONTROL Server]** pacote:

   1. Substitua o [!DNL Server\Bin] pasta para atualizar [!DNL InsightServer64.exe] e arquivos de suporte.

   1. Substitua o [!DNL Server\Profiles] pasta. Você pode substituir todos os arquivos.
   1. Atualize o [!DNL Server\Lookups] pasta. Você desejará adicionar os arquivos recém-baixados aos arquivos personalizados já localizados na pasta .
   1. Substitua o [!DNL Server\Software] pasta a atualizar [!DNL Insight.exe] e [!DNL ReportServer.exe]

   1. Atualize o [!DNL Server\Scripts] pasta a atualizar [!DNL TnTSend.exe].

1. Se empregar **[!UICONTROL DeviceAtlas]**, então será necessário [atualizar o pacote](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) localizada na [!DNL Server\Lookups] pasta.
1. Definir [!DNL Directories] no [!DNL Profile.cfg] para garantir que o vetor seja atualizado para refletir o número de itens para cada perfil.

   Por exemplo, para ativar a variável **[!UICONTROL Predictive Analytics]** seu perfil precisará atualizar essa configuração.

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. Configure e salve o [!DNL PAServer.cfg] para atualizar o recurso de Análise preditiva.

   Se você quiser enviar trabalhos do Predictive Analytics para os servidores, será necessário configurar o [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] para gerenciar envios de cluster do lado do servidor.

   O perfil personalizado deve herdar as configurações do perfil de configuração do Predictive Analytics, permitindo configurar e salvar o [!DNL PAServer.cfg] com base na implementação do site.

1. Defina as **[!UICONTROL Log Source ID]**.

   O **[!UICONTROL Recording of Rows per Log Source]** foi adicionado em **[!UICONTROL v6.04]** e definidas no [!DNL Log Processing.cfg] adicionar um nome exclusivo **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Se você não tiver a ID da fonte de log definida, aparecerá o seguinte erro:

   ```
   Missing Log Source ID in log processing.cfg.
   Log Source ID must be defined for all log sources.
   ```

1. Porque a variável [!DNL EventMessages.dll] foi atualizado, é necessário cancelar o registro e, em seguida, registrar a variável **[!UICONTROL Adobe Insight Server]** no cluster.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Inicie o **[!UICONTROL Adobe Insight Server]** em todo o cluster.

A instalação do servidor foi concluída.

## Atualização do servidor de relatórios {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Antes de atualizar para **[!UICONTROL Report Server v6.1]**, primeiro você deve atualizar para **[!UICONTROL Server v6.1]**.

1. Usar o **[!UICONTROL Software and Docs]** perfil, download **[!UICONTROL v6.1]** do **[!UICONTROL Report Server]** pacote em uma pasta local.
1. Copiar **[!UICONTROL Report Server 6.1]** do pacote baixado e substitua os pacotes de perfil.

   >[!NOTE]
   >
   >O [!DNL Insight.zbin] no [!DNL install] é um arquivo de backup usado para localização e deve estar presente no [!DNL install] diretório. Esse arquivo ou outro [!DNL .zbin] os arquivos serão usados dependendo das configurações da linha de comando passadas ao iniciar.

1. (opcional) Modifique o arquivo de configuração do servidor de relatórios para suportar caracteres de byte duplo.

   No momento, o Data Workbench oferece suporte para inglês (-en-us) e chinês (-zh-cn). É necessário definir uma fonte para suportar caracteres de byte único e duplo:

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
   1. Navegar até o servidor de relatórios [!DNL install] pasta.
   1. Exclua o serviço Servidor de relatórios usando o seguinte comando:

      ```
      ReportServer.exe /unregserver
      ```

1. Inicie o serviço com base nas configurações de idioma:

   ```
   ReportServer.exe -RegServer -Locale -en-us (English)
   ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
   ```

1. Para verificar se o Servidor de relatórios está sendo executado com as configurações corretas, abra **[!UICONTROL Windows Service Manager]** e clique com o botão direito do mouse **[!UICONTROL Adobe Insight Report Server - Properties]**. O caminho para o executável exibirá as configurações atualizadas da linha de comando.

A instalação do servidor de relatórios foi concluída.

## Atualização do cliente {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Antes de atualizar para **[!UICONTROL Client v6.1]**, o administrador deve primeiro atualizar para **[!UICONTROL Server v6.1.]**

1. Launch [!DNL Insight.exe] mas NÃO se conecte a nenhum perfil.
1. Edite o [!DNL Insight.cfg] não atualize o software automaticamente.

   ```
   Update Software = bool: false
   ```

1. Conectar-se a **[!UICONTROL Software and Docs]** perfil (softdocs).
1. Baixar [!DNL Software\Insight Client\v6.10].
1. (opcional) Modificar [!DNL insight.cfg] para suportar caracteres de byte duplo.

   Atualmente, o Data Workbench oferece suporte para inglês e chinês simplificado. Selecione fontes para oferecer suporte a ambos os idiomas:

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

1. Saia do cliente.
1. Copie os arquivos no arquivo baixado **v6.1** pacote de cliente para o [!DNL Install] pasta.

   >[!NOTE]
   >
   >O [!DNL Insight.zbin] O arquivo na pasta de instalação é um arquivo de backup usado para localização e deve estar presente no diretório de instalação. Esse arquivo ou outro [!DNL .zbin] os arquivos serão usados dependendo das configurações da linha de comando passadas ao iniciar.
   >
   >Por exemplo, para iniciar o idioma Chinês simplificado, crie um atalho que passe na configuração da linha de comando.
   >
   >
   ```
   >Insight.exe -zh-cn
   >```
   >
   >Se quiser iniciar em inglês (padrão), nenhuma alteração na linha de comando será necessária.

1. Launch [!DNL Insight.exe] para inglês ou o atalho criado para outro idioma.
1. Conecte-se ao seu perfil e permita que o cliente sincronize com o servidor.
1. (opcional) Para usar o IME, faça essas alterações no [!DNL Insight.cfg] arquivo:

   ```
   Localized IME = bool: true
   ```

   O Editor de método de entrada (IME) permite inserir caracteres internacionais.

1. (opcional) Edite o [!DNL Insight.cfg] para atualizar automaticamente o software:

   ```
   Update Software = bool: true
   ```

   Consulte as instruções para implementar o IME.
1. Reinicie novamente após a sincronização do perfil para usar o mais recente [!DNL .zbin] arquivo.

A instalação do cliente está concluída.
