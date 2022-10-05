---
description: Informações sobre adicionar, remover ou copiar uma condição.
title: Trabalhar com condições
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
exl-id: 0792b308-aa0b-4741-be0c-4f7cc28f3e09
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Trabalhar com condições{#working-with-conditions}

{{eol}}

Informações sobre adicionar, remover ou copiar uma condição.

* [Para adicionar uma condição a um arquivo de configuração de conjunto de dados](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511)
* [Para remover uma condição de um arquivo de configuração de conjunto de dados](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540)
* [Para copiar uma condição](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## Para adicionar uma condição a um arquivo de configuração de conjunto de dados {#section-3e2a34db047b462585502f69722f6511}

1. Ao trabalhar no perfil do conjunto de dados, use a variável [!DNL Profile Manager] para abrir o arquivo de configuração do conjunto de dados que deseja editar.

   * Para abrir o [!DNL Log Processing.cfg] arquivo, consulte [Editar o arquivo de configuração de processamento de log](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

   * Para abrir o [!DNL Transformation.cfg] arquivo, consulte [Editar o arquivo de configuração de transformação](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

   * Para abrir um [!DNL Dataset Include] arquivo, consulte [Arquivos de inclusão do conjunto de dados](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. No arquivo de configuração do conjunto de dados, localize a Condição de entrada de log ou o parâmetro de condição que você deseja definir.
1. Clique com o botão direito do mouse no parâmetro e clique em **[!UICONTROL Add new]**. Escolha um dos seguintes tipos de condição:

   * [!DNL Not Empty]
   * [!DNL String Match]
   * [!DNL Regular Expression]
   * [!DNL Range]
   * [!DNL And]
   * [!DNL Or]
   * [!DNL Neither]
   * [!DNL Compare]

1. Edite os parâmetros da condição conforme desejado. Para obter descrições dos parâmetros de cada condição, consulte a seção apropriada do presente apêndice.
1. Para salvar as alterações, clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager,] clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] e, em seguida, clique em **[!UICONTROL Save to]** > &lt;* **[!UICONTROL profile name]***>, onde o nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o arquivo pertence.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.

## Para remover uma condição de um arquivo de configuração de conjunto de dados {#section-677270f93f1648c3a268ca2aea7d4540}

1. Clique com o botão direito do mouse no nome da condição ou no número correspondente à condição que deseja remover.
1. Clique em **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, onde number é o número correspondente à condição que você deseja remover.

## Para copiar uma condição {#section-00617bcf2c274f428686b2ec7f2d1db8}

Você pode copiar uma condição de um local para outro local no mesmo arquivo ou pode copiar uma condição de um arquivo de configuração de conjunto de dados para outro.

1. Clique com o botão direito do mouse no nome da condição ou no número correspondente à condição que você deseja copiar e clique em **[!UICONTROL Copy]**.
1. Clique com o botão direito do mouse no nome ou no número da condição abaixo da qual deseja colocar a condição copiada e clique em **[!UICONTROL Paste]**.
