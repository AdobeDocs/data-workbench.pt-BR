---
description: A funcionalidade de transformação é executada em uma máquina FSU do servidor Insight para permitir a exportação de dados de fonte de log para uso por outros aplicativos.
title: Configurar a transformação
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Configurar a transformação{#configuring-transform}

A funcionalidade de transformação é executada em uma máquina FSU do servidor Insight para permitir a exportação de dados de fonte de log para uso por outros aplicativos.

[!DNL Transform] pode ler  [!DNL .vsl] arquivos, arquivos de log, arquivos XML e dados ODBC e exportar os dados como  [!DNL .vsl] arquivos, arquivos de texto ou arquivos de texto delimitados que podem ser usados pelas rotinas de carregamento do data warehouse, agências de auditoria ou outros destinos. A extração e transformação de dados podem ser realizadas de forma contínua ou programada. Cada FSU [!DNL Insight Server] que fornece a saída de dados de evento alterados deve executar [!DNL Transform].

>[!NOTE]
>
>Normalmente, [!DNL Transform] é instalado em uma FSU [!DNL Insight Server]. No entanto, sua implementação pode exigir instalação em uma [!DNL Insight Server] DPU. Para obter mais informações, entre em contato com o Adobe.

Para obter informações sobre os requisitos do sistema para instalar, configurar e operar [!DNL Transform], consulte o documento *Requisitos mínimos do sistema*.

O Adobe distribui a funcionalidade [!DNL Transform] como um perfil dentro do arquivo [!DNL .zip] para o pacote de versão [!DNL Insight Server]. O perfil [!DNL Transform] é um perfil interno que fornece funcionalidade adicional para [!DNL Insight Server]. Assim como em todos os outros perfis internos fornecidos pelo Adobe, o perfil não deve ser alterado. Toda personalização deve ocorrer em seu conjunto de dados, em perfis específicos de função ou em outros perfis que você criar.

O perfil consiste nos seguintes arquivos:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* um arquivo de inclusão de conjunto de dados de processamento de log

Todos esses arquivos estão localizados na pasta [!DNL Dataset] do perfil.

**Para instalar o  [!DNL Transform] perfil no[!DNL Insight Server]**

>[!NOTE]
>
>As instruções de instalação a seguir pressupõem que você instalou [!DNL Insight] e estabeleceu uma conexão entre [!DNL Insight] e [!DNL Insight Server] na qual está instalando [!DNL Transform]. Se ainda não tiver feito isso, consulte o * [!DNL Insight] Guia do Usuário*.

1. Abra o arquivo [!DNL .zip] para o pacote de versão [!DNL Insight Server] e abra a pasta [!DNL Profiles] dentro desse arquivo [!DNL .zip].
1. Copie a pasta [!DNL Transform] para a pasta [!DNL Profiles] no diretório de instalação [!DNL Insight Server]. Você deseja terminar com uma pasta [!DNL ...\Profiles\Transform] em seu [!DNL Insight Server], como mostrado no exemplo a seguir.

   ![Informações da etapa](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Se você seguir todas as etapas para instalar [!DNL Insight Server] (consulte [Servidor Insight](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), talvez já tenha uma pasta [!DNL Transform] no diretório Perfis .

1. Use as etapas a seguir para atualizar o arquivo [!DNL profile.cfg] para o perfil com o qual você deseja usar [!DNL Transform]. O conjunto de dados é reprocessado após a conclusão dessas etapas.

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. A janela [!DNL profile.cfg] é exibida.

   1. Na janela [!DNL profile.cfg], clique com o botão direito do mouse em **[!UICONTROL Directories]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para adicionar o novo diretório ao final da lista de diretórios, clique com o botão direito do mouse no número ou nome do último diretório na lista e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digite o nome do novo diretório: [!DNL Transform]
   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL profile.cfg] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

      >[!NOTE]
      >
      >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe (incluindo o perfil), pois as alterações são substituídas ao instalar atualizações nesses perfis.
