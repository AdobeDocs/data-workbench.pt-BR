---
description: Depois de implantar seu experimento, você deve validar se o experimento está funcionando corretamente.
solution: Analytics,Analytics
title: Validar o experimento
topic: Data workbench
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---


# Validar o experimento{#validating-the-experiment}

Depois de implantar seu experimento, você deve validar se o experimento está funcionando corretamente.

Conforme discutido em [Modificação do parâmetro ExpCookieURL (Opcional)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf), a página especificada no parâmetro ExpCookieURL no arquivo de [!DNL Sensor] configuração pode ser usada para se colocar em um grupo de experimentos específico.

A página virtual padrão é [!DNL /setcookie.htm], mas você deve usar o valor definido no parâmetro ExpCookieURL.

## Solicitação da página de teste {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Para testar um grupo de experimentos específico para seu site, seu navegador deve estar configurado para aceitar cookies e você já não deve ter um cookie para este site.

Sempre que quiser testar um novo grupo, certifique-se de limpar os cookies do site.

Para se colocar em um grupo específico em um experimento específico, solicite à página de teste uma string de query no seguinte formulário:

[!DNL http://] *&lt;[!DNL sitename/?Experiment Name=Group Name]>*

Por exemplo:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Quando a solicitação de URL virtual é enviada para o servidor, o [!DNL Sensor] identifica como um membro do grupo especificado no experimento especificado e o redireciona para a raiz do site. Agora você pode navegar até o local apropriado no site para validar se o conteúdo correto é exibido para esse experimento e grupo.

Se você digitar o seguinte no seu navegador, o navegador exibirá o home page do site e o colocará no grupo index2 no experimento New_Homepage:

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

Quando visitantes no grupo index2 solicitam o home page, o link gráfico &quot;Solicitar uma demonstração&quot; é exibido acima na página, como no seguinte gráfico:

![](assets/TestPage.png)

