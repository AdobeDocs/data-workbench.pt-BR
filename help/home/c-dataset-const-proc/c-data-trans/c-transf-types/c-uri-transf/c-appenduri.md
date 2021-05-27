---
description: A transformação AppendURI fornece uma maneira de adicionar informações ao valor padrão que vem das entradas de log usadas para criar o conjunto de dados.
title: AppendURI
uuid: 8334d4f9-2bf6-4bd0-af65-8f2b0959652d
exl-id: 0d5901c0-bd13-4499-8e26-44839aeb7413
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 1%

---

# AppendURI{#appenduri}

A transformação AppendURI fornece uma maneira de adicionar informações ao valor padrão que vem das entradas de log usadas para criar o conjunto de dados.

A transformação coloca um par nome-valor no final do campo interno usado para criar a dimensão URI. O par nome-valor é criado usando o parâmetro Chave da string de consulta como o nome e o valor do parâmetro de entrada identificado como o valor do par. O comando [!DNL AppendURI] adiciona qualquer e os &amp; símbolos necessários para separar os pares nome-valor do tronco [!DNL URI] e de qualquer operação [!DNL AppendURI] anterior que possa ter sido aplicada ao URI.

A transformação [!DNL AppendURI] funciona somente quando definido no arquivo [!DNL Transformation.cfg] ou [!DNL Transformation Dataset Include].

| Parâmetro | Descrição | Padrão |
|---|---|---|
| Nome | Nome descritivo da transformação. Você pode inserir qualquer nome aqui. |  |
| Comentários | Opcional. Observações sobre a transformação. |  |
| Condição | Condições de aplicação desta transformação. |  |
| Padrão | O valor padrão a ser usado se a condição for atendida e o valor de entrada não estiver disponível. |  |
| Entrada | O nome do campo cujo valor é anexado ao URI. |  |
| Chave da string de consulta | O nome a ser usado na criação do par de nome-valor que está sendo anexado. |  |

Considere um site que foi construído usando uma abordagem tradicional de Controlador de exibição de modelo. Nesses sistemas, é comum ter uma única página da web como ponto de acesso ao sistema. Para esse site, as visualizações dos padrões de tráfego no sistema seriam muito desinteressantes e não forneceriam insights sobre a utilização e o fluxo de tráfego do visitante. Por exemplo, considere um site que funis todas as solicitações da Web por meio de um URI do seguinte formulário:

* [!DNL http://www.examplesite.com/modelview.asp?id=login&name=bob]

A página ASP de visualização de modelo recebe todo o tráfego e determina suas ações com base no valor do campo de id na consulta. Por padrão, a dimensão URI conteria uma única entrada:

* [!DNL modelview.asp]

Isso resultaria em um mapeamento bastante desinteressante do tráfego pelo site, já que todo o tráfego está sendo canalizado por meio de um único URI. Para lidar com esse cenário específico e fornecer uma visualização mais informativa sobre a arquitetura subjacente do site, [!DNL AppendURI] pode ser usado para mover alguns dos pares de nome-valor exclusivos do campo de consulta cs-uri para a dimensão URI usada para visualizações. A transformação mostrada abaixo fornece os detalhes dessa transformação:

![](assets/cfg_TransformationType_AppendURI.png)

Neste exemplo, há duas páginas usadas pelo sistema para lidar com todas as solicitações: [!DNL modelview.asp] e [!DNL xmlmodelview.asp]. Uma página é usada para o tráfego do navegador e a outra é usada para comunicações XML sistema a sistema. O processo do servidor de aplicativos usa o nome da id da consulta cs-uri para determinar qual ação tomar. Portanto, você pode extrair o valor do campo de id e anexá-lo ao URI. O resultado é uma coleção de URIs com um intervalo de variação que reflete o tráfego do visitante no site. Aqui, uma condição [!DNL String Match] determina as entradas de log às quais a transformação é aplicada, pesquisando o campo cs-uri-stem para as duas páginas da Web de interesse e ignorando todas as outras. A entrada (o valor do nosso par nome-valor) é o resultado de cs-uri-query(id), que é &quot;login&quot;. Conforme especificado pelo parâmetro Chave da string de consulta, o nome que está sendo anexado é &quot;id&quot;. Assim, para o valor cs-uri de entrada do nosso exemplo, o URI resultante usado pela dimensão [!DNL URI] é [!DNL /modelview.asp&id=login].
