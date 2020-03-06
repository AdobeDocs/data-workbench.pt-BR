---
description: A funcionalidade de transformação é executada em uma máquina FSU do Insight Server para permitir a exportação de dados de origem de log para uso por outros aplicativos.
solution: Insight
title: Configurando a transformação
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Configurando a transformação{#configuring-transform}

A funcionalidade de transformação é executada em uma máquina FSU do Insight Server para permitir a exportação de dados de origem de log para uso por outros aplicativos.

[!DNL Transform] pode ler [!DNL .vsl] arquivos, arquivos de log, arquivos XML e dados ODBC e exportar os dados como [!DNL .vsl] arquivos, arquivos de texto ou arquivos de texto delimitados que podem ser usados pelas rotinas de carregamento do data warehouse, agências de auditoria ou outros destinos. A extração e transformação de dados podem ser realizadas de forma contínua ou programada. Cada [!DNL Insight Server] FSU que fornece saída de dados de eventos alterados deve ser executado [!DNL Transform].

>[!NOTE]
>
>Normalmente, [!DNL Transform] é instalado em um [!DNL Insight Server] FSU. No entanto, sua implementação pode exigir instalação em uma [!DNL Insight Server] DPU. Para obter mais informações, entre em contato com a Adobe.

Para obter informações sobre os requisitos do sistema para instalação, configuração e operação [!DNL Transform], consulte o documento Requisitos ** mínimos do sistema.

A Adobe distribui a [!DNL Transform] funcionalidade como um perfil dentro do [!DNL .zip] arquivo para o pacote de [!DNL Insight Server] versão. O [!DNL Transform] perfil é um perfil interno que fornece funcionalidade adicional para [!DNL Insight Server]. Assim como com todos os outros perfis internos fornecidos pela Adobe, o perfil não deve ser alterado. Toda personalização deve ocorrer em seu conjunto de dados ou em perfis específicos de função ou em outros perfis que você criar.

O perfil consiste nos seguintes arquivos:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* um conjunto de dados de processamento de log inclui um arquivo

Todos esses arquivos estão localizados na [!DNL Dataset] pasta do perfil.

**Para instalar o[!DNL Transform]perfil em[!DNL Insight Server]**

>[!NOTE]
>
>As instruções de instalação a seguir pressupõem que você instalou [!DNL Insight] e estabeleceu uma conexão entre [!DNL Insight] e o [!DNL Insight Server] local em que está instalando [!DNL Transform]. Se você não tiver feito isso, consulte o * Guia do usuário [!DNL Insight] *.

1. Abra o [!DNL .zip] arquivo do pacote de [!DNL Insight Server] versão e abra a [!DNL Profiles] pasta dentro desse [!DNL .zip] arquivo.
1. Copie a [!DNL Transform] pasta para a [!DNL Profiles] pasta no diretório [!DNL Insight Server] de instalação. Você deseja terminar com uma [!DNL ...\Profiles\Transform] pasta em sua página, [!DNL Insight Server] como mostrado no exemplo a seguir.

   ![Informações da etapa](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Se você seguiu todas as etapas para instalar [!DNL Insight Server] (consulte [Insight Server](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), talvez já tenha uma [!DNL Transform] pasta no diretório Perfis.

1. Use as seguintes etapas para atualizar o [!DNL profile.cfg] arquivo para o perfil com o qual você deseja usar [!DNL Transform]. O conjunto de dados é reprocessado após a conclusão dessas etapas.

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A [!DNL profile.cfg] janela é exibida.

   1. Na [!DNL profile.cfg]janela, clique com o botão direito do mouse **[!UICONTROL Directories]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para adicionar o novo diretório ao final da lista de diretórios, clique com o botão direito do mouse no número ou nome do último diretório na lista e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digite o nome do novo diretório: [!DNL Transform]
   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção para [!DNL profile.cfg] na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe (incluindo o perfil), pois suas alterações são substituídas quando você instala atualizações nesses perfis.

