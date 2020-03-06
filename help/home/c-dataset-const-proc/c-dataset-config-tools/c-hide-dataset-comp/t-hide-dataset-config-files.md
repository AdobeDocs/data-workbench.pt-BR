---
description: Se você não quiser herdar um arquivo de configuração de um perfil interno ou herdado (ou seja, se quiser que as instruções no arquivo sejam ignoradas durante a construção do conjunto de dados), mas não quiser modificar o arquivo, crie um arquivo vazio (byte zero) com o mesmo nome e armazene o arquivo em outro perfil.
solution: Analytics
title: Ocultar Arquivos de Configuração de Conjunto de Dados
topic: Data workbench
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ocultar Arquivos de Configuração de Conjunto de Dados{#hiding-dataset-configuration-files}

Se você não quiser herdar um arquivo de configuração de um perfil interno ou herdado (ou seja, se quiser que as instruções no arquivo sejam ignoradas durante a construção do conjunto de dados), mas não quiser modificar o arquivo, crie um arquivo vazio (byte zero) com o mesmo nome e armazene o arquivo em outro perfil.

**Para um arquivo de configuração de conjunto de dados de byte zero**

1. No [!DNL Profile Manager], abra as pastas e subpastas necessárias para localizar o arquivo que você deseja que seja de byte zero.
1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo e clique em **[!UICONTROL Make Local]**.
1. Abra o arquivo local em um editor de texto, como o Bloco de notas, e exclua seu conteúdo.
1. Salve e feche o arquivo.
1. No arquivo [!DNL Profile Manager], salve o arquivo de zero byte em um perfil à direita do perfil no qual o arquivo original reside. (Você deseja que o arquivo de 0 byte tenha prioridade sobre o arquivo original.)

   No [!DNL Profile Manager], um hífen (-), em vez de uma marca de seleção, em uma coluna identifica o arquivo de byte zero como mostrado no exemplo abaixo.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Quando você reprocessa seu conjunto de dados, o conjunto de dados não contém os componentes do conjunto de dados que o arquivo original define.

>[!NOTE]
>
>Se um arquivo de configuração de byte zero definir uma dimensão estendida que é usada em uma visualização ou definição de métrica, a análise de big data produzirá um erro para essa visualização ou métrica, respectivamente.

Você também pode usar arquivos de byte zero para mover uma métrica, dimensão ou filtro para outro local no perfil ou para ocultar itens de menu. For information, see the *Data Workbench User Guide*.
