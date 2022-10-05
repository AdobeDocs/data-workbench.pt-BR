---
description: Informações sobre como configurar o cluster no Principal Insight Server, atualizar o arquivo de controle de acesso para um cluster e muito mais.
title: Configurar o servidor Insight principal para clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Configurar o servidor Insight principal para clustering{#configuring-the-master-insight-server-for-clustering}

{{eol}}

Informações sobre como configurar o cluster no Principal Insight Server, atualizar o arquivo de controle de acesso para um cluster e muito mais.

Para configurar o cluster, execute as seguintes etapas no principal [!DNL Insight Server]:

* Adicionar o processamento [!DNL Insight Servers’] nomes e endereços comuns do arquivo de endereço.
* Adicione todas as [!DNL Insight Servers] para o grupo Servidores de Cluster na [!DNL Access Control.cfg] arquivo.

* Atualize o [!DNL Synchronize.cfg] no diretório Componentes para Servidores de Processamento para apontar para o principal [!DNL Insight Server].

* Se necessário, modifique o [!DNL Disk Files.cfg] no diretório Componentes para Servidores de Processamento para especificar o local da variável [!DNL temp.db] no processamento [!DNL Insight Servers].

Para concluir essas etapas, é necessário conhecer os nomes comuns (conforme especificado nos certificados digitais do indivíduo [!DNL Insight Server]) e os endereços IP de cada [!DNL Insight Server] no cluster. Se ainda não tiver essas informações, obtenha-as antes de continuar.

>[!NOTE]
>
>Os procedimentos descritos nesta seção exigem [!DNL Insight]. Se você não tiver instalado o [!DNL Insight]siga as instruções em **[!DNL Insight]Guia do usuário** antes de continuar.

## Adicionar os servidores Insight de processamento ao arquivo de endereço {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Use o procedimento a seguir para adicionar o processamento [!DNL Insight Servers’] nomes e endereços IP comuns para o arquivo de endereço na principal [!DNL Insight Server]. (Embora o arquivo de endereço seja mantido e administrado no principal [!DNL Insight Server], ele é usado por todas as [!DNL Insight Servers] no cluster.)

>[!NOTE]
>
>O seguinte assume que o arquivo de endereço já foi configurado para o principal [!DNL Insight Server]. Se você ainda não tiver adicionado o principal [!DNL Insight Server’s] Endereço(s) IP para o arquivo de endereço, conclua o procedimento descrito em [Definir o local de rede do servidor](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) antes de começar.

**Para adicionar o processamento [!DNL Insight Servers] ao arquivo de endereço**

1. Iniciar [!DNL Insight] e carregue o Perfil de configuração (se ele ainda não estiver aberto) clicando com o botão direito do mouse na barra de título e clicando em **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. Em [!DNL Insight], no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir o espaço de trabalho do Gerenciador de Servidores.

1. Clique com o botão direito do mouse no ícone da principal **[!UICONTROL Insight Server]** e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], abra o diretório Endereços e faça o seguinte para abrir o [!DNL Insight Server’s] arquivo de endereço:

   1. Clique com o botão direito do mouse na marca de seleção no *nome do servidor* e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção no [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda o conteúdo da variável [!DNL Locations] e expanda NetworkLocation 0, Addresses e AddressDefinition.
1. Faça o seguinte para adicionar um AddressDefinition à NetworkLocation 0 para cada processamento [!DNL Insight Server] no cluster:

   1. Clique com o botão direito do mouse **[!UICONTROL AddressDefinition]** e clique em **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. No parâmetro Nome , especifique o processamento [!DNL Insight Server’s] nome comum.
   1. No parâmetro Address , especifique o processamento [!DNL Insight Server’s] Endereço IP.

      É possível usar um asterisco como curinga no campo Endereço, como 10.10.116.&#42;, para simplificar o clustering. Consulte [Compreender níveis de acesso](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      O exemplo a seguir define um cluster que contém dois [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Se os servidores estiverem conectados a várias redes, repita a Etapa 6 para adicionar o processamento [!DNL Insight Servers] à NetworkLocations dessas redes.

   O exemplo a seguir mostra um cluster de quatro [!DNL Insight Servers] conectadas a duas redes (&quot;Intranet Corporativa&quot; e &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Atualização do Arquivo de Controle de Acesso para um Cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Para usar [!DNL Insight Servers] em um cluster, cada [!DNL Insight Server] no cluster (incluindo o principal [!DNL Insight Server]) deve pertencer ao grupo de controle de acesso Servidores de Cluster. O grupo Servidores de Cluster identifica os servidores (por endereço IP) que têm permissão para participar do cluster. Embora este ficheiro seja mantido e administrado na principal [!DNL Insight Server], é usado por todos os [!DNL Insight Servers] no cluster.

**Para editar o arquivo de controle de acesso**

1. Em [!DNL Insight], no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir o espaço de trabalho do Gerenciador de Servidores.

1. Clique com o botão direito do mouse no ícone da principal [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], abra o diretório Controle de acesso .
1. Faça o seguinte para abrir o [!DNL Access Control.cfg] arquivo:

   1. Clique com o botão direito do mouse na marca de seleção no *nome do servidor* e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção no [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda a estrutura Grupos de Controle de Acesso e, em seguida, expanda AccessGroup (Servidores de Cluster).
1. Para cada [!DNL Insight Server] no cluster (incluindo o principal [!DNL Insight Server]), faça o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL Members]** e clique em **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Especifique a [!DNL Insight Server’s] Endereço IP (seu endereço IP numérico, não seu nome). Se a variável [!DNL Insight Servers] estão conectados a várias redes, esse AccessGroup deve conter apenas os endereços internos que [!DNL Insight Servers] use para comunicação entre servidores no cluster.

      Veja a seguir o AccessGroup (Servidores de Cluster) para um cluster de quatro [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL Temp] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configurar o arquivo de sincronização {#section-d23e751771c84da6bab6a34a8db867bc}

Você pode usar o procedimento a seguir para configurar a cópia central do [!DNL Synchronize.cfg] arquivo. A cópia central deste arquivo é mantida na principal [!DNL Insight Server]. O processamento [!DNL Insight Servers] no cluster, inicie a comunicação com o principal [!DNL Insight Server] para recuperar uma cópia atualizada deste arquivo.

O [!DNL Synchronize.cfg] especifica o local do principal [!DNL Insight Server]. Também identifica o conjunto de arquivos administrativos que cada um dos processos processam [!DNL Insight Servers] no cluster recupera do principal [!DNL Insight Server]. O processamento [!DNL Insight Servers] baixe automaticamente esses arquivos da principal [!DNL Insight Server] quando começarem. Eles também recuperam dinamicamente cópias atualizadas desses arquivos do principal [!DNL Insight Server] quando os arquivos mudarem.

>[!NOTE]
>
>Embora você configure a variável [!DNL Synchronize.cfg] no principal [!DNL Insight Server], o principal [!DNL Insight Server] O próprio não utiliza este ficheiro. Você atualiza este arquivo na principal [!DNL Insight Server] para que seja configurado corretamente durante o processamento [!DNL Insight Servers] recupere o arquivo.

**Para atualizar o arquivo Synchronize.cfg no principal[!DNL Insight Server]**

1. Em [!DNL Insight], no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir o espaço de trabalho do Gerenciador de Servidores.

1. Clique com o botão direito do mouse no ícone da principal [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.

1. Em [!DNL Server Files Manager], abra o **[!UICONTROL Components]** para o diretório Servidores de Processamento.

1. Faça o seguinte para abrir [!DNL Synchronize.cfg]:

   1. Clique com o botão direito do mouse na marca de seleção no *nome do servidor* e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse no [!DNL Temp] marque e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda a estrutura do componente.
1. No parâmetro Endereço do Servidor Principal do Cluster, especifique o endereço IP do principal (primário) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Para criar um log que registre cada vez que a sincronização ocorre entre a principal [!DNL Insight Server] e a transformação [!DNL Insight Servers], verifique se o parâmetro Ativar log de sincronização está definido como &quot;true&quot;.

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Em [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL Temp] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configurar a localização do conjunto de dados (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Execute o seguinte procedimento se desejar que o processamento [!DNL Insight Servers] manter [!DNL temp.db] (o conjunto de dados) em um diretório ou unidade diferente do local padrão ou se você deseja distribuir [!DNL temp.db] em várias unidades.

>[!NOTE]
>
>Como o processamento [!DNL Insight Servers] todos compartilham o mesmo [!DNL Disk Files.cfg], todos devem suportar os locais de arquivo especificados neste arquivo. Por exemplo, se você atribuir [!DNL temp.db] à E: unidade, cada processamento [!DNL Insight Server] no cluster deve ter um E: unidade.

**Para configurar o local do temp.db**

1. Em [!DNL Insight], no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir o espaço de trabalho do Gerenciador de Servidores.

1. Clique com o botão direito do mouse no ícone da principal [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], abra o **[!UICONTROL Components for Processing Servers]** diretório.

1. Faça o seguinte para abrir [!DNL Disk Files.cfg]:

   1. Clique com o botão direito do mouse na marca de seleção no *nome do servidor* e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção no [!DNL Temp]e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda a estrutura DiskSpaceManagerComponent e expanda a lista Arquivos de disco.
1. Edite a entrada 0 para alterar a localização do [!DNL temp.db] arquivo.
1. Se quiser distribuir [!DNL temp.db] em várias unidades, use as etapas abaixo para criar uma entrada adicional para cada unidade adicional.

   1. Clique com o botão direito do mouse **[!UICONTROL Disk Files]** e clique em **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Na nova entrada, especifique o local onde deseja [!DNL temp.db] escrito.
   O exemplo a seguir mostra [!DNL temp.db] gravado em quatro unidades.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Em [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL Temp] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
