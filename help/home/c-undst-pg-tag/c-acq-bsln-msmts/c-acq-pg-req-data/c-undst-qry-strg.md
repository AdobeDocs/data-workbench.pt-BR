---
description: A sequência de caracteres de consulta (cs-uri-query) é frequentemente usada por aplicativos da Web e desenvolvedores de sites para passar informações de página para página devido à natureza sem estado do HTTP.
solution: Analytics
title: Como entender a string de consulta
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como entender a string de consulta{#understanding-the-query-string}

A sequência de caracteres de consulta (cs-uri-query) é frequentemente usada por aplicativos da Web e desenvolvedores de sites para passar informações de página para página devido à natureza sem estado do HTTP.

Em muitos casos, as informações podem ser passadas na string de consulta quando são adquiridas pelo [!DNL Sensor] no servidor da Web. Essas informações podem ser usadas [!DNL Site] para iluminar a verdadeira estrutura do site, o caminho dos visitantes através dele, bem como outras informações.

Em alguns sites dinâmicos, pares de nome=valor (variáveis) na string de consulta são importantes para determinar a página real que está sendo solicitada por um visitante. Nesses casos, os URLs podem ser estruturados da seguinte maneira ou de maneira semelhante:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

Neste exemplo, PAGENAME é na verdade o indicador de qual página será disponibilizada ao solicitante deste URL. Muitas ferramentas e serviços de análise de log da Web limitam a capacidade do operador do site de definir o que é uma página em seu site com base em quais variáveis de sequência de consulta ocorrem nas sequências de consulta dos URLs do site. O servidor da análise de big data e a análise de big data podem ser configurados para usar esses nomes de consulta para definir páginas exclusivas. Isso é importante porque muitos sistemas interpretariam os seguintes URLs como a mesma página, mas [!DNL Site] não.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Da mesma forma, os desenvolvedores e aplicativos do site muitas vezes adicionam muitas variáveis de sequência de consulta aos URLs de um site que não têm nada a ver com a identificação da página real que está sendo solicitada. Os exemplos são mostrados abaixo:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

Neste exemplo, a variável da string de consulta CAMPAIGN= foi adicionada ao URL. Essa variável CAMPAIGN está sendo usada para indicar qual campanha de marketing fez com que um visitante selecionasse esse URL. [!DNL Site] pode ser configurado para usar essas informações de CAMPANHA, mas separá-las da definição de que página um visitante visualizou para que na lista de páginas para fins de relatório e análise você visualize o seguinte:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

