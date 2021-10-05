---
description: A sequência de consulta (cs-uri-query) é frequentemente usada por aplicativos da Web e desenvolvedores de sites para transmitir informações de página para página devido à natureza sem estado do HTTP.
title: Compreender a sequência de consulta
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# Compreender a sequência de consulta{#understanding-the-query-string}

A sequência de consulta (cs-uri-query) é frequentemente usada por aplicativos da Web e desenvolvedores de sites para transmitir informações de página para página devido à natureza sem estado do HTTP.

Em muitos casos, as informações podem ser passadas na string de consulta quando são adquiridas por [!DNL Sensor] no servidor da Web. Essas informações podem ser usadas por [!DNL Site] para iluminar a verdadeira estrutura do site, o caminho dos visitantes através dele, bem como outras informações.

Em alguns sites dinâmicos, os pares name=value (variáveis) na sequência de consulta são importantes para determinar a página real que está sendo solicitada por um visitante. Nesses casos, os URLs podem ser estruturados da seguinte maneira ou de maneira semelhante:

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

Neste exemplo, PAGENAME é, na verdade, o indicador de qual página será disponibilizada ao solicitante deste URL. Muitas ferramentas e serviços de análise de log da Web limitam a capacidade do operador do site de definir o que uma página é em seu site com base em quais variáveis de sequência de consulta ocorrem nas sequências de consulta dos URLs do site. O servidor do Data Workbench e o Data Workbench podem ser configurados para usar esses nomes de query para definir páginas exclusivas. Isso é importante porque muitos sistemas interpretariam os seguintes URLs como a mesma página, mas [!DNL Site] não.

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
https://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Da mesma forma, desenvolvedores de site e aplicativos frequentemente adicionam muitas variáveis de sequência de consulta aos URLs de um site que não têm nada a ver com a identificação da página real que está sendo solicitada. Os exemplos são mostrados abaixo:

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

Neste exemplo, a variável da string de consulta CAMPAIGN= foi adicionada ao URL. Essa variável CAMPAIGN está sendo usada para indicar qual campanha de marketing fez com que um visitante selecionasse esse URL. [!DNL Site] O pode ser configurado para usar essas informações da CAMPANHA, no entanto, separá-las da definição de qual página um visitante visualizou, de modo que na lista de páginas para fins de análise e relatório você veja o seguinte:

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
