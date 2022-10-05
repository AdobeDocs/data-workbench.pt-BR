---
description: A barra lateral fornece acesso a funções usadas regularmente e preserva as visualizações à medida que você se move entre espaços de trabalho.
title: Configurar a barra lateral
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 2%

---

# Configurar a barra lateral{#configure-the-sidebar}

{{eol}}

A barra lateral fornece acesso a funções usadas regularmente e preserva as visualizações à medida que você se move entre espaços de trabalho.

Os administradores podem personalizar uma barra lateral para torná-la apropriada para grupos de usuários diferentes e, em seguida, implantar a barra lateral com um perfil.

A barra lateral é ideal para ajudá-lo a rastrear os filtros e as substituições locais. Se preferir não usar a barra lateral, você pode ocultá-la.

## Adicionar visualizações à barra lateral {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Inicie o Data Workbench.
1. Na barra lateral, clique em **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. Por exemplo, [!DNL Selections Panel], [!DNL Filters Panel] ou [!DNL Table].

   Os seguintes painéis da barra lateral estão disponíveis na instalação padrão do Data Workbench. Mais itens podem estar disponíveis no seu perfil específico:

   * **Painel de seleções:** Permite compreender quais seleções estão ativas no espaço de trabalho atual. O [!DNL Selections Panel] é atualizado sempre que você faz uma nova seleção. Você pode apagar as seleções clicando em **[!UICONTROL x]**. Consulte [Fazer seleções em visualizações](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) para obter informações sobre como selecionar dados.
   * **Painel Filtros:** Facilita o carregamento e a aplicação de filtros salvos. Você pode carregar vários filtros e ativá-los ou desativá-los independentemente clicando na caixa de seleção ao lado dele. Consulte [Editores de filtro](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **Painel de substituição local:** Esse painel exibe quais métricas, dimensões e filtros presentes no perfil foram modificados em sua cópia pessoal do perfil. Isso ajuda a alertá-lo sobre possíveis diferenças entre a maneira como os dados aparecem no cliente e a de outros usuários. Ao salvar as alterações em uma métrica, dimensão ou filtro no servidor, a substituição é removida do [!DNL Local Overrides panel]. Se você clicar em uma substituição e, em seguida, clicar em **[!UICONTROL Revert to Server]**, a substituição local é removida e o item é revertido para a versão compartilhada.
   * **Legenda da métrica:** Adiciona uma legenda de métrica. [!DNL Metric legends] permite visualizar métricas de linha de base relacionadas ao seu perfil e estatísticas relacionadas ao conjunto de dados (ou à seleção atual, se houver). Consulte [Legendas de métricas](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **Legenda de cores:** Adiciona uma legenda de cores. É possível colorir visualizações de código por métricas, como Conversão e Retenção, e usá-las em quase todos [!DNL Workspace]. Vincular as métricas comerciais à cor facilita a detecção de anomalias, exceções e tendências. Consulte [Legendas de cores](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).
   * **Anotação de texto:** Adiciona um painel de notas. [!DNL Text annotations] são janelas nas quais você pode inserir texto arbitrário para adicionar informações descritivas ou comentários a um [!DNL Workspace]. Consulte [Trabalhar com anotações de texto](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **Tabela:** Adiciona uma tabela. Uma tabela pode exibir uma ou mais métricas em uma ou mais dimensões de dados. Consulte [Tabelas](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **Abrir:** Abre um arquivo salvo.

## Abrir um painel da barra lateral {#section-cbc8e57491854274a577d47a48c306b8}

Você pode abrir um arquivo de visualização da barra lateral de um local salvo ou da área de transferência.

1. Na barra lateral, clique em **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. Clique em **[!UICONTROL File]** para localizar o [!DNL .vw] do painel que deseja adicionar ou clique em **[!UICONTROL Last Closed Window]**, que extrai a visualização da área de transferência.

   Além disso, você pode clicar em **[!UICONTROL From Clipboard]** para colar uma visualização que foi copiada para a área de transferência. Consulte [Copiando um painel da barra lateral](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1).

## Copiando um painel da barra lateral {#section-720ae057632a4b8dbb94412e06a370b1}

1. Clique com o botão direito do mouse na borda superior do painel e clique em **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. Para colar o painel, clique em **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Salvar um painel da barra lateral {#section-fb19936b12704fb0a4c592abb579db1d}

Em um painel da barra lateral, clique com o botão direito do mouse na barra de título e clique em **[!UICONTROL Save]**.

Da mesma forma, é possível abrir uma visualização da barra lateral salva. A Data Workbench salva a visualização como uma [!DNL .vw] no local especificado.

## Reverter para a barra lateral padrão {#section-4d14b8771ad747bba799876267f24831}

Na barra lateral, clique em **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

Ao fechar o Data Workbench, o sistema salva a configuração atual da barra lateral no [!DNL sidebar.vw] no perfil do usuário. Quando você abre o Data Workbench, o sistema carrega o [!DNL sidebar.vw] do perfil do usuário, em vez de um perfil principal.

Você pode reverter para uma barra lateral padrão ou salva anteriormente, o que exclui a barra lateral do perfil do usuário e recarrega a barra lateral do perfil principal. Os administradores podem substituir a barra lateral padrão (principal) por uma barra lateral local fazendo o upload da barra lateral [!DNL Profile Manager].

## Personalizar o arquivo do painel Mais status {#section-8d502f3b59cc4331966edec05e896ce1}

Os administradores do sistema podem criar fórmulas na [!DNL More Status Panel.vw]. Isso coloca palavras contextuais em torno de valores de métrica e dimensão, e exibe os resultados na variável [!DNL More Status panel] na barra lateral.

Para exibir o [!DNL More Status panel] na barra lateral, clique nas setas mostradas no exemplo a seguir.

![](assets/more_status_panel_arrows.png)

O procedimento a seguir mostra um exemplo simples de como criar um status personalizado que informa quantos dias há em um conjunto de dados:

1. Na [!DNL Profile Manager], clique em **[!UICONTROL Sidebar\]**.

1. No [!DNL Base_5_3*] , faça uma cópia local da [!DNL More Status Panel.vw] arquivo.

   Para fazer isso, clique com o botão direito do mouse na marca de seleção de arquivo e clique em **[!UICONTROL Make Local]**.

1. Abra o [!DNL More Status Panel.vw] no [!DNL .vw] [!DNL Editor] ou no Bloco de notas.

   ![](assets/more_status_panel_file.png)

1. Complete o [!DNL Context] e [!DNL Items] nos campos [!DNL Editor]. Consulte [Sintaxe do idioma da consulta](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) para obter diretrizes sobre sintaxe.

1. Salve o arquivo.

   Os valores no exemplo anterior resultam em uma fórmula de status exibida da seguinte maneira:

   ![](assets/more_status_panel.png)
