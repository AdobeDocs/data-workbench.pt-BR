---
description: Se você não tiver permissão para excluir arquivos de um perfil ou não quiser excluir um arquivo permanentemente, poderá usar arquivos vazios (de byte zero) para ocultar arquivos.
solution: Analytics
title: Ocultar um arquivo esvaziando-o (byte zero)
topic: Data workbench
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ocultar um arquivo esvaziando-o (byte zero){#hide-a-file-by-emptying-it-zero-byte}

Se você não tiver permissão para excluir arquivos de um perfil ou não quiser excluir um arquivo permanentemente, poderá usar arquivos vazios (de byte zero) para ocultar arquivos.

No [!DNL Profile Manager], um hífen (-), em vez de uma marca de seleção, em uma coluna identifica um arquivo de byte zero.

![](assets/vis_ProfMgr_Zero-byte.png)

Ao contrário dos outros métodos de ocultação de arquivos (como [!DNL order.txt]o parâmetro Mostrar e o parâmetro Oculto), o Análise de big data trata os arquivos de byte zero como inexistentes. Por exemplo, se você adicionar um byte zero a uma dimensão que tenha sido usada em uma visualização ou definição de métrica, o Análise de big data produzirá um erro para essa visualização ou métrica, respectivamente.

Essa funcionalidade é útil por vários motivos, inclusive quando você deseja fazer o seguinte:

* **Torne um arquivo inutilizável** no Análise de big data sem precisar das permissões de perfil necessárias para excluir o arquivo.
* **Mova uma métrica, dimensão ou filtro** para outro local sem precisar das permissões de perfil necessárias para excluir o arquivo do local original.
* **Ocultar itens de menu.** Por exemplo, o [!DNL Base] perfil tem um [!DNL Metric Legend] definido no [!DNL Metric.vw] arquivo. Diga que sua empresa criou três legendas de métricas que você deseja exibir em um submenu Adicionar legenda > Métrica. É possível fazer um byte zero no arquivo de [!DNL Base] perfil [!DNL Metric.vw] para que somente o novo submenu e três novas legendas de métricas sejam exibidos.

**Para ocultar um arquivo**

1. No [!DNL Profile Manager], abra as pastas e subpastas necessárias para localizar o arquivo que você deseja que seja de byte zero.
1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo e clique em **[!UICONTROL Make Local]**.
1. Abra o arquivo local e exclua seu conteúdo.
1. Salve e feche o arquivo.

