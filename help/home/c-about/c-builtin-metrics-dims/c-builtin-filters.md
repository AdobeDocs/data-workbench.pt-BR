---
description: Os filtros de perfil restringem o escopo dos dados disponíveis em um conjunto de dados.
title: Filtros de perfil embutidos
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
exl-id: bb167487-415d-44a8-9a0a-9a76d90ba5c0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# Filtros de perfil embutidos{#built-in-profile-filters}

Os filtros de perfil restringem o escopo dos dados disponíveis em um conjunto de dados.

Além do processamento de log e dos filtros de transformação que podem ser aplicados antes ou durante a criação de um conjunto de dados, outros filtros de perfil estão disponíveis e afetam o escopo dos dados disponíveis para seleção em um conjunto de dados. Esta seção descreve somente o último tipo de filtro especial.

Os seguintes filtros de perfil estão disponíveis para o usuário depois que um conjunto de dados é criado:

* Filtro de Subconjunto de Dados
* Filtro de Sessão Quebrada

>[!NOTE]
>
>Filtros adicionais podem ser criados e aplicados por meio de sua presença no diretório Filters de um perfil.

## Subconjunto de dados {#section-0defb44315d94254ab6e629ec3d6f420}

Um subconjunto de dados atua como um filtro de dados, permitindo selecionar apenas os elementos de dimensão dos dados que são de seu interesse.

A criação de subconjuntos de dados reduz a quantidade de tempo necessária para calcular respostas exatas para suas consultas. Se o subconjunto de dados especificado for pequeno o suficiente, o Data Workbench poderá recuperar todos os dados necessários do servidor Insight e responder perguntas sobre o subconjunto de forma rápida e precisa. Isso é especialmente útil se você sabe que, por exemplo, analisar um dia de dados ou sessões de um referenciador específico exigirá várias horas.

Os usuários podem criar eles mesmos subconjuntos de dados ou acessar subconjuntos de dados definidos em um perfil herdado ou de trabalho. Quando um usuário cria um subconjunto do conjunto de dados (selecionando os dados desejados no Insight e clicando com o botão direito do mouse no espaço de trabalho e clicando em Dados > Subconjunto), um arquivo Subconjunto.filter de dados é criado na pasta Filtros no diretório do perfil do usuário. Esse filtro define o subconjunto de dados selecionado e salva o subconjunto para uso futuro.

>[!NOTE]
>
>É possível criar vários subconjuntos de dados e alterá-los para exibir partes diferentes dos dados. Lembre-se de desativar o Subconjunto de dados quando quiser exibir todos os dados. Caso contrário, seus valores de métrica não serão representativos de todos os dados no conjunto de dados.

## Filtro de Sessão Interrompido {#section-1608e97da6464b11aea27cbb7f3160e4}

O Filtro de sessão quebrada é uma fórmula de métrica que pode ser facilmente modificada para atender a quaisquer requisitos de filtragem. Nos perfis padrão do Site, o Filtro de Sessão Quebrada é configurado para incluir todos os visitantes que têm um Sinalizador Visitado definido como 1. O valor 1 indica a presença de um cookie de rastreamento para esse visitante.

A seguir está o texto do arquivo filtro Sessão quebrada padrão fornecido pelo Adobe no pacote de lançamento para os perfis do Site.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

Por padrão, os espaços de trabalho têm o filtro Sessão quebrada aplicado à sua seleção e aos seus benchmarks, e ele pode ser alternado clicando com o botão direito do mouse no espaço de trabalho e clicando em Dados > Filtro de sessão quebrada.

O Filtro de Sessão Quebrada pode ser referenciado em expressões de filtro como Broken_Session_Filter, mesmo se não estiver habilitado para o espaço de trabalho atual. Consulte [expressões de filtro](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) para obter mais informações.
