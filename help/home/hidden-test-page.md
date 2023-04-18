---
title: Página de teste oculta
description: Esta página está oculta da pesquisa e do TOC
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
source-git-commit: 87af4ae77f71701b52247f996b89edfb93794dd7
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 2%

---

# Página de teste oculta

## Etiquetas

Um selo é um rótulo colorido usado como um indicador de conteúdo. Por exemplo, você pode adicionar um selo para marcar um artigo como _Beta_ ou uma seção como _Premium_. Você pode alterar a cor de um selo e associar um URL e uma dica de ferramenta.

[!BADGE Exemplo de selo]

Há dois tipos de emblemas, cada um com uma sintaxe diferente:

* **Metadados** - Exibe o selo próximo à parte superior de uma página
* **Inline** - Exibe o símbolo onde a sintaxe está localizada

### Selos de metadados

Adicionar a sintaxe do selo nos metadados coloca um selo acima do título da página (H1) no artigo.

É possível nomear emblemas, por exemplo, usando _selo1_ ou _badge2_. Ou você pode ser mais criativo (desde que o nome comece com _emblema_).

Exemplos de metadados:

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** Este exemplo exibe um selo Premium com um URL e uma dica de ferramenta.

* **badgeExam:** Este exemplo exibe um selo escuro com um número de ID de exame.

#### Etiquetas embutidas

Especifique as informações do selo em sua própria linha ou em um cabeçalho, tabela ou outro elemento de página.

Esta é a sintaxe de um selo em linha com um rótulo beta, cor azul, URL e dica de ferramenta:

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Cores de selo disponíveis

Os emblemas usam as cores definidas no Adobe Spectrum:

| Tipo | Símbolo |
|---|---|
| Informativo (padrão) | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| Positiva | [!BADGE Novo recurso]{type=Positive url="https://www.example.com" tooltip="Vá para example.com"} |
| Negativa | [!BADGE Descontinuação]{type=negative tooltip="Esse recurso agora está no fim da vida útil"} |
| Neutra | [!BADGE Talvez]{type=Neutral tooltip="Um cavaleiro caiu do cavalo..."} |
| Cuidado | [!BADGE Atenção]{type=Caution tooltip="Estado amarelo"} |

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

### Requisitos para os cartões

* Somente dois emblemas são permitidos nos metadados. Essa regra é configurável, portanto, informe-nos se precisar de uma exceção.
* Somente o rótulo do selo é necessário. O `type`, `url`e `tooltip` são opcionais. O `type` determina a cor. O `url` permite que os usuários cliquem no selo para abrir um artigo ou uma página. O `tooltip` exibe o texto da dica de ferramenta ao passar o mouse sobre ele.
* Adicionar um selo ao `TOC.md` O arquivo exibe o selo em cada artigo no guia. Se você especificar um URL para o selo ir para um artigo, certifique-se de usar um link raiz (por exemplo, `/help/guide/article.md`) não é um link relativo (por exemplo, `article.md`) para considerar artigos em pastas diferentes.
* Adicionar um selo a `metadata-new.md` exibe o selo em cada artigo em um acordo de recompra.
* Para emblemas de metadados, verifique se todos os valores estão entre aspas. Para emblemas em linha, verifique se `url` e `tooltip` são encapsuladas entre aspas.
* Os valores de tipo válidos incluem *Informativo* (padrão, azul), *Positivo* (verde), *Negativo* (vermelho), *Neutro* (cinza escuro) e *Cuidado* (amarelo).
* Rótulos de emblema estão localizados.
* Se vários selos de metadados forem especificados, os emblemas serão exibidos em ordem alfabética com base no nome do emblema, como `badge1:` ou `badgeWeb`.
* Se desejar que o URL seja aberto em uma nova guia, use esta sintaxe:

   ```
   [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
   ```

   Renderizado:

   [!BADGE Abrir em uma nova guia]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Abra o adobe.com na nova guia"}

## Destaque do texto

A equipe do Workfront pediu para usar o realce amarelo para indicar a pré-visualização dos recursos futuros. Veja como funciona.

Exemplo 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Renderizado:

Todo este parágrafo NÃO deve ser destacado. <span class="preview"> Esta palavra é **bold** dentro de uma frase realçada.</span> E esta é apenas a última frase.

Exemplo 2:

```
Highlighting should start after this paragraph.

<span class="preview">

**This is a test**

>[!TIP]
>
>Drink 6 cups of water a day.

Last highlighted paragraph

</span>

Not highlighted
```

Renderizado:

O realce deve começar após este parágrafo.

<span class="preview">

**Este é um teste**

>[!TIP]
>
>Beba 6 xícaras de água por dia.

Último parágrafo destacado

</span>

Não destacado

## Realce de sintaxe para blocos de código

O Experience League oferece suporte ao realce da sintaxe para blocos de código. Certifique-se de especificar um idioma como `java` depois do conjunto de aberturas de acentos graves para garantir que a sintaxe seja realçada corretamente. Para obter uma lista de idiomas válidos, consulte [https://prismjs.com](https://prismjs.com/#supported-languages). Se algum idioma estiver faltando, registre um tíquete jira.

### Numeração de linha em blocos de código

Adicionar `{line-numbers="true"}` após o idioma para ativar a numeração de linha.

Exemplo com números de linha (&grave;&grave;&grave;;`html {line-numbers="true"}`):

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

Adicionar `start-number="n"` após a sintaxe do número da linha para iniciar a numeração em um número diferente de 1.

Exemplo com nova linha de início (&grave;&grave;&grave;;`html {line-numbers="true" start-line="7"}`):

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

### Realce da linha em blocos de código

Adicionar `highlight="n"` após a sintaxe do número da linha para destacar linhas em um bloco de código. Especificação `11-13, 16` destacará as linhas 11 a 13 e 16.

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
