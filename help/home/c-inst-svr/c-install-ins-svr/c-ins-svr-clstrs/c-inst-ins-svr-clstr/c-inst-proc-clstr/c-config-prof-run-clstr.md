---
description: Quando você configura um perfil de conjunto de dados para ser executado em um cluster do Insight Server, todos os computadores no cluster compartilham todos os arquivos de configuração do conjunto de dados para esse perfil.
solution: Insight
title: Configuração de um perfil para execução em um cluster
uuid: e181d069-fb2f-4a71-a86f-bb9a48cfe059
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuração de um perfil para execução em um cluster{#configuring-a-profile-to-run-on-a-cluster}

Quando você configura um perfil de conjunto de dados para ser executado em um cluster do Insight Server, todos os computadores no cluster compartilham todos os arquivos de configuração do conjunto de dados para esse perfil.

Portanto, as entradas para os parâmetros nesses arquivos devem ser aplicáveis a todos [!DNL Insight Servers] no cluster. Por exemplo, os locais dos arquivos de log a serem lidos, os arquivos de pesquisa a serem usados por [!DNL Insight Server][!DNL Insight Server] e o local da saída de dados por devem ser os mesmos em todas as máquinas do cluster.

Você executa todas as tarefas de configuração no mestre do cluster [!DNL Insight Server], que é o [!DNL Insight Server] que você usa para editar seus arquivos de configuração. Todas as alterações de arquivo de configuração salvas feitas no mestre [!DNL Insight Server] são sincronizadas automaticamente com os arquivos no processamento [!DNL Insight Servers] no cluster.

Para executar um perfil de conjunto de dados em um [!DNL Insight Server] cluster, execute os seguintes processos na ordem listada:

1. [Determinando Quais Servidores Insight Processam Dados De Evento](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-59b8e3f2b34f49739d544c8740a62fba)
1. [Especificação dos servidores de processamento em Profile.cfg](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)
1. (Se necessário) [Modificando os arquivos de configuração do conjunto de dados para o perfil](../../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99bf9248e4e5483cb518f453b0a2f278)

## Determinando Quais Servidores Insight Processam Dados De Evento {#section-59b8e3f2b34f49739d544c8740a62fba}

Não é necessário que todos os dados do evento do processo de cluster [!DNL Insight Servers] sejam exibidos. Você pode designar um [!DNL Insight Server] no cluster como uma Unidade de Servidor de Arquivos que armazena os arquivos de origem (VSL e arquivos de log) e os serve a todas as Unidades de Processamento de Dados (servidores de processamento) no cluster. Essa configuração oferece o benefício de um único repositório de dados de eventos e aproveita o poder de processamento de todos os servidores de processamento no cluster. Os servidores de processamento dividem os arquivos de dados entre eles e garantem que o mesmo arquivo não seja processado mais de uma vez.

Para obter mais informações sobre como designar um usuário [!DNL Insight Server] para execução como uma Unidade de Servidor de Arquivos, consulte o capítulo Arquivo de Configuração de Processamento de Log do Guia *de Configuração de* Conjunto de Dados.

Se você decidir armazenar arquivos de dados de origem em cada um dos servidores de processamento em vez de em uma única Unidade de Servidor de Arquivos, deverá dividir os arquivos igualmente entre os servidores de processamento. Não armazene todos os arquivos de origem do conjunto de dados em cada um dos servidores de processamento. Se várias cópias do mesmo arquivo estiverem disponíveis para vários servidores de processamento, os dados serão lidos várias vezes (uma por cada máquina) e distorcerão seus dados.

Para obter ajuda sobre como determinar quais arquivos de registro devem ser processados, entre em contato com a Adobe Consulting. [!DNL Insight Servers]

## Especificação dos servidores de processamento em Profile.cfg {#section-99664e072c21462f91fbafb6d893fcf9}

No [!DNL profile.cfg] arquivo, especifique os servidores de processamento que processam os dados para o perfil.

**Para acessar o arquivo profile.cfg**

Você acessa o arquivo de configuração do perfil usando o [!DNL Profile Manager] em [!DNL Insight].

1. Ao trabalhar no perfil do conjunto de dados, abra o arquivo clicando com o botão direito do mouse [!DNL Profile Manager] em um espaço de trabalho e clicando em **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**, ou abrindo o espaço de trabalho Gerenciamento de perfil na [!DNL Admin] guia.

1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.

1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A janela de configuração do perfil é exibida.

**Para adicionar os Servidores de Processamento**

1. No [!DNL profile.cfg] arquivo, clique em **[!UICONTROL Profile]**, em seguida, clique **[!UICONTROL Processing Servers]** para exibir seu conteúdo.

1. Clique com o botão direito do mouse **[!UICONTROL Processing Servers]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Processing Server]**.

1. No parâmetro Common Name, digite o nome comum para o primeiro servidor de processamento no cluster. Por exemplo: [!DNL server1.mycompany.com]
1. Repita as Etapas 2 e 3 até ter adicionado os nomes comuns de todos os servidores de processamento no cluster.

   >[!NOTE]
   >
   >Se o mestre [!DNL Insight Server] processar dados, você também deverá adicioná-los.

1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

1. Clique com o botão direito do mouse na marca de seleção na [!DNL User] coluna ao lado de [!DNL profile.cfg]. Clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>*.

## Modificação dos arquivos de configuração do conjunto de dados para o perfil {#section-99bf9248e4e5483cb518f453b0a2f278}

**Para modificar os arquivos de configuração do conjunto de dados**

Se for necessário fazer alterações nos arquivos de configuração do conjunto de dados ( [!DNL Log Processing.cfg], [!DNL Transformation.cfg], o conjunto de dados inclui arquivos, [!DNL Log Processing Mode.cfg]e assim por diante), faça isso somente no mestre [!DNL Insight Server].

1. Acesse os arquivos que deseja modificar:

   Para obter instruções sobre como acessar os arquivos, consulte o Guia *de configuração de* conjuntos de dados.
1. Faça as alterações. Consulte o Guia *de configuração do* conjunto de dados para obter detalhes sobre os parâmetros no(s) arquivo(s) de configuração.
1. Salve o arquivo.

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Clique com o botão direito do mouse na marca de seleção na [!DNL User] coluna ao lado do nome do arquivo.
   1. Clique **[!UICONTROL Save to]** e selecione o perfil desejado.

>[!NOTE]
>
>[!DNL Insight] os usuários que acessam um perfil de conjunto de dados em execução em um cluster identificam somente o mestre [!DNL Insight Server] no arquivo de [!DNL Insight] configuração ( [!DNL insight.cfg]). Na perspectiva do [!DNL Insight] usuário, o perfil é acessível em apenas um [!DNL Insight Server] (o mestre [!DNL Insight Server]); no entanto, as solicitações de consulta dos analistas podem ser direcionadas para qualquer um dos [!DNL Insight Servers] no cluster.

Um [!DNL Insight Server] cluster permite o armazenamento centralizado de arquivos de [!DNL .vsl] log (de [!DNL Sensor]) em uma única [!DNL Insight Server] máquina chamada de Unidade de Servidor de Arquivos (FSU). Para obter informações sobre como instalar um FSU, consulte Procedimentos [de instalação para um FSU](../../../../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)do Insight Server. Para obter informações sobre como configurar um FSU, consulte o Guia *de configuração de* conjuntos de dados.
