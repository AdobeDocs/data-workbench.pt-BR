---
description: Ao configurar um perfil de conjunto de dados para ser executado em um cluster do Insight Server, todos os computadores no cluster compartilham todos os arquivos de configuração de conjunto de dados desse perfil.
title: Configurar um perfil para execução em um cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Configurar um perfil para execução em um cluster{#configuring-a-profile-to-run-on-a-cluster}

{{eol}}

Ao configurar um perfil de conjunto de dados para ser executado em um cluster do Insight Server, todos os computadores no cluster compartilham todos os arquivos de configuração de conjunto de dados desse perfil.

Portanto, as entradas para os parâmetros nesses arquivos devem ser aplicáveis a todos [!DNL Insight Servers] no cluster. Por exemplo, os locais dos arquivos de log a serem lidos, os arquivos de pesquisa a serem usados por [!DNL Insight Server]e a localização da saída de dados por [!DNL Insight Server] deve ser o mesmo em todas as máquinas do cluster.

Você executa todas as tarefas de configuração no principal do cluster [!DNL Insight Server], que é o [!DNL Insight Server] você usa para editar seus arquivos de configuração. Todas as alterações do arquivo de configuração salvas feitas na principal [!DNL Insight Server] são sincronizados automaticamente com os arquivos no processamento [!DNL Insight Servers] no cluster.

Para executar um perfil de conjunto de dados em um [!DNL Insight Server] , você deve executar os seguintes processos na ordem listada:

1. [Determinar quais servidores Insight processam dados de evento](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Especificação dos servidores de processamento no Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Se necessário) [Modificar os arquivos de configuração do conjunto de dados para o perfil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Determinar quais servidores Insight processam dados de evento {#section-59b8e3f2b34f49739d544c8740a62fba}

Não é necessário que todas as [!DNL Insight Servers] nos dados de evento do processo de cluster. Você pode designar um [!DNL Insight Server] no cluster como uma unidade de servidor de arquivos que armazena os arquivos de origem (arquivos de VSL e log) e os serve a todas as unidades de processamento de dados (servidores de processamento) no cluster. Essa configuração oferece o benefício de um único repositório de dados de evento e aproveita o poder de processamento de todos os servidores de processamento no cluster. Os servidores de processamento dividem os arquivos de dados entre eles e garantem que o mesmo arquivo não seja processado mais de uma vez.

Para obter mais informações sobre a designação de um [!DNL Insight Server] para executar como uma unidade de servidor de arquivos, consulte o capítulo Arquivo de configuração de processamento de log do *Guia de configuração do conjunto de dados*.

Se você decidir armazenar arquivos de dados de origem em cada um dos servidores de processamento em vez de em uma única Unidade de Servidor de Arquivos, deverá dividir os arquivos igualmente entre os servidores de processamento. Não armazene todos os arquivos de origem do conjunto de dados em cada um dos servidores de processamento. Se várias cópias do mesmo arquivo estiverem disponíveis para vários servidores de processamento, os dados serão lidos várias vezes (uma por cada máquina) e seus dados serão ignorados.

Para obter ajuda sobre como determinar [!DNL Insight Servers] caso processe arquivos de log, entre em contato com a Adobe Consulting.

## Especificação dos servidores de processamento no Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

No [!DNL profile.cfg] , especifique os servidores de processamento que processam os dados do perfil.

**Para acessar o arquivo profile.cfg**

Você acessa o arquivo de configuração de perfil usando o [!DNL Profile Manager] em [!DNL Insight].

1. Ao trabalhar no perfil do conjunto de dados, abra o [!DNL Profile Manager] clicando com o botão direito do mouse em um espaço de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]** ou abrindo a área de trabalho Gerenciamento de perfil no [!DNL Admin] guia .

1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.

1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A janela de configuração de perfil é exibida.

**Para adicionar os servidores de processamento**

1. No [!DNL profile.cfg] , clique em **[!UICONTROL Profile]**, depois clique em **[!UICONTROL Processing Servers]** para exibir seu conteúdo.

1. Clique com o botão direito do mouse **[!UICONTROL Processing Servers]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. No parâmetro Common Name, digite o nome comum para o primeiro servidor de processamento no cluster. Por exemplo: [!DNL server1.mycompany.com]
1. Repita as Etapas 2 e 3 até ter adicionado os nomes comuns de todos os servidores de processamento no cluster.

   >[!NOTE]
   >
   >Se o principal [!DNL Insight Server] processa dados, você também deve adicioná-los.

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

1. Clique com o botão direito do mouse na marca de seleção no [!DNL User] coluna ao lado de [!DNL profile.cfg]. Clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modificar os arquivos de configuração do conjunto de dados para o perfil {#section-99bf9248e4e5483cb518f453b0a2f278}

**Como modificar os arquivos de configuração do conjunto de dados**

Se precisar fazer alterações nos arquivos de configuração do conjunto de dados ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], arquivos de inclusão do conjunto de dados, [!DNL Log Processing Mode.cfg]e assim por diante), faça isso somente na principal [!DNL Insight Server].

1. Acesse os arquivos que deseja modificar:

   Para obter instruções para acessar os arquivos, consulte a *Guia de configuração do conjunto de dados*.
1. Faça as alterações. Consulte a *Guia de configuração do conjunto de dados* para obter detalhes sobre os parâmetros no(s) arquivo(s) de configuração.
1. Salve o arquivo.

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Clique com o botão direito do mouse na marca de seleção no [!DNL User] ao lado do nome do arquivo.
   1. Clique em **[!UICONTROL Save to]** e selecione o perfil desejado.

>[!NOTE]
>
>[!DNL Insight] os usuários que acessam um perfil de conjunto de dados em execução em um cluster identificam somente o principal [!DNL Insight Server] no [!DNL Insight] arquivo de configuração ( [!DNL insight.cfg]). Da perspectiva do [!DNL Insight] usuário, o perfil pode ser acessado em apenas um [!DNL Insight Server] (o principal [!DNL Insight Server]); no entanto, as solicitações de consulta dos analistas podem ser direcionadas para qualquer um dos [!DNL Insight Servers] no cluster.

Um [!DNL Insight Server] cluster permite o armazenamento centralizado de [!DNL .vsl] arquivos de log (de [!DNL Sensor]) em um único [!DNL Insight Server] chamada de unidade de servidor de arquivos (FSU). Para obter informações sobre como instalar uma FSU, consulte [Procedimentos de instalação para uma FSU do servidor Insight](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Para obter informações sobre como configurar uma FSU, consulte o *Guia de configuração do conjunto de dados*.
