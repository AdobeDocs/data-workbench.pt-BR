---
description: As novas dimensões que você cria usando a Análise de big data (conhecida como dimensões derivadas) são dimensões do cliente.
solution: Analytics
title: Trabalhar com dimensões derivadas
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trabalhar com dimensões derivadas{#work-with-derived-dimensions}

As novas dimensões que você cria usando a Análise de big data (conhecida como dimensões derivadas) são dimensões do cliente.

Em vez de definir essas dimensões durante a construção e o processo de atualização do conjunto de dados (no [!DNL Transformation.cfg] arquivo) nos computadores do servidor do Análise de big data, as dimensões derivadas são criadas e armazenadas individualmente como [!DNL .dim] arquivos em um perfil. Como resultado, você pode alterar as dimensões existentes e criar novas dimensões derivadas sem reprocessar seu conjunto de dados.

>[!NOTE]
>
>Para obter mais informações sobre dimensões do que as fornecidas nesta seção, consulte o guia de aplicativos da Análise de big data apropriado.

Para obter mais informações sobre a configuração e o processo de atualização do conjunto de dados, consulte o Guia *de Configuração do* Conjunto de Dados.

## Criar dimensões derivadas {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Para criar uma dimensão derivada, você pode copiar e modificar uma dimensão existente ou salvar uma dimensão de uma visualização.

## Criar dimensões derivadas de uma dimensão existente {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Os usuários geralmente querem criar novas dimensões de tempo a partir das existentes. Por exemplo, você pode criar uma nova dimensão &quot;Últimos 5 dias&quot; a partir da dimensão &quot;Últimos 7 dias&quot; existente.

1. Na [!DNL Profile Manager], na coluna nome *do* perfil, clique com o botão direito do mouse na marca de seleção de uma dimensão que seja semelhante à dimensão que você deseja criar e clique em **[!UICONTROL Copy]**.

   Por exemplo, para copiar a pasta [!DNL Last 7 Days.dim] de relatórios do [!DNL Traffic] perfil, clique com o botão direito do mouse na marca de seleção do nome do arquivo na [!DNL Traffic] coluna e clique em **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Clique com o botão direito do mouse na [!DNL User] coluna da pasta na qual deseja armazenar a dimensão copiada e clique em **[!UICONTROL Paste]**.

   A dimensão aparece na pasta Dimensões selecionada com uma marca de seleção na [!DNL User] coluna.

1. Para renomear a nova dimensão, clique com o botão direito do mouse em sua marca de seleção na [!DNL User] coluna e digite o novo nome no [!DNL File] campo.
1. No menu de clique com o botão direito do mouse, clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Os parâmetros de definição da dimensão são exibidos.
1. Modifique os parâmetros conforme necessário para definir a nova dimensão.

   Para dimensões de tempo, provavelmente você precisa modificar apenas os parâmetros Contagem e Intervalo.

1. Para salvar o arquivo, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   Se desejar que todos os usuários de um perfil usem a dimensão criada, faça upload dele para o perfil usando o [!DNL Profile Manager]. Para obter mais informações, consulte [Publicação de arquivos no seu perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabalho.

Agora você pode usar a nova dimensão em todo o perfil atual selecionando-a como faria com qualquer dimensão incorporada.

## Salvar uma dimensão de uma visualização {#section-84cfe5e9ccb640afa2ee4e2da2682757}

É possível salvar dimensões estendidas de mapas de processo e segmentos. Para obter etapas para salvar uma dimensão de um mapa de processos, consulte [Salvar dimensões de mapas](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051)de processos. Para obter etapas para salvar uma dimensão de segmento, consulte [Criação de dimensões](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) de segmento na página 82.

## Salvar um segmento como uma dimensão {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Também é possível salvar segmentos definidos como uma dimensão. Para obter etapas, consulte [Reutilização de uma visualização](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc)de segmento.

## Editar uma dimensão derivada existente {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   Na coluna [!DNL Profile Manager], nome *do* perfil, clique com o botão direito do mouse na marca de seleção do arquivo de dimensão que deseja editar e clique em **[!UICONTROL Make Local]**.
1. Clique com o botão direito do mouse na marca de seleção do arquivo de dimensão na [!DNL User] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Complete os parâmetros conforme necessário. Para obter mais informações, entre em contato com os Serviços de consultoria da Adobe.
1. Para salvar o arquivo, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   Se você deseja que todos os usuários de um perfil usem a dimensão modificada, faça upload dele para o perfil usando o [!DNL Profile Manager]. Para obter mais informações, consulte [Publicação de arquivos no seu perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabalho.

