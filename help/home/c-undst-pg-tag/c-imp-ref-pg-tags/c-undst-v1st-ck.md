---
description: O site usa cookies para identificar de forma exclusiva os visitantes do site e rastrear o comportamento deles ao longo do tempo.
title: Compreender o cookie v1st
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# Compreender o cookie v1st{#understanding-the-v-st-cookie}

{{eol}}

O site usa cookies para identificar de forma exclusiva os visitantes do site e rastrear o comportamento deles ao longo do tempo.

A primeira vez que um determinado navegador (considerado um visitante) faz uma solicitação de seu site, [!DNL Sensor] O funciona com o servidor da Web para definir um cookie persistente, cs(cookie)(v1st), que é interpretado internamente no sistema como x-trackingid. Esse cookie persistente é definido além de qualquer outro cookie que seu site possa definir. Esse cookie otimiza sua capacidade de rastrear seus visitantes em várias sessões, o que permite vários tipos de análise que, de outra forma, seriam impossíveis.

[!DNL Sensor] atribui uma chave numérica de 64 bits no cookie para identificar novos visitantes que fazem uma solicitação do site como um identificador exclusivo. Quando a variável [!DNL Sensor] vê uma solicitação de um navegador, ele verifica se &quot;cs(cookie)(v1st)&quot;, um cookie persistente primário definido por [!DNL Sensor], existe nos dados da solicitação. Se o cs(cookie)(v1st) não estiver presente, [!DNL Sensor], por meio do servidor da Web, informa ao navegador para configurá-lo. Ao contrário de outras soluções, [!DNL Sensor] O pode definir esse cookie na primeira solicitação do visitante.

Abaixo está o cabeçalho de cookie persistente padrão enviado ao navegador em sua primeira solicitação do site pelo servidor da Web, na direção de [!DNL Sensor]. O formato pode ser definido no momento da configuração, se desejar um nome ou uma data de expiração diferente. Por exemplo:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Este cookie é definido apenas uma vez, na primeira solicitação feita ao seu site por esse visitante. Em seguida, ele é coletado desse visitante sempre que o navegador fizer uma solicitação (página ou solicitação de objeto incorporada) do site no futuro. O cookie é de tamanho muito pequeno para minimizar a quantidade de largura de banda usada para transmiti-lo para seus servidores com cada solicitação desse navegador para o site.

Aceitar um cookie persistente depende do navegador. A maioria dos usuários da Web entende o que os cookies fazem e também reconhece que os cookies primários proporcionam um benefício valioso para eles ao permitir que o conteúdo do site seja personalizado de acordo com suas preferências. Esses cookies próprios não são bloqueados pelas configurações de segurança padrão dos navegadores populares. Se um usuário optar por bloquear cookies primários, suas solicitações de exibição de página ainda serão registradas, mas os dados de medição dessas solicitações não poderão ser correlacionados de maneira confiável a um visitante específico ou a suas sessões no site. Muitos sites, especialmente sites dinâmicos sofisticados, já usam cookies primários, que são necessários em muitos casos para permitir que aplicativos Web operem para o visitante. Um retrocesso de um cookie persistente é um cookie de sessão, que permite que uma série de solicitações sejam agrupadas em uma sessão, mas não permite o rastreamento de visitantes entre sessões. [!DNL Site] O é capaz de dimensionar os dados do visitante com base nos cookies da sessão ou pelo número de IP, mas ambos os métodos diminuem significativamente os tipos e o valor da análise que pode ser realizada com [!DNL Site] ou qualquer outro sistema de análise e relatório de atividade da Web.
