---
description: Informações sobre como configurar o cluster no Principal Insight Server, atualizar o arquivo de controle de acesso para um cluster e muito mais.
title: Configurar o servidor Insight principal para clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Configurar o servidor Insight principal para clustering{#configuring-the-master-insight-server-for-clustering}

Informações sobre como configurar o cluster no Principal Insight Server, atualizar o arquivo de controle de acesso para um cluster e muito mais.

Para configurar o cluster, execute as seguintes etapas no [!DNL Insight Server] principal:

* Adicione os nomes e endereços comuns de processamento [!DNL Insight Servers’] ao arquivo de endereço.
* Adicione todos os [!DNL Insight Servers] ao grupo Servidores de Cluster no arquivo [!DNL Access Control.cfg].

* Atualize o arquivo [!DNL Synchronize.cfg] no diretório Componentes para Servidores de Processamento para apontar para o [!DNL Insight Server] principal.

* Se necessário, modifique o arquivo [!DNL Disk Files.cfg] no diretório Componentes para Servidores de Processamento para especificar o local do arquivo [!DNL temp.db] no processamento [!DNL Insight Servers].

Para concluir essas etapas, você precisa saber os nomes comuns (conforme especificado nos certificados digitais para o [!DNL Insight Server] individual) e os endereços IP de cada [!DNL Insight Server] no cluster. Se ainda não tiver essas informações, obtenha-as antes de continuar.

>[!NOTE]
>
>Os procedimentos descritos nesta seção exigem [!DNL Insight]. Se você não tiver instalado [!DNL Insight], siga as instruções no **[!DNL Insight]Guia do Usuário** antes de continuar.

## Adicionar os servidores Insight de processamento ao arquivo de endereço {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Use o procedimento a seguir para adicionar os nomes e endereços IP comuns de processamento [!DNL Insight Servers’] ao arquivo de endereço no [!DNL Insight Server] principal. (Embora o arquivo de endereço seja mantido e administrado no [!DNL Insight Server] principal, ele é usado por todos os [!DNL Insight Servers] no cluster.)

>[!NOTE]
>
>O seguinte assume que o arquivo de endereço já foi configurado para o [!DNL Insight Server] principal. Se você ainda não tiver adicionado o(s) endereço(s) IP principal(s) ao arquivo de endereço, conclua o procedimento descrito em [Definição do local de rede do servidor](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) antes de começar.[!DNL Insight Server’s]

**Para adicionar o processamento  [!DNL Insight Servers] ao arquivo de endereço**

1. Inicie [!DNL Insight] e carregue o Perfil de configuração (se ele ainda não estiver aberto) clicando com o botão direito do mouse na barra de título e clicando em **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.

1. Clique com o botão direito do mouse no ícone do principal **[!UICONTROL Insight Server]** e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], abra o diretório Endereços e faça o seguinte para abrir o arquivo de endereço [!DNL Insight Server’s]:

   1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda o conteúdo da estrutura [!DNL Locations] e, em seguida, expanda NetworkLocation 0, Addresses e AddressDefinition.
1. Faça o seguinte para adicionar AddressDefinition à NetworkLocation 0 para cada processamento [!DNL Insight Server] no cluster:

   1. Clique com o botão direito do mouse em **[!UICONTROL AddressDefinition]** e clique em **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. No parâmetro Name , especifique o nome comum de processamento [!DNL Insight Server’s].
   1. No parâmetro Address , especifique o endereço IP de processamento [!DNL Insight Server’s].

      É possível usar um asterisco como curinga no campo Endereço, como 10.10.116.*, para simplificar o clustering. Consulte [Compreender Níveis de Acesso](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      O exemplo a seguir define um cluster que contém dois [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Se os servidores estiverem conectados a várias redes, repita a Etapa 6 para adicionar o processamento [!DNL Insight Servers] ao NetworkLocations dessas redes.

   O exemplo a seguir mostra um cluster de quatro [!DNL Insight Servers] conectados a duas redes (&quot;Intranet Corporativa&quot; e &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Atualização do Arquivo de Controle de Acesso para um Cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Para usar [!DNL Insight Servers] em um cluster, cada [!DNL Insight Server] no cluster (incluindo o principal [!DNL Insight Server]) deve pertencer ao grupo de controle de acesso Servidores de Cluster. O grupo Servidores de Cluster identifica os servidores (por endereço IP) que têm permissão para participar do cluster. Embora esse arquivo seja mantido e administrado no [!DNL Insight Server] principal, ele é usado por todos os [!DNL Insight Servers] no cluster.

**Para editar o arquivo de controle de acesso**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.

1. Clique com o botão direito do mouse no ícone do principal [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], abra o diretório Controle de Acesso.
1. Faça o seguinte para abrir o arquivo [!DNL Access Control.cfg]:

   1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda a estrutura Grupos de Controle de Acesso e, em seguida, expanda AccessGroup (Servidores de Cluster).
1. Para cada [!DNL Insight Server] no cluster (incluindo o [!DNL Insight Server] principal), faça o seguinte:

   1. Clique com o botão direito do mouse em **[!UICONTROL Members]** e clique em **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Especifique o endereço IP [!DNL Insight Server’s] (seu endereço IP numérico, não seu nome). Se [!DNL Insight Servers] estiverem conectados a várias redes, esse AccessGroup deverá conter apenas os endereços internos que o [!DNL Insight Servers] usa para comunicação entre servidores no cluster.

      A seguir, é exibido o AccessGroup (Servidores de Cluster) para um cluster de quatro [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Configurar o arquivo de sincronização {#section-d23e751771c84da6bab6a34a8db867bc}

Você pode usar o procedimento a seguir para configurar a cópia central do arquivo [!DNL Synchronize.cfg]. A cópia central deste arquivo é mantida no principal [!DNL Insight Server]. O processamento [!DNL Insight Servers] no cluster inicia a comunicação com o [!DNL Insight Server] principal para recuperar uma cópia atualizada deste arquivo.

O arquivo [!DNL Synchronize.cfg] especifica o local do [!DNL Insight Server] principal. Também identifica o conjunto de arquivos administrativos que cada um dos [!DNL Insight Servers] de processamento no cluster recupera do [!DNL Insight Server] principal. O processamento [!DNL Insight Servers] baixa automaticamente esses arquivos do [!DNL Insight Server] principal quando eles começam. Eles também recuperam dinamicamente cópias atualizadas desses arquivos do [!DNL Insight Server] principal quando os arquivos forem alterados.

>[!NOTE]
>
>Embora você configure o arquivo [!DNL Synchronize.cfg] no [!DNL Insight Server] principal, o próprio [!DNL Insight Server] principal não usa esse arquivo. Você atualiza esse arquivo no [!DNL Insight Server] principal para que ele seja configurado corretamente quando o processamento [!DNL Insight Servers] recuperar o arquivo.

**Para atualizar o arquivo Synchronize.cfg no principal[!DNL Insight Server]**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.

1. Clique com o botão direito do mouse no ícone do principal [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.

1. Em [!DNL Server Files Manager], abra o diretório **[!UICONTROL Components]** para Servidores de Processamento.

1. Faça o seguinte para abrir [!DNL Synchronize.cfg]:

   1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda a estrutura do componente.
1. No parâmetro Endereço do servidor primário do cluster , especifique o endereço IP do principal (primário) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Para criar um log que registre cada vez que a sincronização ocorre entre o [!DNL Insight Server] principal e o processamento [!DNL Insight Servers], verifique se o parâmetro Ativar log de sincronização está definido como &quot;true&quot;.

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Em [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.

## Configurar a localização do conjunto de dados (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Execute o seguinte procedimento se desejar que o processamento [!DNL Insight Servers] mantenha [!DNL temp.db] (o conjunto de dados) em um diretório ou unidade diferente do local padrão ou se quiser distribuir [!DNL temp.db] em várias unidades.

>[!NOTE]
>
>Como o processamento [!DNL Insight Servers] compartilha o mesmo [!DNL Disk Files.cfg], todos devem suportar os locais de arquivo especificados neste arquivo. Por exemplo, se você atribuir [!DNL temp.db] ao E: , cada processamento [!DNL Insight Server] no cluster deve ter um E: unidade.

**Para configurar o local do temp.db**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.

1. Clique com o botão direito do mouse no ícone do principal [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], abra o diretório **[!UICONTROL Components for Processing Servers]**.

1. Faça o seguinte para abrir [!DNL Disk Files.cfg]:

   1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção na coluna [!DNL Temp]e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda a estrutura DiskSpaceManagerComponent e expanda a lista Arquivos de disco.
1. Edite a entrada 0 para alterar o local do arquivo [!DNL temp.db].
1. Se quiser distribuir [!DNL temp.db] entre várias unidades, use as etapas abaixo para criar uma entrada adicional para cada unidade adicional.

   1. Clique com o botão direito do mouse em **[!UICONTROL Disk Files]** e clique em **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Na nova entrada, especifique o local onde deseja que [!DNL temp.db] seja escrito.
   O exemplo a seguir mostra [!DNL temp.db] gravado em quatro unidades.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Em [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL Temp] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
