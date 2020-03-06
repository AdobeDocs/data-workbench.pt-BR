---
description: Esta seção explica os diferentes tipos de Dimensões e como configurá-las no DWB.
title: Configuração de dimensão
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Configuração de dimensão{#dimension-setup}

Esta seção explica os diferentes tipos de Dimensões e como configurá-las no DWB.

## O que são dimensões {#section-dac631943df24706827cedc6f0641543}

No nível mais básico, as dimensões são categorias nas quais os dados no conjunto de dados podem ser divididos.

Prática recomendada: As dimensões no esquema de dados podem ser fornecidas com qualquer nome. Os nomes de dimensão usados e explicados neste curso são considerados uma prática recomendada. As dimensões podem ser nomeadas de forma diferente. À medida que você fica exposto a outros conjuntos de dados, você verá diferenças nos conjuntos de dados. É importante compreender o objetivo das dimensões em vez do seu nome. Por exemplo, seja chamado de &quot;Visitante&quot;, &quot;Cliente&quot;, &quot;Pessoa&quot;, &quot;Consumidor&quot; ou &quot;Usuário&quot;, é importante entender que esses termos são comumente usados para se referir à dimensão contável de mais alto nível que está sendo usada para coletar informações sobre uma pessoa singular.

Para obter informações completas, consulte o guia Configuração [do](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html) conjunto de dados.

## Tipos de dimensões no DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

Há dois tipos de dimensões no Análise de big data: Dimensões estendidas e dimensões derivadas.

Dimensões estendidas são criadas a partir de campos nos arquivos de dados &quot;brutos&quot;. Dimensões estendidas são usadas para categorizar dados &quot;brutos&quot; e especificar as relações que existem entre os dados. As dimensões estendidas são criadas pelos Arquitetos da Análise de big data.

As Dimensões Derivadas são criadas por um usuário &quot;no lado do cliente&quot; depois que o conjunto de dados é processado usando as definições de dimensão Estendida existentes. Por exemplo, com base na dimensão URI existente, um usuário pode optar por criar uma dimensão derivada de Nome da página, que exibe um nome de página mais amigável no lugar de um determinado URI. Todas as dimensões consistem em elementos ou itens que foram classificados (agrupados) juntos para formar a dimensão. Abaixo estão três dimensões e seus elementos.

Várias dimensões derivadas são criadas automaticamente para ativar tipos diferentes de visualizações. Por exemplo, quando um usuário cria um site ou mapa de processos, os servidores DWB criam uma dimensão Prefixo. Outras, como as dimensões de hora de relatório, são definidas por arquivos no diretório Dimensões de um perfil.

>[!NOTE]
>
>Os elementos que aparecem em qualquer dimensão específica refletirão apenas os valores que existem em registros que foram escolhidos para serem carregados no conjunto de dados. Por exemplo, se não houver dados para &quot;12 de maio&quot;, esse mês não aparecerá na dimensão &quot;Mês&quot;.

## Extended Dimensions {#section-5fc51fa539034941a30a2df606f7d727}

Tipos de dimensões estendidas

**1) Dimensões contáveis**

No nível mais alto estão dimensões contáveis. Dimensões contáveis servem duas funções principais. Primeiro, são dimensões cujos elementos você deseja contar. Em outras palavras, os contadores respondem a perguntas como:

* &quot;Quantos visitantes visitaram sua página inicial?&quot;
* &quot;Quantas visitas vieram do google.com?&quot;

Por essa razão, os contadores são frequentemente usados como o elemento básico fundamental para criar métricas.

A segunda grande função dos contadores é que eles formam a espinha dorsal da estrutura do esquema do conjunto de dados. Seu esquema de dados e todas as outras dimensões estão organizados para serem agrupados e pertencerem a um contável. Em outras palavras, se considerarmos dimensões como &quot;categorias&quot;, então os contáveis são a forma como organizamos essas &quot;categorias&quot; em grupos.

Quando as dimensões são agrupadas em uma dimensão contável, elas devem estar no &quot;nível&quot; da dimensão contável. Por exemplo, o &#39;Endereço de email&#39; pode estar no nível do Visitante e o &quot;Navegador&quot; está no nível da Visita. &quot;Pai&quot; e &quot;filho&quot; referem-se à relação entre o contável e as dimensões agrupadas abaixo dele. Por exemplo, Visitante é um &quot;pai&quot; do endereço de email. Por outro lado, o endereço de email é um &quot;filho&quot; do Visitante.

**2) Dimensões simples**

As dimensões mais comuns são dimensões simples. Dimensões simples têm uma relação um para muitos com uma dimensão pai contável e são comumente usadas em visualizações para que você possa visualizar seus elementos. Isso significa que uma dimensão contável pode ter um valor para uma dimensão simples, mas a dimensão simples pode pertencer a um ou mais contáveis. Por exemplo, um cliente tem o nome &quot;John&quot; - esse cliente só pode ter um nome, no entanto, muitos outros clientes podem ter o nome &quot;John;. Como outro exemplo, somente um navegador (por exemplo, Firefox) pode ser usado para qualquer visita específica a um site, mas esse navegador pode ser usado para muitas visitas diferentes.

Se dimensões contáveis responderem &quot;Quantas?&quot;, então dimensões simples responderão &quot;Quais?&quot;. Usando o mesmo exemplo acima usado na seção de dimensão contável; Nome da página é a dimensão simples. Usando a tabela e a dimensão simples, Nome da página, podemos responder perguntas como:

* &quot;Qual página tinha mais visualizações de página?&quot;
* &quot;De todas as páginas do Carrinho de Compras, qual delas tinha mais visitas?&quot;

**3) Dimensões muitas para muitas**

As dimensões muitas para muitas têm uma relação muitas para muitas com uma dimensão pai contável. Por exemplo, se uma dimensão chamada Termo de pesquisa externa estiver no nível de Visita; um determinado Termo de pesquisa externa pode ser usado em uma ou várias Visitas, e uma determinada Visita pode incluir um ou vários Termos de pesquisa externa. Assim, o Termo de pesquisa externa é uma dimensão muitas para muitas.

**4) Dimensões numéricas**

Dimensões numéricas são um tipo de dimensão simples que tem um valor numérico. Geralmente, dimensões numéricas são criadas para serem usadas em métricas. Exemplos de dimensões numéricas incluem &quot;Receita&quot;, &quot;Pedidos&quot; e &quot;Unidades&quot;. No exemplo acima, &quot;Pedidos do cliente&quot; é uma dimensão numérica.
**5) Dimensões** desnormalizadas Dimensões desnormalizadas são dimensões que têm uma relação um para um com uma dimensão pai contável. As dimensões denormal são frequentemente usadas com dimensões com alta cardinalidade (muitos elementos únicos), como dados de identificação. Por exemplo, um visitante só pode ter uma ID de usuário e uma ID de usuário só pode pertencer a um visitante. Portanto, essa é uma relação um para um e pode ser uma dimensão desnormalizada.

Por exemplo, a ID de usuário da Web Geometrixx é uma dimensão desnormalizada no nível do cliente. Como é desnormalizada, ele tem uma relação um para um com sua dimensão pai, o que significa que cada ID de usuário da Web tem um cliente e cada cliente tem apenas uma ID de usuário da Web. Assim, a métrica &quot;Clientes&quot; só pode ser &quot;1&quot; para cada elemento da ID de usuário da Web Geometrixx.

**6) Dimensões de tempo**

As dimensões de tempo permitem criar um conjunto de dimensões de hora local periódicas ou absolutas com base no campo de carimbo de data e hora especificado. Exemplos de dimensões de tempo incluem &quot;Dia&quot;, &quot;Hora&quot;, &quot;Semana&quot; e &quot;Hora do dia&quot;. No exemplo acima, a tabela &quot;Hora do dia&quot; mostra quantas visitas e exibições de página foram recebidas durante as diferentes horas dos dias.

>[!NOTE]
>
>O % de escape usado para a formatação de exibição é igual ao *tempo de execução* padrão da biblioteca C.

## Definindo Dimensões Estendidas {#section-38ee124ec74b43fb95f13194a9582b97}

Etapas para definir Dimensão estendida:

1. Ao trabalhar em seu perfil de conjunto de dados, abra o Gerenciador de perfis e clique em Conjunto de dados para mostrar seu conteúdo.
1. Abra o arquivo Transformation.cfg ou o arquivo Transformation Dataset Include no qual você deseja definir a dimensão estendida.
1. Clique com o botão direito do mouse em Transformações e clique em Adicionar novo > `<Extended dimension type>`.
1. Insira as informações apropriadas para sua dimensão estendida. Para obter descrições dos tipos de transformação e informações sobre seus parâmetros, consulte as seguintes seções:

   * [Dimensões contáveis](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Dimensões simples](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Dimensões de muitos para muitos](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Dimensões numéricas](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Dimensões desnormalizadas](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Dimensões de tempo](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. Para qualquer dimensão estendida que você definir, é possível adicionar uma ou mais linhas de comentário ao parâmetro Comentários para descrever a dimensão ou adicionar observações sobre seu uso. Para adicionar um comentário, clique com o botão direito do mouse no rótulo *Comentários* e clique em* Adicionar novo > Linha de comentário*.

1. Depois de definir suas dimensões estendidas no arquivo de configuração, salve o arquivo localmente e salve-o no perfil do conjunto de dados no servidor DWB.

## Ocultar dimensões estendidas {#section-02339fb51658418eabc10186cd5957d7}

Dimensões estendidas podem ser ocultadas para que não sejam exibidas no Menu de dimensões no DWB. Para ocultar a dimensão, defina a propriedade Oculto como &quot;Verdadeiro&quot; na definição da dimensão.
