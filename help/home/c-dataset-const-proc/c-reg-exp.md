---
description: Expressões regulares são usadas em todos os campos de pesquisa da análise de big data, incluindo os painéis de entidade do query.
solution: Analytics
title: Expressões regulares
topic: Data workbench
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
translation-type: tm+mt
source-git-commit: 0727e5b18c89a22b6ee775b1293d3b68e5cee81c
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 2%

---


# Expressões regulares{#regular-expressions}

Expressões regulares são usadas em todos os campos de pesquisa da análise de big data, incluindo os painéis de entidade do query.

* [Sobre Expressões regulares](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologia de Expressão Regular](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [Sobre correspondência literal](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Uso de metacaracteres](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Extração de padrões](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## Sobre Expressões regulares {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Uma expressão regular é um padrão de texto, que consiste em uma combinação de caracteres alfanuméricos e caracteres especiais conhecidos como metacaracteres, que localiza padrões e extrai subsequências de texto. Expressões regulares são amplamente usadas na programação de computadores e são parte integrante de línguas como a Perl.

Para identificar e extrair padrões complexos de sequência de caracteres, o servidor da análise de big data usa expressões regulares em algumas das transformações e condições. O que se segue é um breve guia para expressões regulares.

Este apêndice não é uma introdução abrangente a expressões regulares. Uma referência particularmente boa é a publicação O&#39;Reilly *Mastering Regular Expressão, segunda edição* de Jeffrey E. F. Friedl.

## Terminologia de Expressão Regular {#section-80b0d54f731e448391532ab3eb3c525c}

| Termo | Definição |
|---|---|
| Literal | Um literal é um caractere que usamos em uma expressão regular para localizar uma sequência específica de caracteres. Por exemplo, para encontrar o produto no, [!DNL shop/products.html]o produto de string é um literal, ou o que estamos literalmente procurando na string. |
| Metacaractere | Um metacaractere é um caractere especial que tem uma interpretação exclusiva no contexto de expressões regulares. Por exemplo, o ponto (.) é um metacaractere usado para corresponder a qualquer caractere. |
| Sequência de escape | Uma sequência de escape é simplesmente uma forma de dizer ao mecanismo de expressão comum que gostaríamos de usar um dos metacaracteres como literal. Sequências de escape sempre start com o caractere de barra invertida (`\`). Ao colocar a barra invertida (que também é um metacaráter) na frente de um metacaráter, o mecanismo de expressão regular interpreta o metacaracter escapado como um literal. Por exemplo, se você deseja corresponder ao período de metacaractere (`.`), é necessário usar uma sequência de escape. No entanto, para corresponder a um dos pontos da string 168.196.0.11, você pode usar a expressão regular que consiste em uma barra invertida e um ponto (`\.`). |
| Padrão | Esta é a terminologia abreviada para a expressão regular. Em essência, uma expressão regular é um padrão que você está tentando comparar com a string do público alvo. |
| String de público alvo | Esse termo se refere à string que estamos pesquisando para localizar o padrão desejado. |

## Sobre correspondência literal {#section-ec4497e3160c47ba9b828d939761b3e0}

A correspondência literal usa uma sequência literal sem nenhum caractere de escape e procura na sequência do público alvo para ver se é uma subsequência de caracteres da sequência do público alvo.

Neste exemplo, você vê como a correspondência literal funciona. Considere uma situação na qual os dados são coletados do tráfego do site, e o campo cs(quem indicou) contém o seguinte valor:

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

Para determinar se a quem indicou representa alguém que clicou em um dos anúncios, é necessário verificar se a quem indicou contém o anúncio de string. Você poderia simplesmente usar a sequência de caracteres literal para pesquisar a sequência de caracteres do público alvo e determinar se um anúncio foi usado para direcionar o tráfego para o site. Embora isso corresponda à sequência de públicos alvos, ela corresponderia em dois locais e, portanto, é ambígua e pode levar a falsos positivos.

O URL a seguir contém o anúncio de string em dois lugares diferentes:

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Portanto, se você estiver tentando determinar quais sessões foram iniciadas como resultado de uma campanha de anúncio específica, simplesmente usar o anúncio literal, já que a expressão regular claramente não é suficiente. Alterar o literal para &quot;ad=&quot; eliminaria essa ambiguidade e resultaria na expressão fazendo apenas uma única correspondência. No entanto, mesmo isso pode não ser suficiente para garantir que a quem indicou seja parte da campanha do anúncio. Considere a seguinte quem indicou:

`http://www.xyz.com/hello.html?pad=something`

Você não tem nenhum controle sobre os URLs que outras pessoas podem estar usando para criar links para o site. A correspondência literal é um mecanismo muito simples para localizar sessões que foram iniciadas como resultado da campanha do anúncio. A seção a seguir discute como usar metacaracteres para obter uma correspondência mais flexível e poderosa.

## Uso de metacaracteres {#section-e29a804336304ea1ba33d40d60139aa2}

Um metacaractere é um caractere especial em um programa ou campo de dados que fornece informações sobre outros caracteres.

| metacaractere | descrição |
|---|---|
| . (ponto) | Corresponde a um único caractere, por exemplo: `re:x.z` corresponde a &quot;xyz&quot; ou &quot;xxz&quot;. |
| * (estrela) | Corresponde a um ou mais caracteres, por exemplo: `re:Z*` corresponde a &quot;ZZZ&quot;. |
| ? (curinga) | Corresponde a 0 ou 1 da expressão anterior para forçar a correspondência mínima, por exemplo: `xy?z` corresponde a &quot;xy&quot; e &quot;xyz&quot;. |

Expressões comuns adicionais também podem ser usadas para criar strings de pesquisa mais complexas.

**Listas, intervalos e OU**

A correspondência literal permite que você procure uma única string, mas colchetes, traços e barra vertical permitem que você defina uma lista de coisas a serem procuradas na string do público alvo.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este metacarbonato... </th> 
   <th colname="col2" class="entry"> O expressão normal... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Colchetes quadrados ([ ]) </td> 
   <td colname="col2"> Corresponder a qualquer um dos caracteres dentro do colchete com uma única posição de caractere. Por exemplo, [AB] é uma instrução para corresponder à letra A ou à letra B e [0123456789] diz corresponder a qualquer caractere no intervalo de 0 a 9. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Traço (-) </td> 
   <td colname="col2"> <p>Corresponder a um intervalo de caracteres. Assim, em vez de escrever [0123456789], podíamos simplesmente escrever [0-9]. </p> <p> Isso pode ser estendido para intervalos de caracteres e vários intervalos dentro de um conjunto de colchetes. Por exemplo, [0-9A-C] corresponde aos caracteres de 0 a 9 e de A a C. </p> <p> <p>Observação:  Para testar se há um traço (-) como literal dentro dos colchetes, ele deve vir primeiro ou por último. Por exemplo, [-0-9] testa para - e 0 a 9. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Estágio (|) </td> 
   <td colname="col2"> Corresponder uma de duas opções a uma determinada string de público alvo. Por exemplo, b|nat corresponde a bat ou nat. </td> 
  </tr> 
 </tbody> 
</table>

Considere os exemplos a seguir:

| Padrão | String | Correspondência |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Lição`[A-Z]` | Lição a | Nenhuma correspondência porque a minúsculo não está no intervalo de A a Z maiúsculo. |

**Negação**

A negação é uma forma de dizer que você gostaria de corresponder a qualquer item, exceto aos caracteres especificados. O metacaractere de negação, o circunflexo ou o caractere circunflexo (`^`), é usado como o primeiro caractere entre colchetes para dizer que você gostaria que a correspondência fosse qualquer coisa, exceto os caracteres restantes entre colchetes. Por exemplo, para corresponder qualquer caractere, exceto um ponto-e-vírgula (`;`), você escreveria

[`^;`]

Isso corresponderia a qualquer caractere, exceto o ponto-e-vírgula.

**Posicionamento**

Para forçar uma correspondência ao início ou ao fim de uma string de público alvo, um de dois metacaracteres é usado.

| Para este metacarbonato... | O expressão normal... |
|---|---|
| Circumflex ou Caret (`^`) | Corresponder ao início da string. Por exemplo, ^`[Tt]`ele corresponderia à string de público alvo &quot;O início&quot;, mas não corresponderia a &quot;Este é o início&quot;. |
| Símbolo de moeda (`$`) | Corresponder ao final da string. Por exemplo, `[Ee]`nd$ corresponderia a &quot;Este é o fim&quot;, mas não corresponderia a &quot;O fim é um tempo especial&quot;. |

>[!NOTE]
>
>Quando a expressão regular contém ^ no início e $ no final, a string inteira do público alvo deve corresponder à expressão normal.

**Correspondência de qualquer coisa**

O ponto (.) é um metacaractere especial que corresponde a qualquer caractere na string do público alvo. Por exemplo, a expressão regular `^…$` corresponde a qualquer string de público alvo com exatamente três caracteres. A expressão regular &quot;...&quot; corresponde a qualquer string de público alvo que contenha pelo menos três caracteres.

**Padrões repetidos**

Metacaracteres de iteração permitem que você corresponda a um padrão mais de uma vez.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este metacarbonato... </th> 
   <th colname="col2" class="entry"> O expressão normal... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ponto de interrogação (?) </td> 
   <td colname="col2"> Não corresponde a nenhuma instância ou a uma instância do caractere imediatamente anterior ao metacaractere (?). Por exemplo, o padrão rea?d corresponde a red e read. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Asterisco (*) </td> 
   <td colname="col2"> Corresponder a zero ou mais ocorrências do caractere imediatamente antes do metacaractere (*). Por exemplo, o padrão [0-9]* corresponde a qualquer número de caracteres de 0 a 9 (qualquer número inteiro). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> Corresponder uma ou mais ocorrências do caractere ou intervalo anterior. Por exemplo, o padrão três+ corresponderia a três, mas não a through. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Corresponder ao caractere de processo ou intervalo exatamente n vezes. O seguinte padrão corresponde aos números de telefone dos Estados Unidos: <code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>. </p> <p> Embora não seja um padrão ideal, ele determina se a string do público alvo está no formato correto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Corresponder ao caractere anterior pelo menos n vezes e no máximo em m vezes. Por exemplo, fo{1,2}d corresponderia a comida e comida, mas não a comida. </td> 
  </tr> 
 </tbody> 
</table>

## Extração de padrões {#section-4389779653b64f6cb7c47615b25c1a79}

A correspondência de padrões é apenas parte do poder das expressões regulares. Expressões regulares também fornecem um mecanismo para extrair partes principais de uma sequência de públicos alvos. Isso é feito com o uso dos parênteses esquerdo e direito. Normalmente, essas extrações são usadas como entrada em outro processo e são acessadas por meio do uso de *%position%*, onde position é um número inteiro que se refere à contagem de qual conjunto de parênteses correspondeu.

Considere os seguintes exemplos de extração de padrões:

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Padrão </th> 
   <th colname="col2" class="entry"> String </th> 
   <th colname="col3" class="entry"> Correspondência </th> 
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
   <td colname="col3"> Nenhuma correspondência porque a minúsculo não está no intervalo de A a Z maiúsculo </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

