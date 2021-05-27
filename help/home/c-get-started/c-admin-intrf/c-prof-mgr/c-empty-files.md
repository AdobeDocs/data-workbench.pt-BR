---
description: Se você não tiver permissão para excluir arquivos de um perfil ou não quiser excluir um arquivo permanentemente, poderá usar arquivos vazios (byte zero) para ocultar arquivos.
title: Ocultar um arquivo esvaziando-o (byte zero)
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---

# Ocultar um arquivo esvaziando-o (byte zero){#hide-a-file-by-emptying-it-zero-byte}

Se você não tiver permissão para excluir arquivos de um perfil ou não quiser excluir um arquivo permanentemente, poderá usar arquivos vazios (byte zero) para ocultar arquivos.

No [!DNL Profile Manager], um hífen (-), em vez de uma marca de seleção, em uma coluna identifica um arquivo de byte zero.

![](assets/vis_ProfMgr_Zero-byte.png)

Ao contrário dos outros métodos de ocultação de arquivos (como [!DNL order.txt], o parâmetro Mostrar e o parâmetro Oculto ), o Data Workbench trata arquivos com bytes zero como inexistentes. Por exemplo, se você adicionar um byte zero a uma dimensão que foi usada em uma visualização ou definição de métrica, o Data Workbench produzirá um erro para essa visualização ou métrica, respectivamente.

Essa funcionalidade é útil por vários motivos, incluindo quando você deseja fazer o seguinte:

* **Faça uma Data Workbench de arquivo** inutilizável sem precisar das permissões de perfil necessárias para excluir o arquivo.
* **Mova uma métrica, dimensão ou** filtro para outro local sem precisar das permissões de perfil necessárias para excluir o arquivo do local original.
* **Ocultar itens de menu.** Por exemplo, o  [!DNL Base] perfil tem um  [!DNL Metric Legend] definido no  [!DNL Metric.vw] arquivo . Diga que sua empresa criou três legendas de métrica que você deseja exibir em um submenu Adicionar legenda > Métrica . É possível bytes zero no arquivo [!DNL Base] de perfil [!DNL Metric.vw] para que somente o novo submenu e três novas legendas de métricas sejam exibidos.

**Para ocultar um arquivo**

1. No [!DNL Profile Manager], abra as pastas e subpastas necessárias para localizar o arquivo que deseja bytes zero.
1. Clique com o botão direito do mouse na marca de seleção ao lado do nome do arquivo e clique em **[!UICONTROL Make Local]**.
1. Abra o arquivo local e exclua seu conteúdo.
1. Salve e feche o arquivo.
