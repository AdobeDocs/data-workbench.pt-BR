---
description: Informações conceituais sobre marcação de terceiros e prevenção do bloqueio de cookies usando P3P.
title: Considerações sobre P3P para marcação de página de terceiros
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Considerações sobre P3P para marcação de página de terceiros{#p-p-considerations-for-third-party-page-tagging}

Informações conceituais sobre marcação de terceiros e prevenção do bloqueio de cookies usando P3P.

## Como entender a marcação de página de terceiros {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

Na maioria das implementações, o cookie persistente do Adobe é exibido como um cookie próprio. Os cookies próprios são definidos como os associados ao domínio do host.

Suponha que um usuário visite https://www.example.com/. Supondo que um Sensor esteja instalado e operacional no servidor da Web que hospeda o domínio, um cookie persistente do Adobe será definido e visualizado como um cookie próprio. No entanto, você pode desejar coletar dados de medição de um site de terceiros usando objetos incorporados, que são solicitados e carregados de seu servidor que está executando [!DNL Sensor] em vez de do servidor de terceiros que hospeda a página ou o programa de publicidade. Por exemplo, https://www.example2.com/ serve uma página da Web com uma solicitação de objeto incorporado veiculada em https://www.example.com/. A solicitação para o objeto incorporado de https://www.example.com/ resulta na definição de um cookie; no entanto, nesse contexto, o navegador da web ou o agente-usuário visualiza o cookie como um cookie de terceiros.

Em navegadores da Web mais recentes, como o IE6 da Microsoft, os recursos de privacidade filtram cookies com base em suas políticas compactas enviadas no cabeçalho de resposta HTTP do servidor da Web. Nas configurações padrão do IE6, que a maioria dos usuários nunca muda, os cookies de terceiros são bloqueados quando têm políticas compactas inexistentes ou insatisfatórias. A maioria dos sites que está enfrentando problemas de bloqueio de cookies tem cookies de terceiros no site que não têm as políticas compactas apropriadas sendo enviadas no cabeçalho de resposta HTTP. Além disso, alguns problemas de bloqueio de cookies ocorrem quando um site é enquadrado por outro site. Por exemplo, uma loja online que faz parte de um portal de compras online pode aparecer em um quadro fornecido pelo portal. Da perspectiva do navegador, o conteúdo da loja pode parecer ser de terceiros quando enquadrado pelo portal. No entanto, se um visitante for diretamente para a loja online sem passar pelo portal, o conteúdo será conteúdo primário. Assim, a loja online encontra seus cookies bloqueados somente quando os visitantes entram pelo portal.

Os sistemas de e-mail baseados na Web causam um problema semelhante. Se um visitante do site enviar uma página da Web por email para um amigo que usa um sistema de email baseado na Web, a mensagem de email será exibida como conteúdo de terceiros no navegador do amigo porque é enquadrada pelo sistema de email. Se houver cookies associados à página que foi enviada por email, eles serão tratados como cookies de terceiros pelo IE6.

## Usar o P3P para evitar o bloqueio de cookies {#section-96831cad887649f295aec6931750e41a}

O P3P fornece uma maneira padrão para os sites codificarem suas políticas de privacidade em um formato XML legível por computador. Os navegadores da Web habilitados para P3P e outros agentes de usuário do P3P buscam automaticamente as políticas de privacidade do P3P, analisam-nas e as comparam com as preferências de privacidade de um usuário.

Para evitar que o IE6 bloqueie cookies em seu site, você precisa garantir o seguinte:

1. Todos os cookies que estão sendo definidos em um contexto de terceiros têm políticas compactas P3P associadas a eles.
1. A política compacta apropriada é enviada usando um cabeçalho de resposta HTTP personalizado.
1. Essas políticas compactas são consideradas satisfatórias pelo IE6.
1. Se os cookies de terceiros estiverem sendo definidos por outra empresa, talvez seja necessário solicitar que habilite o P3P e defina políticas compactas P3P. Qualquer host que defina uma política compacta P3P também deve ter uma política P3P completa correspondente. Os usuários podem alterar suas configurações do IE6 para que os cookies também sejam bloqueados sob outras condições; no entanto, colocar políticas compactas satisfatórias em cookies de terceiros impede a maioria do bloqueio de cookies do IE6.

Este é um exemplo desse cabeçalho P3P:

```
P3P: policyref=” https://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

Neste exemplo, o arquivo [!DNL p3p.xml] é usado para fazer referência a um arquivo [!DNL policy.xml] associado que reside em seu servidor da Web, que indica os tipos de informações que seu site coleta, métodos de resolução de disputas que sua organização adere, como os dados coletados são usados, quem detém os dados e outras informações padrão relacionadas à Privacidade da Internet. Os três códigos de caracteres após o &quot;CP&quot; são os códigos de política compacta que emitem o que é declarado em seu arquivo [!DNL policy.xml].

Todas as políticas compactas e arquivos XML de política devem ser personalizados para a respectiva organização para a qual estão sendo implantados, especificando com precisão suas políticas internas de privacidade em relação à coleta de dados do site. Uma infinidade de editores de políticas P3P pode ser encontrada online, juntamente com informações mais detalhadas sobre a implementação de uma política de privacidade apropriada no seu site.

Para obter mais informações sobre como o Internet Explorer 6 lida com cabeçalhos P3P, visite:

[https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
