---
description: O site usa cookies para identificar de forma exclusiva os visitantes do site e rastrear o comportamento deles ao longo do tempo.
solution: Analytics
title: Como entender o cookie v1st
topic: Data workbench
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Como entender o cookie v1st{#understanding-the-v-st-cookie}

O site usa cookies para identificar de forma exclusiva os visitantes do site e rastrear o comportamento deles ao longo do tempo.

A primeira vez que um determinado navegador (considerado um visitante) faz uma solicitação de seu site, [!DNL Sensor] trabalha com o servidor da Web para definir um cookie persistente, cs(cookie)(v1st), que é interpretado internamente no sistema como x-trackingid. Este cookie persistente é definido além de qualquer outro cookie que seu site possa definir. Este cookie otimiza sua capacidade de rastrear seus visitantes em várias sessões, o que permite vários tipos de análise que, de outra forma, são impossíveis.

[!DNL Sensor] atribui uma chave numérica de 64 bits no cookie para identificar novos visitantes que fazem uma solicitação do site como um identificador exclusivo. Quando o [!DNL Sensor] visualiza uma solicitação de um navegador, ele verifica se &quot;cs(cookie)(v1st)&quot;, um cookie persistente primário definido por [!DNL Sensor], existe nos dados da solicitação. Se o cs(cookie)(v1st) não estiver presente, [!DNL Sensor], por meio do servidor da Web, instrui o navegador a defini-lo. Ao contrário de outras soluções, [!DNL Sensor] é possível definir esse cookie na primeira solicitação do visitante.

Abaixo está o cabeçalho de cookie persistente padrão enviado para o navegador na primeira solicitação do site pelo servidor da Web, na direção de [!DNL Sensor]. O formato pode ser definido no momento da configuração se um nome ou uma data de expiração diferente for desejada. Por exemplo:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Este cookie é definido apenas uma vez, na primeira solicitação feita ao site por esse visitante. Em seguida, ele é coletado desse visitante toda vez que o navegador fizer uma solicitação (página ou solicitação de objeto incorporado) do site no futuro. O tamanho do cookie é muito pequeno para minimizar a quantidade de largura de banda usada para transmiti-lo aos servidores com cada solicitação desse navegador para o site.

A aceitação de um cookie persistente fica à discrição do navegador. A maioria dos usuários da Web entende o que os cookies fazem e também reconhece que os cookies primários oferecem uma grande vantagem para eles ao permitir que o conteúdo do site seja personalizado de acordo com suas preferências. Esses cookies primários não são bloqueados pelas configurações de segurança padrão dos navegadores populares. Se um usuário optar por bloquear cookies primários, suas solicitações de visualização de página ainda serão registradas, mas os dados de medição dessas solicitações não poderão ser correlacionados de forma confiável a um visitante específico ou a suas sessões no site. Muitos sites, especialmente sites dinâmicos sofisticados, já usam cookies primários, que em muitos casos são necessários para permitir que aplicativos da Web operem para o visitante. Um recuo de um cookie persistente é um cookie de sessão, que permite que uma série de solicitações sejam agrupadas em uma sessão, mas não permite o rastreamento de visitantes entre sessões. [!DNL Site] é capaz de dimensionar os dados do visitante com base em cookies de sessão ou por número IP, mas ambos os métodos diminuem significativamente os tipos e o valor da análise que podem ser realizados com [!DNL Site] ou qualquer outro sistema de análise e relatório de atividade da Web.
