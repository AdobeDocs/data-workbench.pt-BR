---
description: Esta seção explica o script Saint Scrubber.
title: Script para o depurador SAINT
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Script para o depurador SAINT{#scripting-for-the-saint-scrubber}

Esta seção explica o script Saint Scrubber.

## Visão geral da classificação SAINT {#section-b840a99f10684bb4b58e844a515d0d79}

A classificação também é conhecida pelo acrônimo SAINT para a ferramenta SiteCatalyst Attribute Importing and Naming Tool.

Ao &quot;classificar&quot; uma variável do SiteCatalyst, você está estabelecendo uma relação entre uma variável e metadados relacionados a essa variável. As classificações são usadas com mais frequência na área Campanhas, então usarei isso como uma forma de explicá-las. A maioria dos clientes envia tráfego de campanha para o site usando um código de rastreamento. Este código de rastreamento é um identificador que pode representar uma palavra-chave específica adquirida no Google, como &quot;goog123&quot;. Esse identificador é passado para a variável s.campaign para que você possa ver quais eventos de sucesso de site ocorrem depois que os visitantes chegam ao site a partir desse código de campanha.

Mas e se, em vez de visualizar Campanhas apenas pelo código de rastreamento, você quiser ver os resultados da campanha pelo Mecanismo de pesquisa ou Palavra-chave ou Canal de campanha? Você precisa criar uma nova variável de conversão para o Search Engine, outra para Palavra-chave e outra para o Campaign Channel? Em caso afirmativo, você usaria muitas de suas cinquenta variáveis somente em Campanhas! Felizmente, você pode usar Classificações para facilitar sua vida! Como cada código de rastreamento pode ter um Mecanismo de pesquisa, uma Palavra-chave ou um Canal de campanha, basta criar três Classificações da variável Campanhas para representá-las. Basicamente, você está dizendo ao SiteCatalyst que há uma relação direta entre a variável Campanhas e esses três outros valores &quot;meta-dados&quot;. Ao fazer isso, o SiteCatalyst permitirá que você divida e registre os Eventos de sucesso do site por todas as quatro variáveis sem nenhuma marcação adicional.

## Script do depurador SAINT no DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Esse script é usado quando você traz qualquer dado de classificação SAINT para o DWB. O script *SaintScrubber.dat* normalmente é colocado sob a pasta *\Scripts\Scripository* no FSU.

A principal finalidade desse script é remover o cabeçalho nos arquivos de classificação `<discoiqbr>` SAINT. Além disso, conta o número se a coluna mencionada na linha de cabeçalho da coluna e verifica todas as linhas de dados. Se houver linhas com menos ou mais colunas, elas serão removidas do arquivo.

O *SaintScrubber.dat* chama internamente o script *saint_scrubber.pl *. Abaixo estão os detalhes deste arquivo de script:

Caminho: *E:\Scripts\Scripository\Library\Perl*

Argumentos de script:

1. Pasta de Entrada (Obrigatória): source_diretory
1. Pasta de saída (obrigatório): diretório_de_destino
1. Delimitador (obrigatório): delimitador
1. Rejeitar pasta (opcional)(o parâmetro pode ser deixado em branco ou omitido da linha de comando)
1. Pasta de registro (opcional)(o parâmetro pode ser deixado em branco ou omitido da linha de comando)

Etapas executadas no script Perl:

1. Substitua feeds de formulário escapados, novas linhas, retornos de carro, guias com espaços.
1. Remova os bytes duplos que são interpretados como um caractere de controle no UTF-8 BMP (Basic Multilingual Plane), exceto:

   * 9 guia horizontal
   * Alimentação de 10 linhas
   * 12 feed de formulário
   * 13 retorno de carro
   * Use a palavra-chave pipe, como delimitador para| por exemplo: barra
   * Remover outros caracteres problemáticos
   * Após a depuração acima, solte quaisquer linhas com um número de colunas diferente da primeira linha de dados (não em branco ou comentário)
   * Suportar arquivos de rejeição opcionais para manter linhas rejeitadas em vez de simplesmente ignorá-las
   * Suportar pasta de entrada recursiva; gerar pastas de saída da mesma estrutura
   * Mover arquivos de entrada processados para subpastas processadas para que o script não repita o esforço quando executado novamente na mesma pasta de entrada existente
   * Reconhecer data em nomes de arquivo do workbench; classifique o processamento primeiro por data e depois por alfa — independentemente do nome da pasta. Isso garantirá que a sequência esteja correta, independentemente do tipo de arquivo do workbench (ecom, non-ecom) ou da ID do conjunto de relatórios (se você estiver processando vários conjuntos de relatórios em um único conjunto de dados do Insight).
   * Alertas por email de suporte `<discoiqbr>`

