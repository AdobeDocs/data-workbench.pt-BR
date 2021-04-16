---
description: Se não quiser herdar um arquivo de configuração de um perfil interno ou de outro perfil herdado (ou seja, se quiser que as instruções no arquivo sejam ignoradas durante a construção do conjunto de dados), mas não quiser modificar o arquivo, crie um arquivo vazio (byte zero) com o mesmo nome e armazene o arquivo em outro perfil.
title: Ocultar arquivos de configuração do conjunto de dados
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
exl-id: 327847d1-421a-4ed1-9a5f-2491765a34bd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 2%

---

# Ocultar arquivos de configuração do conjunto de dados{#hiding-dataset-configuration-files}

Se não quiser herdar um arquivo de configuração de um perfil interno ou de outro perfil herdado (ou seja, se quiser que as instruções no arquivo sejam ignoradas durante a construção do conjunto de dados), mas não quiser modificar o arquivo, crie um arquivo vazio (byte zero) com o mesmo nome e armazene o arquivo em outro perfil.

**Para fazer byte zero em um arquivo de configuração de conjunto de dados**

1. No [!DNL Profile Manager], abra as pastas e subpastas necessárias para localizar o arquivo que deseja bytes zero.
1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo e clique em **[!UICONTROL Make Local]**.
1. Abra o arquivo local em um editor de texto, como o Bloco de notas, e exclua seu conteúdo.
1. Salve e feche o arquivo.
1. No [!DNL Profile Manager], salve o arquivo de bytes zero em um perfil à direita do perfil no qual o arquivo original reside. (O arquivo de bytes zero deve ter prioridade sobre o arquivo original.)

   No [!DNL Profile Manager], um hífen (-), em vez de uma marca de seleção, em uma coluna identifica o arquivo de bytes zero, como mostrado no exemplo abaixo.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Ao reprocessar seu conjunto de dados, o conjunto de dados não contém os componentes do conjunto de dados que o arquivo original define.

>[!NOTE]
>
>Se um arquivo de configuração de byte zero definir uma dimensão estendida usada em uma visualização ou definição de métrica, o Data Workbench produzirá um erro para essa visualização ou métrica, respectivamente.

Também é possível usar arquivos de bytes zero para mover uma métrica, dimensão ou filtro para outro local no perfil ou para ocultar itens de menu. Para obter informações, consulte o *Guia do Usuário do Data Workbench*.
