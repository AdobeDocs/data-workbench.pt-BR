---
description: Informações sobre como configurar o cluster no Master Insight Server, atualizar o arquivo de controle de acesso para um cluster e muito mais.
solution: Insight
title: Configuração do Master Insight Server para Clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
translation-type: tm+mt
source-git-commit: b5a22e7a050d7c01570286dcb54e368f7ecdbcd8

---


# Configuração do Master Insight Server para Clustering{#configuring-the-master-insight-server-for-clustering}

Informações sobre como configurar o cluster no Master Insight Server, atualizar o arquivo de controle de acesso para um cluster e muito mais.

Para configurar o cluster, execute as seguintes etapas no mestre [!DNL Insight Server]:

* Adicione os nomes e endereços [!DNL Insight Servers’] comuns de processamento ao arquivo de endereço.
* Adicione todas as opções [!DNL Insight Servers] ao grupo Servidores de Cluster no [!DNL Access Control.cfg] arquivo.

* Atualize o [!DNL Synchronize.cfg] arquivo no diretório Componentes para Servidores de Processamento para apontar para o mestre [!DNL Insight Server].

* Se necessário, modifique o [!DNL Disk Files.cfg] arquivo no diretório Componentes para Servidores de Processamento para especificar o local do [!DNL temp.db] arquivo no processamento [!DNL Insight Servers].

Para concluir essas etapas, é necessário saber os nomes comuns (conforme especificados nos certificados digitais do indivíduo [!DNL Insight Server]) e os endereços IP de cada um [!DNL Insight Server] no cluster. Se você ainda não tiver essas informações, obtenha-as antes de continuar.

>[!NOTE]
>
>Os procedimentos descritos na presente seção exigem [!DNL Insight]. Se você não tiver instalado [!DNL Insight], siga as instruções no **[!DNL Insight]Guia **do usuário antes de continuar.

## Adicionando os Servidores de Informações de Processamento ao Arquivo de Endereço {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Use o procedimento a seguir para adicionar os nomes [!DNL Insight Servers’] comuns de processamento e os endereços IP ao arquivo de endereço no mestre [!DNL Insight Server]. (Embora o arquivo de endereço seja mantido e administrado no mestre [!DNL Insight Server], ele é usado por todos os usuários [!DNL Insight Servers] no cluster.)

>[!NOTE]
>
>O seguinte assume que o arquivo de endereço já foi configurado para o mestre [!DNL Insight Server]. Se você ainda não tiver adicionado os endereços [!DNL Insight Server’s] IP mestre ao arquivo de endereço, conclua o procedimento descrito em [Definindo o local](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) de rede do servidor antes de começar.

**Para adicionar o processamento[!DNL Insight Servers]ao arquivo de endereço**

1. Start [!DNL Insight] e carregue o perfil de configuração (se ainda não estiver aberto) clicando com o botão direito do mouse na barra de título e clicando em **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.

1. Clique com o botão direito do mouse no ícone da página mestre **[!UICONTROL Insight Server]** e clique em **[!UICONTROL Server Files]**.

1. No diretório [!DNL Server Files Manager], abra o diretório Endereços e faça o seguinte para abrir o arquivo de [!DNL Insight Server’s] endereço:

   1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda o conteúdo da [!DNL Locations] estrutura e, em seguida, expanda NetworkLocation 0, Addresses e AddressDefinition.
1. Faça o seguinte para adicionar AddressDefinition à NetworkLocation 0 para cada processamento [!DNL Insight Server] no cluster:

   1. Clique com o botão direito do mouse **[!UICONTROL AddressDefinition]** e clique em **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. No parâmetro Name, especifique o nome [!DNL Insight Server’s] comum de processamento.
   1. No parâmetro Address, especifique o endereço [!DNL Insight Server’s] IP de processamento.

      Você pode usar um asterisco como curinga no campo Endereço, como 10.10.116.*, para simplificar a organização por clusters. Consulte [Compreensão dos níveis](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a)de acesso.

      O exemplo a seguir define um cluster contendo dois [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Se os servidores estiverem conectados a várias redes, repita a Etapa 6 para adicionar o processamento [!DNL Insight Servers] aos NetworkLocations dessas redes.

   O exemplo a seguir mostra um cluster de quatro redes [!DNL Insight Servers] conectadas (&quot;Intranet corporativa&quot; e &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Atualização do Arquivo de Controle de acesso para um Cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Para usar [!DNL Insight Servers] em um cluster, cada um [!DNL Insight Server] no cluster (incluindo o mestre [!DNL Insight Server]) deve pertencer ao grupo de controles de acesso Servidores de Cluster. O grupo Servidores de Cluster identifica os servidores (por endereço IP) que podem participar do cluster. Embora esse arquivo seja mantido e administrado no mestre [!DNL Insight Server], ele é usado por todos os [!DNL Insight Servers] no cluster.

**Para editar o arquivo de controle de acesso**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.

1. Clique com o botão direito do mouse no ícone da página mestre [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.

1. No diretório [!DNL Server Files Manager], abra o diretório Controle de acesso.
1. Faça o seguinte para abrir o [!DNL Access Control.cfg] arquivo:

   1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda a estrutura Grupos de Controles de acesso e, em seguida, expanda AccessGroup (Servidores de Cluster).
1. Para cada um [!DNL Insight Server] no cluster (incluindo o mestre [!DNL Insight Server]), faça o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL Members]** e clique em **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Especifique o endereço [!DNL Insight Server’s] IP (seu endereço IP numérico, não seu nome). Se [!DNL Insight Servers] estiverem conectados a várias redes, esse AccessGroup deverá conter apenas os endereços internos que [!DNL Insight Servers] serão usados para a comunicação entre servidores no cluster.

      A seguir, é mostrado o AccessGroup (Cluster Servers) para um cluster de quatro [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuração do arquivo de sincronização {#section-d23e751771c84da6bab6a34a8db867bc}

Você pode usar o procedimento a seguir para configurar a cópia central do [!DNL Synchronize.cfg] arquivo. A cópia central deste arquivo é mantida no arquivo mestre [!DNL Insight Server]. O processamento [!DNL Insight Servers] no cluster inicia a comunicação com o mestre [!DNL Insight Server] para recuperar uma cópia atualizada deste arquivo.

O [!DNL Synchronize.cfg] arquivo especifica o local do mestre [!DNL Insight Server]. Ele também identifica o conjunto de arquivos administrativos que cada um dos processamentos [!DNL Insight Servers] no cluster recupera do mestre [!DNL Insight Server]. O processamento [!DNL Insight Servers] baixa automaticamente esses arquivos da página mestre [!DNL Insight Server] quando eles são start. Eles também recuperam dinamicamente cópias atualizadas desses arquivos do mestre [!DNL Insight Server] quando os arquivos mudam.

>[!NOTE]
>
>Embora você configure o [!DNL Synchronize.cfg] arquivo no arquivo mestre [!DNL Insight Server], o arquivo mestre [!DNL Insight Server] em si não o usa. Atualize esse arquivo no mestre [!DNL Insight Server] para que ele seja configurado corretamente quando o processamento [!DNL Insight Servers] recuperar o arquivo.

**Para atualizar o arquivo Synchronize.cfg no mestre[!DNL Insight Server]**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.

1. Clique com o botão direito do mouse no ícone da página mestre [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.

1. Em [!DNL Server Files Manager], abra o diretório **[!UICONTROL Components]** para Servidores de processamento.

1. Faça o seguinte para abrir [!DNL Synchronize.cfg]:

   1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de [!DNL Temp] seleção e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda a estrutura do componente.
1. No parâmetro Cluster Primary Server Address, especifique o endereço IP do mestre (primário) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Para criar um log que registra cada vez que a sincronização ocorre entre o mestre [!DNL Insight Server] e o processamento [!DNL Insight Servers], verifique se o parâmetro Ativar log de sincronização está definido como &quot;true&quot;.

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Em [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configuração da localização do conjunto de dados (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Execute o seguinte procedimento se desejar que o processamento seja mantido [!DNL Insight Servers] (o conjunto de dados) em um diretório ou unidade diferente do local padrão ou se desejar distribuir [!DNL temp.db] [!DNL temp.db] entre várias unidades.

>[!NOTE]
>
>Como todos os processamentos [!DNL Insight Servers] compartilham o mesmo [!DNL Disk Files.cfg], todos devem oferecer suporte aos locais de arquivo especificados neste arquivo. Por exemplo, se você atribuir [!DNL temp.db] ao E: , cada processamento [!DNL Insight Server] no cluster deve ter um E: dirigir.

**Para configurar o local de temp.db**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.

1. Clique com o botão direito do mouse no ícone da página mestre [!DNL Insight Server] e clique em **[!UICONTROL Server Files]**.

1. No [!DNL Server Files Manager], abra o **[!UICONTROL Components for Processing Servers]** diretório.

1. Faça o seguinte para abrir [!DNL Disk Files.cfg]:

   1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor e clique em **[!UICONTROL Make Local]**.

   1. Clique com o botão direito do mouse na marca de seleção na [!DNL Temp]coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Expanda a estrutura DiskSpaceManagerComponent e expanda a lista Arquivos de Disco.
1. Edite a entrada 0 para alterar o local do [!DNL temp.db] arquivo.
1. Se você quiser distribuir [!DNL temp.db] entre várias unidades, use as etapas abaixo para criar uma entrada adicional para cada unidade adicional.

   1. Clique com o botão direito do mouse **[!UICONTROL Disk Files]** e clique em **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Na nova entrada, especifique o local onde deseja [!DNL temp.db] gravar.
   A seguir, é exibido [!DNL temp.db] gravado em quatro unidades.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Em [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

