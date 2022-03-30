---
description: Depois de implantar seu experimento, você deve validar que o experimento está funcionando corretamente.
solution: Analytics
title: Validar o experimento
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# Validar o experimento{#validating-the-experiment}

Depois de implantar seu experimento, você deve validar que o experimento está funcionando corretamente.

Conforme discutido no [Modificar o parâmetro ExpCookieURL (opcional)](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf), a página especificada no parâmetro ExpCookieURL na [!DNL Sensor] o arquivo de configuração pode ser usado para se colocar em um grupo de experimentos específico.

A página virtual padrão é [!DNL /setcookie.htm], mas você deve usar o valor definido no parâmetro ExpCookieURL .

## Solicitar a página de teste {#section-8aed3b48d47f4e6c8869c0216f8781b1}

Para testar um grupo de experimentos específico para seu site, seu navegador deve ser configurado para aceitar cookies e você ainda não deve ter um cookie para esse site.

Sempre que quiser testar um novo grupo, certifique-se de limpar os cookies do site.

Para se colocar em um grupo específico em um experimento específico, solicite uma string de consulta à página de teste no seguinte formulário:

[!DNL https://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

Por exemplo:

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

Quando a solicitação de URL virtual é enviada para o servidor, [!DNL Sensor] O identifica você como um membro do grupo especificado no experimento especificado e redireciona você para a raiz do site. Agora você pode navegar até o local apropriado no site para validar se o conteúdo correto é exibido para esse experimento e grupo.

Se você digitasse o seguinte no navegador, o navegador exibiria a página inicial do site e o colocaria no grupo index2 dentro do experimento New_Homepage:

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

Quando os visitantes do grupo index2 solicitam a página inicial, o link gráfico &quot;Solicitar uma demonstração&quot; é exibido mais alto na página, como no gráfico a seguir:

![](assets/TestPage.png)
