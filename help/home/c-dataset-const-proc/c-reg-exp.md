---
description: Expressões regulares são usadas em todos os campos de pesquisa do Data Workbench, incluindo os painéis de entidades de consulta.
title: Expressões regulares
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
exl-id: 75841a70-e78a-429b-b00d-ac107b7a87aa
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 2%

---

# Expressões regulares{#regular-expressions}

Expressões regulares são usadas em todos os campos de pesquisa do Data Workbench, incluindo os painéis de entidades de consulta.

* [Sobre expressões regulares](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologia de expressão regular](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [Sobre a correspondência literal](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Uso de metacaracteres](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Extração de padrão](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## Sobre expressões regulares {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Uma expressão regular é um padrão de texto, que consiste em uma combinação de caracteres alfanuméricos e caracteres especiais conhecidos como metacaracteres, que localiza padrões e extrai subsequências de texto. Expressões regulares são amplamente usadas na programação de computadores e fazem parte de línguas como o Perl.

Para identificar e extrair padrões complexos de string, o servidor do Data Workbench usa expressões regulares em algumas transformações e condições. O que segue é um breve guia para expressões regulares.

Este apêndice não é uma introdução abrangente a expressões regulares. Uma referência particularmente boa é a publicação O&#39;Reilly *Mastering Regular Expression, 2ª Edição* de Jeffrey E. F. Friedl.

## Terminologia de expressão regular {#section-80b0d54f731e448391532ab3eb3c525c}

| Termo | Definição |
|---|---|
| Literal | Um literal é um caractere usado em uma expressão regular para localizar uma sequência específica de caracteres. Por exemplo, para localizar o produto em [!DNL shop/products.html], o produto da string é um literal ou o que estamos literalmente procurando na string. |
| Metacaractere | Um metacaracter é um caractere especial que tem uma interpretação exclusiva no contexto de expressões regulares. Por exemplo, o ponto (.) é um metacaractere usado para corresponder a qualquer caractere. |
| Sequência de escape | Uma sequência de escape é simplesmente uma maneira de dizer ao mecanismo de expressão regular que gostaríamos de usar um dos metacaracteres como um literal. As sequências de escape sempre começam com o caractere de barra invertida (`\`). Ao colocar a barra invertida (que também é um metacaractere) na frente de um metacaractere, o mecanismo de expressão regular interpreta o metacaractere escapado como um literal. Por exemplo, se você deseja corresponder ao período de metacaracter (`.`), é necessário usar uma sequência de escape. No entanto, para corresponder a um dos pontos na string 168.196.0.11, você pode usar a expressão regular que consiste em uma barra invertida e um ponto (`\.`). |
| Padrão | Essa é a terminologia abreviada da expressão regular. Em essência, uma expressão regular é um padrão que você está tentando corresponder em relação à string de destino. |
| String de destino | Esse termo se refere à string na qual estamos pesquisando para localizar o padrão desejado. |

## Sobre a correspondência literal {#section-ec4497e3160c47ba9b828d939761b3e0}

A correspondência literal usa uma string literal sem qualquer caractere de escape e procura na string de destino para ver se é uma substring da string de destino.

Neste exemplo, você vê como a correspondência literal funciona. Considere uma situação em que os dados são coletados do tráfego do site, e o campo cs(referrer) contém o seguinte valor:

`https://www.abc.com/adventurenews/today.html?ad=123AZ45`

Para determinar se o referenciador representa alguém que clicou em um dos anúncios, é necessário ver se o referenciador contém o anúncio de string. Você poderia simplesmente usar a sequência de caracteres literal para pesquisar a sequência de destino e determinar se um anúncio foi usado para rotear o tráfego para o site. Embora isso correspondesse à string de destino, ela corresponderia em dois locais e, portanto, é ambígua e pode levar a falsos positivos.

O URL a seguir contém a string e em dois lugares diferentes:

`https://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Assim, se você estiver tentando determinar quais sessões foram iniciadas como resultado de uma campanha de publicidade específica, simplesmente usar o anúncio literal como a expressão regular claramente não é suficiente. Alterar o literal para &quot;ad=&quot; eliminaria essa ambiguidade e resultaria na expressão fazendo apenas uma correspondência. No entanto, mesmo isso pode não ser suficiente para garantir que o referenciador fizesse parte da campanha publicitária. Considere o seguinte referenciador:

`https://www.xyz.com/hello.html?pad=something`

Você não tem controle sobre os URLs que outras pessoas podem estar usando para criar links para o site. A correspondência literal é um mecanismo muito simples para localizar sessões que começaram como resultado da campanha de publicidade. A seção a seguir discute como você pode usar metacaracteres para obter uma correspondência mais flexível e eficiente.

## Uso de metacaracteres {#section-e29a804336304ea1ba33d40d60139aa2}

Um metacaractere é um caractere especial em um programa ou campo de dados que fornece informações sobre outros caracteres.

| metacaractere | descrição |
|---|---|
| . (ponto) | Corresponde a um único caractere, por exemplo: `re:x.z` corresponde a &quot;xyz&quot; ou &quot;xxz&quot;. |
| * (estrela) | Corresponde a um ou mais caracteres, por exemplo: `re:Z*` corresponde a &quot;ZZZ&quot;. |
| ? (curinga) | Corresponde a 0 ou 1 da expressão anterior para forçar a correspondência mínima, por exemplo: `xy?z` corresponde a &quot;xy&quot; e &quot;xyz&quot;. |

Expressões regulares comuns adicionais também podem ser usadas para criar strings de pesquisa mais complexas.

**Listas, Intervalos e OU**

A correspondência literal permite procurar uma única string, mas colchetes, traços e barra vertical permitem definir uma lista de coisas a serem procuradas na string de destino.

<table id="table_18B86955EC3748079E7C176273ADE92B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Para este metacarbonato... </th>
   <th colname="col2" class="entry"> O processador de expressão regular.. </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Colchetes ([ ]) </td>
   <td colname="col2"> Corresponda qualquer um dos caracteres dentro do colchete com uma única posição de caractere. Por exemplo, [AB] é uma instrução para corresponder à letra A ou à letra B e [0123456789] diz corresponder a qualquer caractere no intervalo de 0 a 9. </td>
  </tr>
  <tr>
   <td colname="col1"> Traço (-) </td>
   <td colname="col2"> <p>Corresponder a um intervalo de caracteres. Assim, em vez de escrever [0123456789], podíamos simplesmente escrever [0-9]. </p> <p> Isso pode ser estendido para intervalos de caracteres e vários intervalos dentro de um conjunto de colchetes. Por exemplo, [0-9A-C] corresponde aos caracteres de 0 a 9 e de A a C. </p> <p> <p>Observação:  Para testar se há um traço (-) como um literal dentro dos colchetes, ele deve vir primeiro ou por último. Por exemplo, [-0-9] testa - e 0 a 9. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Estágio (|) </td>
   <td colname="col2"> Corresponda uma de duas opções a uma determinada string de destino. Por exemplo, b|nat corresponde a bat ou nat. </td>
  </tr>
 </tbody>
</table>

Considere os exemplos a seguir:

| Padrão | String | Corresponder |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Lição`[A-Z]` | Lição a | Nenhuma correspondência porque a minúscula não está no intervalo de A a Z maiúsculo. |

**Negação**

A negação é uma maneira de dizer que você gostaria de corresponder qualquer coisa exceto os caracteres em questão. O metacaractere de negação, o circunflexo ou sinal de interpolação (`^`), é usado como o primeiro caractere entre colchetes para dizer que você gostaria que a correspondência fosse tudo, exceto os caracteres restantes entre colchetes. Por exemplo, para corresponder qualquer caractere, exceto um ponto e vírgula (`;`), você gravaria

[`^;`]

Isso corresponderia a qualquer caractere, exceto o ponto e vírgula.

**Posicionamento**

Para forçar uma correspondência para o início ou o fim de uma string de destino, um de dois metacaracteres é usado.

| Para este metacarbonato... | O processador de expressão regular.. |
|---|---|
| Circunflexo ou Cursor (`^`) | Corresponder ao início da string. Por exemplo, ^`[Tt]`ele corresponderia à string de destino &quot;O Início&quot;, mas não corresponderia a &quot;Este é o início&quot;. |
| Símbolo de moeda (`$`) | Corresponder ao final da string. Por exemplo, `[Ee]`nd$ corresponderia a &quot;Este é o fim&quot;, mas não corresponderia a &quot;O fim é um tempo especial&quot;. |

>[!NOTE]
>
>Quando a expressão regular contém ^ no início e $ no fim, toda a string de destino deve corresponder à expressão regular.

**Correspondência de qualquer coisa**

O período (.) é um metacaracter especial que corresponde a qualquer caractere na string de destino. Por exemplo, a expressão regular `^…$` corresponde a qualquer string de destino que tenha exatamente três caracteres. A expressão regular &quot;..&quot; corresponde a qualquer string de destino que contenha pelo menos três caracteres.

**Padrões repetidos**

Os metacaracteres de iteração permitem que você corresponda a um padrão mais de uma vez.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Para este metacarbonato... </th>
   <th colname="col2" class="entry"> O processador de expressão regular.. </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Ponto de interrogação (?) </td>
   <td colname="col2"> Não corresponde a instâncias ou a uma instância do caractere imediatamente antes do metacaractere (?). Por exemplo, o padrão rea?d corresponde a vermelho e read. </td>
  </tr>
  <tr>
   <td colname="col1"> Asterisco (*) </td>
   <td colname="col2"> Corresponder a zero ou mais ocorrências do caractere imediatamente antes do metacaractere (*). Por exemplo, o padrão [0-9]* corresponde a qualquer número de caracteres de 0 a 9 (qualquer inteiro). </td>
  </tr>
  <tr>
   <td colname="col1"> Plus (+) </td>
   <td colname="col2"> Corresponder a uma ou mais ocorrências do caractere ou intervalo anterior. Por exemplo, o padrão três+ corresponderia a três, mas não a até. </td>
  </tr>
  <tr>
   <td colname="col1"> {n} </td>
   <td colname="col2"> <p>Corresponder ao caractere de processo ou intervalo exatamente n vezes. O seguinte padrão corresponde aos números de telefone dos Estados Unidos: <code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>. </p> <p> Embora não seja um padrão ideal, ele determina se a string de destino está no formato adequado. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> {n,m} </td>
   <td colname="col2"> Corresponder ao caractere anterior pelo menos n vezes e no máximo m vezes. Por exemplo, fo{1,2}d corresponderia a comida e alimento, mas não a comida. </td>
  </tr>
 </tbody>
</table>

## Extração de padrão {#section-4389779653b64f6cb7c47615b25c1a79}

A correspondência de padrões é apenas parte do poder das expressões regulares. Expressões regulares também fornecem um mecanismo para extrair partes principais de uma string de destino. Isso é feito com o uso dos parênteses esquerdo e direito. Normalmente, essas extrações são usadas como entrada em outro processo e são acessadas por meio do uso de *%position%*, onde a posição é um número inteiro referindo-se à contagem de qual conjunto de parênteses foi correspondido.

Considere os seguintes exemplos de extração de padrão:

<table id="table_BC8D471B966844049FFFCDEC0F183941">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Padrão </th>
   <th colname="col2" class="entry"> String </th>
   <th colname="col3" class="entry"> Corresponder </th>
   <th colname="col4" class="entry"> Extração </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Win(9[58]) </td>
   <td colname="col2"> OS=Win95 </td>
   <td colname="col3"> Win95 </td>
   <td colname="col4"> %1% = 95 </td>
  </tr>
  <tr>
   <td colname="col1"> (Win)(95|8) </td>
   <td colname="col2"> OS=Win98 </td>
   <td colname="col3"> Win98 </td>
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td>
   <td colname="col2"> Mozilla/3.0 </td>
   <td colname="col3"> Mozilla/3.03 </td>
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Lição([A-Z]) </td>
   <td colname="col2"> Lição a </td>
   <td colname="col3"> Nenhuma correspondência porque a minúscula não está no intervalo de A maiúsculo a Z </td>
   <td colname="col4"> </td>
  </tr>
 </tbody>
</table>
