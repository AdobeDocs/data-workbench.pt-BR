---
description: As novas dimensões criadas usando o Data Workbench (chamadas de dimensões derivadas) são dimensões do lado do cliente.
title: Trabalhar com dimensões derivadas
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Trabalhar com dimensões derivadas{#work-with-derived-dimensions}

As novas dimensões criadas usando o Data Workbench (chamadas de dimensões derivadas) são dimensões do lado do cliente.

Em vez de definir essas dimensões durante a construção do conjunto de dados e o processo de atualização (no arquivo [!DNL Transformation.cfg]) nos computadores do servidor do Data Workbench, as dimensões derivadas são criadas e armazenadas individualmente como arquivos [!DNL .dim] em um perfil. Como resultado, é possível alterar as dimensões existentes e criar novas dimensões derivadas sem reprocessar o conjunto de dados.

>[!NOTE]
>
>Para obter mais informações sobre dimensões do que as fornecidas nesta seção, consulte o guia de aplicativos do Data Workbench apropriado.

Para obter mais informações sobre a configuração do conjunto de dados e o processo de atualização, consulte o *Guia de Configuração do Conjunto de Dados*.

## Criar dimensões derivadas {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Para criar uma dimensão derivada, você pode copiar e modificar uma dimensão existente ou salvar uma dimensão de uma visualização.

## Crie dimensões derivadas de uma dimensão existente {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Os usuários frequentemente desejam criar novas dimensões de tempo a partir das existentes. Por exemplo, você pode criar uma nova dimensão &quot;Últimos 5 dias&quot; a partir da dimensão &quot;Últimos 7 dias&quot; existente.

1. Na coluna [!DNL Profile Manager], na coluna *nome do perfil*, clique com o botão direito do mouse na marca de seleção de uma dimensão semelhante à dimensão que você deseja criar e clique em **[!UICONTROL Copy]**.

   Por exemplo, para copiar o [!DNL Last 7 Days.dim] da pasta Relatório do perfil [!DNL Traffic], clique com o botão direito do mouse na marca de seleção do nome do arquivo na coluna [!DNL Traffic] e clique em **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Clique com o botão direito do mouse na coluna [!DNL User] da pasta na qual deseja armazenar a dimensão copiada e clique em **[!UICONTROL Paste]**.

   A dimensão aparece na pasta Dimension selecionada com uma marca de seleção na coluna [!DNL User].

1. Para renomear a nova dimensão, clique com o botão direito do mouse na marca de seleção na coluna [!DNL User] e digite o novo nome no campo [!DNL File].
1. No menu de contexto, clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Os parâmetros de definição da dimensão são exibidos.
1. Modifique os parâmetros conforme necessário para definir a nova dimensão.

   Para dimensões de tempo, provavelmente você precisa modificar apenas os parâmetros Contagem e Intervalo .

1. Para salvar o arquivo, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   Se quiser que todos os usuários de um perfil usem a dimensão que você criou, faça upload dele para o perfil usando o [!DNL Profile Manager]. Para obter mais informações, consulte [Publicar arquivos no seu perfil de trabalho](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Agora é possível usar a nova dimensão em todo o perfil atual, selecionando-a como faria com qualquer dimensão incorporada.

## Salvar uma dimensão de uma visualização {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Você pode salvar dimensões estendidas de mapas de processos e segmentos. Para obter etapas para salvar uma dimensão de um mapa de processos, consulte [Salvar Dimension de Mapas de processos](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Para obter etapas para salvar uma dimensão de segmento, consulte [Criação de Dimension de segmento](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) na página 82.

## Salvar um segmento como uma dimensão {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Também é possível salvar segmentos definidos como uma dimensão. Para etapas, consulte [Reutilizar uma visualização de segmento](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Editar uma dimensão derivada existente {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   No [!DNL Profile Manager], na coluna *nome do perfil*, clique com o botão direito do mouse na marca de seleção do arquivo de dimensão que deseja editar e clique em **[!UICONTROL Make Local]**.
1. Clique com o botão direito do mouse na marca de seleção do arquivo de dimensão na coluna [!DNL User] e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Complete os parâmetros, conforme necessário. Para obter mais informações, entre em contato com os Serviços de consultoria do Adobe.
1. Para salvar o arquivo, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   Se quiser que todos os usuários de um perfil usem a dimensão modificada, faça upload dele para o perfil usando o [!DNL Profile Manager]. Para obter mais informações, consulte [Publicar arquivos no seu perfil de trabalho](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
