---
description: Informações conceituais sobre marcação de terceiros e prevenção do bloqueio de cookies usando o P3P.
solution: Analytics
title: Considerações sobre P3P para marcação de página de terceiros
topic: Data workbench
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Considerações sobre P3P para marcação de página de terceiros{#p-p-considerations-for-third-party-page-tagging}

Informações conceituais sobre marcação de terceiros e prevenção do bloqueio de cookies usando o P3P.

## Como entender a marcação de páginas de terceiros {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

Na maioria das implementações, o cookie persistente da Adobe é exibido como um cookie primário. Os cookies primários são definidos como os associados ao domínio do host.

Suponha que um usuário visite http://www.example.com/. Supondo que um Sensor esteja instalado e operacional no servidor da Web que hospeda o domínio, um cookie persistente da Adobe será definido e exibido como um cookie primário. No entanto, você pode desejar coletar dados de medição de um site de terceiros usando objetos incorporados, que são solicitados e carregados do servidor que está sendo executado em vez do servidor de terceiros que hospeda a página ou o programa de publicidade. [!DNL Sensor] Por exemplo, http://www.example2.com/ serve uma página da Web com uma solicitação de objeto incorporado fornecida em http://www.example.com/. A solicitação do objeto incorporado de http://www.example.com/ resulta na definição de um cookie; no entanto, nesse contexto, o navegador da Web ou o agente-usuário visualiza o cookie como um cookie de terceiros.

Em navegadores da Web mais recentes, como o IE6 da Microsoft, os recursos de privacidade filtram cookies com base em suas políticas compactas enviadas no cabeçalho de resposta HTTP do servidor da Web. Nas configurações padrão do IE6, que a maioria dos usuários nunca muda, os cookies de terceiros são bloqueados quando possuem políticas compactas inexistentes ou insatisfatórias. A maioria dos sites com problemas de bloqueio de cookies tem cookies de terceiros no site que não têm as políticas compactas apropriadas sendo enviadas no cabeçalho de resposta HTTP. Além disso, alguns problemas de bloqueio de cookies ocorrem quando um site é enquadrado por outro site. Por exemplo, uma loja online que faz parte de um portal de compras online pode aparecer em um quadro fornecido pelo portal. Na perspectiva do navegador, o conteúdo da loja pode parecer ser de terceiros quando enquadrado pelo portal. No entanto, se um visitante for diretamente para a loja online sem passar pelo portal, o conteúdo será conteúdo primário. Assim, a loja online encontra seus cookies bloqueados somente quando os visitantes entram pelo portal.

Os sistemas de correio baseados na Web causam um problema semelhante. Se um visitante de um site enviar uma página da Web por email para um amigo que usa um sistema de email baseado na Web, a mensagem de email será exibida como conteúdo de terceiros no navegador do amigo, pois ela é enquadrada pelo sistema de email. Se houver cookies associados à página que foi enviada por email, eles serão tratados como cookies de terceiros pelo IE6.

## Uso do P3P para impedir o bloqueio de cookies {#section-96831cad887649f295aec6931750e41a}

O P3P fornece uma maneira padrão de os sites codificarem suas políticas de privacidade em um formato XML legível por computador. Navegadores da Web habilitados para P3P e outros agentes de usuário P3P buscam automaticamente políticas de privacidade P3P, analisam e comparam com as preferências de privacidade do usuário.

Para impedir que o IE6 bloqueie cookies no seu site, é necessário garantir o seguinte:

1. Todos os cookies que estão sendo definidos em um contexto de terceiros têm políticas compactas P3P associadas a eles.
1. A política compacta apropriada é enviada usando um cabeçalho de resposta HTTP personalizado.
1. Essas políticas compactas são consideradas satisfatórias pelo IE6.
1. Se os cookies de terceiros estiverem sendo definidos por outra empresa, talvez seja necessário solicitar que habilitem o P3P e definam políticas compactas P3P. Qualquer host que defina uma política compacta P3P também deve ter uma política P3P completa correspondente. Os usuários podem alterar suas configurações do IE6 para que os cookies também sejam bloqueados sob outras condições; no entanto, colocar políticas compactas satisfatórias em cookies de terceiros impede a maioria dos bloqueios de cookies do IE6.

A seguir está um exemplo de um cabeçalho P3P:

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

Neste exemplo, o arquivo [!DNL p3p.xml] é usado para fazer referência a um [!DNL policy.xml] arquivo associado que reside em seu servidor Web e que indica os tipos de informações que seu site coleta, os métodos de resolução de disputas que sua organização segue, como os dados coletados são usados, quem possui os dados e outras informações padrão relacionadas à Privacidade da Internet. Os três códigos de caracteres que seguem o &quot;CP&quot; são os códigos de política compactos que emitem o que está declarado no seu [!DNL policy.xml] arquivo.

Todas as políticas compactas e arquivos XML de política devem ser personalizados para a respectiva organização para a qual estão sendo implantados, especificando com precisão suas políticas internas de privacidade em relação à coleta de dados do site. Vários editores de políticas P3P podem ser encontrados on-line, além de informações mais aprofundadas sobre a implementação de uma política de privacidade apropriada em seu site.

Para obter mais informações sobre como o Internet Explorer 6 lida com os cabeçalhos P3P, visite:

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
