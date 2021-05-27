---
description: Ao configurar um perfil de conjunto de dados para ser executado em um cluster do Insight Server, todos os computadores no cluster compartilham todos os arquivos de configuração de conjunto de dados desse perfil.
title: Configurar um perfil para execução em um cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
exl-id: be8090fc-b3da-41c4-a5d4-c6eb85b8a84d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 3%

---

# Configurar um perfil para execução em um cluster{#configuring-a-profile-to-run-on-a-cluster}

Ao configurar um perfil de conjunto de dados para ser executado em um cluster do Insight Server, todos os computadores no cluster compartilham todos os arquivos de configuração de conjunto de dados desse perfil.

Portanto, as entradas para os parâmetros nesses arquivos devem ser aplicáveis a todos [!DNL Insight Servers] no cluster. Por exemplo, os locais dos arquivos de log a serem lidos, os arquivos de pesquisa a serem usados por [!DNL Insight Server] e o local da saída de dados por [!DNL Insight Server] devem ser iguais em todas as máquinas no cluster.

Você executa todas as tarefas de configuração no [!DNL Insight Server] principal do cluster, que é o [!DNL Insight Server] usado para editar seus arquivos de configuração. Todas as alterações salvas no arquivo de configuração feitas no [!DNL Insight Server] principal são sincronizadas automaticamente nos arquivos no processamento [!DNL Insight Servers] no cluster.

Para executar um perfil de conjunto de dados em um cluster [!DNL Insight Server], você deve executar os seguintes processos na ordem listada:

1. [Determinar quais servidores Insight processam dados de evento](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Especificação dos servidores de processamento no Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Se necessário) [Modificar os arquivos de configuração do conjunto de dados para o perfil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Determinando quais servidores Insight processam dados de evento {#section-59b8e3f2b34f49739d544c8740a62fba}

Não é necessário que todos os [!DNL Insight Servers] no processo de cluster processem dados de evento. Você pode designar um [!DNL Insight Server] no cluster como uma Unidade de Servidor de Arquivos que armazena os arquivos de origem (VSL e arquivos de log) e os serve a todas as Unidades de Processamento de Dados (servidores de processamento) no cluster. Essa configuração oferece o benefício de um único repositório de dados de evento e aproveita o poder de processamento de todos os servidores de processamento no cluster. Os servidores de processamento dividem os arquivos de dados entre eles e garantem que o mesmo arquivo não seja processado mais de uma vez.

Para obter mais informações sobre como designar um [!DNL Insight Server] para ser executado como uma Unidade de Servidor de Arquivos, consulte o capítulo Arquivo de Configuração de Processamento de Log do *Guia de Configuração de Conjunto de Dados*.

Se você decidir armazenar arquivos de dados de origem em cada um dos servidores de processamento em vez de em uma única Unidade de Servidor de Arquivos, deverá dividir os arquivos igualmente entre os servidores de processamento. Não armazene todos os arquivos de origem do conjunto de dados em cada um dos servidores de processamento. Se várias cópias do mesmo arquivo estiverem disponíveis para vários servidores de processamento, os dados serão lidos várias vezes (uma por cada máquina) e seus dados serão ignorados.

Para obter ajuda para determinar qual [!DNL Insight Servers] deve processar arquivos de log, entre em contato com a Adobe Consulting.

## Especificação dos servidores de processamento em Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

No arquivo [!DNL profile.cfg] , especifique os servidores de processamento que processam os dados do perfil.

**Para acessar o arquivo profile.cfg**

Você acessa o arquivo de configuração de perfil usando [!DNL Profile Manager] em [!DNL Insight].

1. Ao trabalhar no perfil do conjunto de dados, abra o [!DNL Profile Manager] clicando com o botão direito do mouse em um espaço de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**, ou abrindo o espaço de trabalho Gerenciamento de perfil na guia [!DNL Admin].

1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].

1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A janela de configuração de perfil é exibida.

**Para adicionar os servidores de processamento**

1. No arquivo [!DNL profile.cfg], clique em **[!UICONTROL Profile]**, em seguida, clique em **[!UICONTROL Processing Servers]** para exibir seu conteúdo.

1. Clique com o botão direito do mouse em **[!UICONTROL Processing Servers]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. No parâmetro Common Name, digite o nome comum para o primeiro servidor de processamento no cluster. Por exemplo: [!DNL server1.mycompany.com]
1. Repita as Etapas 2 e 3 até ter adicionado os nomes comuns de todos os servidores de processamento no cluster.

   >[!NOTE]
   >
   >Se o [!DNL Insight Server] principal processar dados, você também deverá adicioná-los.

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

1. Clique com o botão direito do mouse na marca de seleção na coluna [!DNL User] ao lado de [!DNL profile.cfg]. Clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modificar os arquivos de configuração do conjunto de dados para o perfil {#section-99bf9248e4e5483cb518f453b0a2f278}

**Como modificar os arquivos de configuração do conjunto de dados**

Se você precisar fazer alterações nos arquivos de configuração do conjunto de dados ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], arquivos de inclusão do conjunto de dados, [!DNL Log Processing Mode.cfg] e assim por diante), faça isso somente no [!DNL Insight Server] principal.

1. Acesse os arquivos que deseja modificar:

   Para obter instruções para acessar os arquivos, consulte o *Guia de Configuração de Conjunto de Dados*.
1. Faça as alterações. Consulte o *Guia de Configuração do Conjunto de Dados* para obter detalhes sobre os parâmetros no(s) arquivo(s) de configuração.
1. Salve o arquivo.

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Clique com o botão direito do mouse na marca de seleção na coluna [!DNL User] ao lado do nome do arquivo.
   1. Clique em **[!UICONTROL Save to]** e selecione o perfil desejado.

>[!NOTE]
>
>[!DNL Insight] os usuários que acessam um perfil de conjunto de dados em execução em um cluster identificam somente o principal  [!DNL Insight Server] no arquivo  [!DNL Insight] de configuração (  [!DNL insight.cfg]). Da perspectiva do usuário [!DNL Insight], o perfil é acessível em apenas um [!DNL Insight Server] (o principal [!DNL Insight Server]); no entanto, as solicitações de consulta dos analistas podem ser direcionadas para qualquer um dos [!DNL Insight Servers] no cluster.

Um cluster [!DNL Insight Server] permite o armazenamento centralizado de [!DNL .vsl] arquivos de log (de [!DNL Sensor]) em uma única máquina [!DNL Insight Server] chamada Unidade de Servidor de Arquivos (FSU). Para obter informações sobre como instalar um FSU, consulte [Procedimentos de instalação para um FSU do servidor Insight](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). Para obter informações sobre como configurar uma FSU, consulte o *Guia de Configuração de Conjunto de Dados*.
