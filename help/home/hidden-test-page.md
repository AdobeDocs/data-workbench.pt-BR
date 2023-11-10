---
title: Página de teste oculta
description: Esta página está oculta da pesquisa e do índice
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Baixar Premium"
badgeExam: label="Exame ADO-E903" type="neutral"
exl-id: 02245655-511e-4e89-8846-dac85681ea91
source-git-commit: 6a10bc9a2ed41223070f3eba94b8ea7b4b1b77ab
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 4%

---

# Página de teste oculta

Ativar? Verifique o envio novamente por volta das 15h10. Será que ele entrará em funcionamento às 15h30?

## Visualizar problema

O parágrafo a seguir não é renderizado corretamente na Visualização do VSC. Não sei por quê.

Se sua senha for gerenciada por [!DNL Adobe], você pode [alterar a senha na sua conta Adobe](https://helpx.adobe.com/manage-account/using/change-or-reset-password.html){target="_blank"}.

## Tipos de Notas

Todos os tipos de notas compatíveis.

>[!NOTE]
>
>This is a standard NOTE block.

>[!TIP]
>
>This is a standard tip.

>[!IMPORTANT]
>
>Essa é uma observação importante.

>[!WARNING]
>
>Isso é um aviso.

>[!CAUTION]
>
>Isso é um aviso.

>[!ADMIN]
>
>Esta é uma nota de administração que é renderizada como ADMINISTRAÇÃO. Somente EXL.

>[!AVAILABILITY]
>
>Esta é uma nota de disponibilidade. Somente EXL.

>[!PREREQUISITES]
>
>Esta é uma observação de Pré-requisitos. Somente EXL.

>[!INFO]
>
>Esta é uma Nota informativa. Somente EXL.

>[!ERROR]
>
>Esta é uma nota de erro. Somente EXL.

>[!SUCCESS]
>
>Esta é uma Nota de sucesso. Somente EXL.

>[!MORELIKETHIS]
>
>* Página 1
>* Página 2

## Medalhas

Um selo é um rótulo colorido usado como indicador de conteúdo. Por exemplo, é possível adicionar um selo para marcar um artigo como _Beta_ ou uma seção como _Premium_. É possível alterar a cor de um selo e associar um URL e uma dica de ferramenta.

[!BADGE Exemplo de medalha]

Há dois tipos of selos, cada um com sintaxe diferente:

* **Metadados** - Exibe o selo próximo à parte superior de uma página
* **Em linha** - Exibe o selo onde a sintaxe está localizada

### Selos de metadados

A adição da sintaxe do selo nos metadados coloca um selo acima do título da página (H1) no artigo.

É possível nomear selos, por exemplo, usando _selo1_ ou _selo2_. Ou você pode ser mais criativo (desde que o nome comece com _selo_).

Exemplos de metadados:

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **seloPremium:** Este exemplo exibe um selo Premium com um URL e uma dica de ferramenta.

* **badgeExam:** Este exemplo exibe um emblema escuro com um número de ID de exame.

#### Medalhas em linha

Especifique as informações do selo em sua própria linha ou em um cabeçalho, tabela ou outro elemento de página.

Esta é a sintaxe de um selo em linha com um rótulo beta, cor azul, URL e dica de ferramenta:

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Cores dos selos disponíveis

Os emblemas usam cores definidas no Espectro de Adobe:

| Tipo | Medalha |
|---|---|
| Informativo (padrão) | [!BADGE  Beta]{type=Informative url="https://www.example.com"} |
| Positiva | [!BADGE Novo recurso]{type=Positive url="https://www.example.com" tooltip="Acesse example.com"} |
| Negativa | [!BADGE Descontinuado]{type=negative tooltip="Este recurso chegou ao fim da vida útil"} |
| Neutra | [!BADGE Talvez]{type=Neutral tooltip="Um cavaleiro caiu do cavalo."} |
| Cuidado | [!BADGE Atenção]{type=Caution tooltip="Status amarelo"} |

Exemplos de sintaxe

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### Requisitos para selos

* Somente duas medalhas são permitidas nos metadados. Essa regra é configurável, portanto, informe-nos se você precisa de uma exceção.
* Somente o rótulo do selo é obrigatório. A variável `type`, `url`, e `tooltip` parâmetros são opcionais. A variável `type` determina a cor. A variável `url` permite que os usuários cliquem no selo para abrir um artigo ou página. A variável `tooltip` exibe o texto da dica de ferramenta ao passar o mouse.
* Adicionar um selo à `TOC.md` arquivo exibe o selo em cada artigo no guia. Se você especificar um URL para o selo pular para um artigo, certifique-se de usar um link raiz (por exemplo, `/help/guide/article.md`) não é um link relativo (por exemplo, `article.md`) para levar em conta os artigos em pastas diferentes.
* Adicionar um selo a `metadata-new.md` exibe o selo em cada artigo em um repositório.
* Para selos de metadados, verifique se todos os valores estão entre aspas. Para selos em linha, verifique se `url` e `tooltip` estão entre aspas.
* Os valores de tipo válido incluem *Informativo* (padrão, azul), *Positivo* (verde), *Negativo* (vermelho), *Neutro* (cinzento escuro), e *Cuidado* (amarelo).
* Os rótulos de selo estão localizados.
* Se vários selos de metadados forem especificados, eles serão exibidos em ordem alfabética com base no nome do selo, como `badge1:` ou `badgeWeb`.
* Se quiser que o URL seja aberto em uma nova guia, use esta sintaxe:

  ```
  [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
  ```

  Renderizado:

  [!BADGE Abrir em nova guia]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Abrir adobe.com em nova guia"}

## Realce do texto

A equipe do Workfront pediu para usar o realce amarelo para indicar a pré-visualização dos recursos futuros. É assim que funciona.

Exemplo 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Renderizado:

Todo este parágrafo NÃO deve ser destacado. <span class="preview"> Esta palavra é **negrito** dentro de uma frase destacada.</span> E esta é apenas a última frase.

Exemplo 2:

```
Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

This is a new paragraph, then an image

![image](/help/home/assets/analytics-icon-24.png)

Last highlighted item.

</div>

Not highlighted
```

Renderizado:

O realce deve começar após este parágrafo.

<div class="preview">

Início de DIV.

Este é um novo parágrafo, depois uma imagem

![imagem](/help/home/assets/analytics-icon-24.png)

Último item realçado.

</div>

Não realçado

## Realce de sintaxe para blocos de código

O Experience League suporta realce de sintaxe para blocos de código. Certifique-se de especificar um idioma como `java` após o conjunto de acentos graves de abertura para verificar se a sintaxe está realçada corretamente. Para obter uma lista de idiomas válidos, consulte [https://prismjs.com](https://prismjs.com/#supported-languages). Se algum idioma estiver ausente, registre um tíquete jira.

### Numeração de linha em blocos de código

Adicionar `{line-numbers="true"}` depois do idioma para ativar a numeração de linha.

Exemplo com números de linha (&grave;&grave;&grave;`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**Iniciar numeração na linha _**

Adicionar `start-number="n"` após a sintaxe de número de linha para iniciar a numeração em um número diferente de 1.

Exemplo com a nova linha inicial (&grave;&grave;&grave;`html {line-numbers="true" start-line="7"}`):

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### Realce de linha em blocos de código

Adicionar `highlight="n"` sintaxe após número de linha para destacar linhas em um bloco de código. Especificação `11-13, 16` destacará as linhas 11 a 13 e 16.

Exemplo com realce de linha (&grave;&grave;&grave;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```
