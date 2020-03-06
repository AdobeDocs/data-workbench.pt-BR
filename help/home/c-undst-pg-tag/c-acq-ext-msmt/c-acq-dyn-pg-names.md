---
description: Para alguns sites, é necessário usar solicitações de objetos incorporados para passar informações para o servidor da Web, de modo que os detalhes sobre qual página foi realmente servida possam ser adquiridos pelo Sensor e usados para relatórios e análises.
solution: Analytics
title: Aquisição de nomes de página dinâmicos
topic: Data workbench
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aquisição de nomes de página dinâmicos{#acquiring-dynamic-page-names}

Para alguns sites, é necessário usar solicitações de objetos incorporados para passar informações para o servidor da Web, de modo que os detalhes sobre qual página foi realmente servida possam ser adquiridos pelo Sensor e usados para relatórios e análises.

Isso pode ser necessário se o URL da página, como visto pelo servidor da Web, não for indicativo do conteúdo da página que é mostrado ao navegador. Esse caso geralmente resulta do uso de sistemas de personalização ou gerenciamento dinâmico de conteúdo nos quais o conteúdo real disponibilizado em uma página é determinado dinamicamente pelo URL, pelo cookie, pelos dados relacionados e pela lógica do aplicativo.

A implementação de um objeto incorporado para coletar medidas adicionais deve ter impacto mínimo no desempenho geral do site. A Adobe sugere que você incorpore um arquivo JavaScript como o objeto usado para coletar os atributos estendidos. (Observe que um arquivo JavaScript pode ser incorporado sem qualquer impacto potencial no layout e na apresentação da sua página da Web, o que pode resultar no uso de uma imagem incorporada.) Para capturar com precisão as informações passadas dentro do objeto incorporado, a Adobe também sugere que um nome comum seja usado. Para fins de nomeação, a Adobe se refere a esse objeto como [!DNL zig.js]. O [!DNL zig.js] arquivo deve ser criado dentro do diretório apropriado em um servidor da Web no qual [!DNL Sensor] está instalado. Esse arquivo precisa existir para que a solicitação não retorne um código de erro 404. O conteúdo do arquivo em si não é importante. Você deve usar um arquivo em branco nomeado [!DNL zig.js] para minimizar a quantidade de tráfego de rede incorrido como resultado da solicitação.

Para [!DNL Sensor] coletar um nome utilizável para a página que foi realmente disponibilizada, algumas linhas do código JavaScript devem ser adicionadas às páginas dinâmicas que você deseja rastrear ou às quais deseja adicionar um nome de página exclusivo. Esse código incorpora um trecho do JavaScript na página, o que faz com que uma solicitação terciária de objeto incorporado seja feita ao servidor da Web enquanto a página está sendo carregada. Essa solicitação envia detalhes sobre a página específica que foi enviada de volta ao servidor da Web. O nome da página que foi realmente disponibilizada é levado de volta para o servidor da Web como uma variável na sequência de caracteres de consulta da solicitação de objeto incorporado (neste caso, JavaScript).

Em geral, a solicitação de objeto incorporada em cada uma dessas páginas HTML deve ter a seguinte aparência:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] garante que [!DNL Sensor] registre a solicitação, apesar das regras de filtragem do tipo de [!DNL Sensor] conteúdo, como a filtragem de solicitações de imagens e JavaScript antes de serem armazenadas. A variável v_pn declarada identifica o nome do conteúdo da página real que está sendo veiculado para que [!DNL Site] saiba o nome da página que o visitante realmente visualizou. O valor v_pn pode ser estabelecido manualmente ou por outro script ou código de aplicativo.

Depois que o valor é coletado, você pode configurar o servidor da análise de big data para usar o conteúdo da variável da string de consulta (par nome=valor, por exemplo, v_pn=Formulário de aplicativo) anexado ao [!DNL zag.gif] URI (por exemplo, [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]), como um acréscimo do [!DNL zag.gif] URI. Além das medidas de linha de base adquiridas com cada solicitação HTTP, uma medida estendida seria adquirida com essa solicitação.

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_pn= | Valor associado à variável da string de consulta v_pn | v_pn=Formulário de aplicativo |

