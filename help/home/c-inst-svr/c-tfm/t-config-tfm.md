---
description: A funcionalidade de transformação é executada em uma máquina FSU do servidor Insight para permitir a exportação de dados de fonte de log para uso por outros aplicativos.
title: Configurar a transformação
uuid: 0526704a-71b2-4094-9d3a-1ba84f4dc287
exl-id: 5dbd70e4-55fc-4446-b687-525e7957209b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Configurar a transformação{#configuring-transform}

{{eol}}

A funcionalidade de transformação é executada em uma máquina FSU do servidor Insight para permitir a exportação de dados de fonte de log para uso por outros aplicativos.

[!DNL Transform] ler [!DNL .vsl] arquivos, arquivos de log, arquivos XML e dados ODBC e exportar os dados como [!DNL .vsl] arquivos, arquivos de texto ou arquivos de texto delimitados que podem ser usados por rotinas de carregamento do data warehouse, agências de auditoria ou outros destinos. A extração e transformação de dados podem ser realizadas de forma contínua ou programada. Cada [!DNL Insight Server] FSU que fornece a saída de dados de evento alterados deve ser executada [!DNL Transform].

>[!NOTE]
>
>Normalmente, [!DNL Transform] está instalado em um [!DNL Insight Server] FSU. No entanto, sua implementação pode exigir instalação em um [!DNL Insight Server] DPU. Para obter mais informações, entre em contato com o Adobe.

Para obter informações sobre os requisitos do sistema para instalação, configuração e operação [!DNL Transform], consulte o *Requisitos mínimos do sistema* documento.

O Adobe distribui o [!DNL Transform] como um perfil dentro da função [!DNL .zip] para o [!DNL Insight Server] pacote de lançamento. O [!DNL Transform] é um perfil interno que fornece funcionalidade adicional para [!DNL Insight Server]. Assim como em todos os outros perfis internos fornecidos pelo Adobe, o perfil não deve ser alterado. Toda personalização deve ocorrer em seu conjunto de dados, em perfis específicos de função ou em outros perfis que você criar.

O perfil consiste nos seguintes arquivos:

* [!DNL Log Processing.cfg]
* [!DNL [!DNL Insight] Transform.cfg]
* [!DNL [!DNL Insight] Transform Mode.cfg]
* um arquivo de inclusão de conjunto de dados de processamento de log

Todos esses arquivos estão localizados na [!DNL Dataset] pasta do perfil.

**Para instalar o [!DNL Transform] perfil no[!DNL Insight Server]**

>[!NOTE]
>
>As instruções de instalação a seguir presumem que você instalou o [!DNL Insight] e estabeleceu uma ligação entre [!DNL Insight] e [!DNL Insight Server] no qual você está instalando o [!DNL Transform]. Se ainda não tiver feito isso, consulte o * [!DNL Insight] Guia do usuário*.

1. Abra o [!DNL .zip] para o [!DNL Insight Server] liberar pacote e abrir o [!DNL Profiles] dentro dessa [!DNL .zip] arquivo.
1. Copie o [!DNL Transform] para [!DNL Profiles] na sua pasta [!DNL Insight Server] diretório de instalação. Você quer acabar com um [!DNL ...\Profiles\Transform] na sua pasta [!DNL Insight Server] como mostrado no exemplo a seguir.

   ![Informações da etapa](assets/win_installTransformProfile.png)

   >[!NOTE]
   >
   >Se você seguir todas as etapas para instalar o [!DNL Insight Server] (consulte [Servidor Insight](../../../home/c-inst-svr/c-msr-server/c-msr-server.md)), você já pode ter uma [!DNL Transform] no diretório Profiles .

1. Use as etapas a seguir para atualizar o [!DNL profile.cfg] para o perfil com o qual você deseja usar [!DNL Transform]. O conjunto de dados é reprocessado após a conclusão dessas etapas.

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece no [!DNL User] coluna.

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. O [!DNL profile.cfg] será exibida.

   1. No [!DNL profile.cfg], clique com o botão direito do mouse **[!UICONTROL Directories]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para adicionar o novo diretório ao final da lista de diretórios, clique com o botão direito do mouse no número ou no nome do último diretório na lista e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digite o nome do novo diretório: [!DNL Transform]
   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL profile.cfg] no [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe (incluindo o perfil), pois as alterações são substituídas ao instalar atualizações nesses perfis.
