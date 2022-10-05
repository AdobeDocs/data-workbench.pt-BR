---
description: Esta seção explica o script Saint Scrubber.
title: Script para o depurador SAINT
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
exl-id: 5f6d92b1-baaa-4d67-a1c2-ce7d51affb17
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 1%

---

# Script para o depurador SAINT{#scripting-for-the-saint-scrubber}

{{eol}}

Esta seção explica o script Saint Scrubber.

## Visão geral da classificação de SAINT {#section-b840a99f10684bb4b58e844a515d0d79}

A classificação também é conhecida pela sigla SAINT para a ferramenta SiteCatalyst Attribute Importing and Naming Tool.

Ao &quot;classificar&quot; uma variável de SiteCatalyst, você está estabelecendo uma relação entre uma variável e metadados relacionados a essa variável. As classificações são usadas com mais frequência na área Campanhas, portanto, usarei isso como uma maneira de explicá-las. A maioria dos clientes envia tráfego de campanha para o site usando um código de rastreamento. Esse código de rastreamento é um identificador que pode representar uma palavra-chave específica adquirida no Google, como &quot;goog123&quot;. Esse identificador é passado para a variável s.campaign, para que você possa ver quais eventos de sucesso de site ocorrem depois que os visitantes chegam ao site a partir desse código de campanha.

Mas e se, em vez de visualizar Campanhas apenas pelo código de rastreamento, você quiser ver os resultados da campanha pelo Mecanismo de pesquisa ou Palavra-chave ou Canal de campanha? Você precisa criar uma nova variável de conversão para o Mecanismo de pesquisa, outra para Palavra-chave e outra para o Canal da campanha? Em caso afirmativo, você usaria muitas de suas cinquenta variáveis somente em Campanhas! Felizmente, você pode usar Classificações para facilitar a vida! Como cada código de rastreamento pode ter um Mecanismo de pesquisa, Palavra-chave ou Canal de campanha, você pode simplesmente criar três Classificações da variável de Campanhas para representar cada uma. Basicamente, você diz ao SiteCatalyst que há uma relação direta entre a variável Campaigns e esses três outros valores de &quot;meta dados&quot;. Ao fazer isso, o SiteCatalyst permitirá que você divida e divida os Eventos de sucesso do site por todas as quatro variáveis, sem marcação adicional.

## Script do depurador de SAINT no DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Esse script é usado ao trazer quaisquer dados de Classificação de SAINT para DWB. O script *SaintScrubber.dat* é normalmente colocada sob a *\Scripts\Scripository* na FSU.

A principal finalidade desse script é remover o cabeçalho na `<discoiqbr>` Arquivos de classificação SAINT. Além disso, conta o número se a coluna mencionada na linha de cabeçalho da coluna e verifica todas as linhas de dados. Se houver linhas com menos ou mais colunas, elas serão removidas do arquivo.

O *SaintScrubber.dat* internamente chama o script *saint_movibber.pl *. Abaixo estão os detalhes deste arquivo de script:

Caminho: *E:\Scripts\Scripository\Library\Perl*

Argumentos de script:

1. Pasta de Entrada (Obrigatório): diretório_de_origem
1. Pasta de Saída (Obrigatório) : diretório_de_destino
1. Delimitador (Obrigatório) : delimiter
1. Rejeitar pasta (Opcional) (O parâmetro pode ser deixado em branco ou omitido da linha de comando)
1. Pasta de registro (Opcional)(O parâmetro pode ser deixado em branco ou omitido da linha de comando)

Etapas executadas no script Perl:

1. Substitua feeds de formulário escaped, novas linhas, retornos de carro, guias com espaços.
1. Remova os bytes duplos que são interpretados como um caractere de controle na BMP UTF-8 (Plano Multilingual Básico) exceto para:

   * 9 tabulação horizontal
   * Alimentação de 10 linhas
   * 12 feed de formulário
   * 13 retorno de carro
   * Use a palavra-chave pipe, como delimitador para | p. ex.: pipe delimiter
   * Remover outros caracteres problemáticos
   * Depois da movimentação acima, solte quaisquer linhas com um número de colunas diferente da primeira linha de dados (não em branco ou comentário)
   * Oferece suporte a arquivos de rejeição opcionais para manter linhas rejeitadas em vez de apenas ignorá-las
   * Suporte a pasta de entrada recursiva; gerar pastas de saída da mesma estrutura
   * Mova arquivos de entrada processados para subpastas processadas para que o script não repita o esforço quando executado novamente na mesma pasta de entrada existente
   * Reconhecer data em nomes de arquivo do workbench; classificar o processamento primeiro por data e depois alfa — independentemente do nome da pasta. Isso garantirá que a sequência esteja correta, independentemente do tipo de arquivo do workbench (ecom, não ecom) ou da ID de conjunto de relatórios (se você estiver processando vários conjuntos de relatórios em um único conjunto de dados do Insight).
   * Enviar alertas de email `<discoiqbr>`
