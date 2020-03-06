---
description: Os resultados dos testes devem ser claros e significativos para que você se sinta confiante em tomar decisões de um grande valor com base nesses resultados.
solution: Insight,Analytics
title: O Que Devo Testar?
topic: Data workbench
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# O Que Devo Testar?{#what-should-i-test}

Os resultados dos testes devem ser claros e significativos para que você se sinta confiante em tomar decisões de um grande valor com base nesses resultados.

Embora seja possível testar vários layouts de página com [!DNL Sensor] e Site, a Adobe sugere que você se concentre em testar iniciativas comerciais estratégicas de alto valor ou funcionalidades de site novas ou reprojetadas que atendam às metas definidas para seu site, bem como para sua empresa. Você pode testar problemas como melhores garantias de preço, funcionalidade de personalização, ofertas do mercado (por exemplo, pacotes ou pacotes), design criativo e processos de aplicativo.

Os seguintes conceitos são mais importantes ao desenvolver seu experimento controlado:

* **Entenda as mudanças certas a serem feitas.** Isso requer alguma pesquisa sobre como seu site funciona e os processos de negócios subjacentes ao site de front-end. Você deseja fazer alterações que proporcionem o maior impacto e possam ser testadas facilmente.
* **Pequenas mudanças podem ter impacto significativo.** Nem todas as mudanças que você testa precisam ser drásticas para terem um impacto significativo nos seus negócios. Esteja sempre aberto a fazer mudanças pequenas, mas muito importantes.

## Metodologias suportadas {#section-1071adaf54c64ba9bc5ef228c4a23635}

Muitos tipos de experimentos com muitas metas diferentes podem ser realizados usando o Site. A lista a seguir fornece alguns exemplos:

* Alteração de páginas, conteúdo e processos de site para melhorar as taxas de conversão.
* Alterar campanhas de marketing, promoções, vendas cruzadas e vendas agregadas para aumentar a receita.
* Diferentes tempos de carregamento de página para entender a qualidade de serviço do cliente e o valor real do desempenho da infraestrutura.

Para atingir essas metas, o Site oferece suporte aos seguintes tipos de metodologias para experimentação e teste controlados:

* **Substituição de página:** Substitua o URL X estático pelo URL estático Y. Esta metodologia é de utilização limitada num ambiente dinâmico.
* **Substituição dinâmica de URI:** Essa é uma variante da Substituição de página que substitui a página estática X pela página dinâmica Y para renderizar o conteúdo dinâmico.
* **Substituição de objeto:** Substitua o objeto fixo X pelo objeto fixo Y.
* **Substituição de conteúdo:** Substitua o conjunto de conteúdo X (vários objetos, páginas, tabela e assim por diante) pelo conjunto de conteúdo Y.
* **Substituição da variável de experimento:** Substitua o objeto JavaScript /writeCookie_X.js pelo objeto JavaScript /writeCookie_Y.js para gravar um cookie que possa ser usado por um sistema back-end para fornecer conteúdo específico.

>[!NOTE]
>
>Os experimentos controlados são baseados na substituição de URI, e não na substituição de sequências de consulta. O URI dentro de um URL específico é destacado no seguinte exemplo:
>
>`http://www.omniture.com/index.asp?id=1`
>
>Por exemplo, em seu experimento controlado, você pode especificar que o URI do grupo de controle [!DNL index.asp] seja substituído pelo URI do grupo de teste [!DNL index2.asp] para determinar qual design de página resultaria em mais valor.
