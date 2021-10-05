---
description: Os resultados dos testes devem ser claros e significativos para que você se sinta confiante em tomar decisões em dólares com base nesses resultados.
solution: Analytics,Analytics
title: O que devo testar?
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
exl-id: 0f06ff0f-b385-4614-8007-afdb85191a85
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# O que devo testar?{#what-should-i-test}

Os resultados dos testes devem ser claros e significativos para que você se sinta confiante em tomar decisões em dólares com base nesses resultados.

Embora você possa testar vários layouts de página com [!DNL Sensor] e Site, o Adobe sugere que você se concentre em testar o alto valor, iniciativas estratégicas de negócios ou funcionalidades novas ou reprojetadas de sites que atendam às metas definidas para seu site, bem como para sua empresa. Você pode testar esses problemas, como as melhores garantias de preço, funcionalidade de personalização, ofertas de mercado (por exemplo, pacotes ou pacotes), design criativo e processos de aplicativo.

Os seguintes conceitos são mais importantes ao desenvolver seu experimento controlado:

* **Entenda as alterações certas para fazer.** Isso requer alguma pesquisa sobre como o seu site funciona e os processos de negócios subjacentes ao site de front-end. Você deseja fazer alterações que proporcionam o maior impacto e podem ser testadas facilmente.
* **Pequenas alterações podem ter um impacto significativo.** Nem todas as alterações que você testar precisam ser drásticas para terem um impacto significativo em sua empresa. Esteja sempre aberto a fazer pequenas alterações, mas muito importantes.

## Metodologias suportadas {#section-1071adaf54c64ba9bc5ef228c4a23635}

Vários tipos de experimentos com muitas metas diferentes podem ser executados usando o Site. A lista a seguir fornece alguns exemplos:

* Alteração de páginas, conteúdo e processos de site para melhorar as taxas de conversão.
* Alterar campanhas de marketing, promoções, vendas cruzadas e vendas adicionais para aumentar a receita.
* Várias horas de carregamento de página para entender a qualidade do serviço do cliente e o valor real do desempenho da infraestrutura.

Para atingir essas metas, o Site oferece suporte aos seguintes tipos de metodologias para experimentação e teste controlados:

* **Substituição de página:** Substitua o URL estático X por um URL estático Y. Essa metodologia é de uso limitado em um ambiente dinâmico.
* **Substituição dinâmica de URI:** essa é uma variante de Substituição de página que substitui a página estática X pela página dinâmica Y para renderizar o conteúdo dinâmico.
* **Substituição de objeto:** Substitua o objeto fixo X pelo objeto fixo Y.
* **Substituição de conteúdo:** substitua o conjunto de conteúdo X (vários objetos, páginas, tabela e assim por diante) pelo conjunto de conteúdo Y.
* **Substituição da variável de experimento:** substitua o objeto JavaScript /writeCookie_X.js pelo objeto JavaScript /writeCookie_Y.js para gravar um cookie que pode ser usado por um sistema de back-end para fornecer conteúdo específico.

>[!NOTE]
>
>Experimentos controlados são baseados na substituição do URI, não na substituição da sequência de consulta. O URI em um URL específico é destacado no seguinte exemplo:
>
>`https://www.omniture.com/index.asp?id=1`
>
>Por exemplo, em seu experimento controlado, você pode especificar que o URI do grupo de controle [!DNL index.asp] seja substituído pelo URI do grupo de teste [!DNL index2.asp] para determinar qual design de página resultaria em mais valor.
