---
description: As operações booleanas combinam os resultados das operações de teste, que funcionam como filhos das operações booleanas.
title: Operações booleanas
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Operações booleanas{#boolean-operations}

As operações booleanas combinam os resultados das operações de teste, que funcionam como filhos das operações booleanas.

Para obter informações sobre as operações de teste, consulte [Operações de Teste](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Ao definir uma operação [!DNL boolean], você pode definir zero ou mais filhos para a operação.

**Para adicionar uma condição filho a uma operação Booleana**

1. Clique com o botão direito do mouse no nome ou no número correspondente à operação [!DNL Boolean].
1. Clique em **[!UICONTROL Add new child]** e escolha um dos tipos de condição disponíveis para adicionar.
1. Repita as etapas 1 e 2 até ter adicionado todas as condições filho desejadas para a operação [!DNL Boolean].

   >[!NOTE]
   >
   >Ao clicar com o botão direito do mouse no nome ou no número correspondente a uma operação [!DNL Boolean], você verá a opção de menu [!DNL Add new sibling]. Um irmão é outra condição na mesma posição relativa na hierarquia de condição que a operação [!DNL Boolean] em que você clicou com o botão direito do mouse. Adicionar um novo irmão para uma operação [!DNL Boolean] é o mesmo que adicionar uma nova condição clicando com o botão direito do mouse no parâmetro [!DNL Condition] ou [!DNL Log Entry Condition].

**Para remover uma condição filho de uma operação Booleana:**

1. Clique com o botão direito do mouse no nome da condição filho ou no número correspondente à condição filho que você deseja remover da operação [!DNL Boolean].
1. Clique em **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, onde número é o número correspondente à condição filho que você deseja remover.

Esta seção discute as seguintes condições:

* [E](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Not](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [Ou](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## E {#section-a14dba4b07cc4ab9aeb20868f773db7c}

A condição [!DNL And] pode ter zero ou mais condições-filho e retorna true quando nenhum de seus nós-filho retorna false.

A condição [!DNL And] forma a operação raiz de todos os testes de condição no servidor do Data Workbench. Se a condição [!DNL And] não contiver filhos, a condição será avaliada como true e a operação associada continuará. É por isso que as ações que têm apenas a condição [!DNL And] como o teste de condição sempre são executadas e por que são usadas como a raiz para todos os testes de condição.

Este exemplo mostra como uma condição [!DNL And] é usada para garantir que a transformação [!DNL Copy] ocorra quando somente a data da entrada do log ocorreu em 2006 e que a página solicitada foi [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Nenhum {#section-7e48b61266aa43ecbc48b979bf5e939b}

A condição [!DNL Neither] pode ter zero ou mais condições-filho e retorna false se qualquer uma de suas condições-filho for avaliada como true. Se a condição [!DNL Neither] não contiver filhos, nenhum de seus filhos poderá retornar true. Como resultado, a condição [!DNL Neither] é avaliada como true.

O exemplo a seguir mostra uma condição [!DNL Neither] com duas condições [!DNL Range] como seus filhos. Conforme definido, a condição [!DNL Neither] exclui entradas de log que ocorreram entre 1º de janeiro de 2007 e 10 de janeiro de 2007 ou durante o período de 12 de janeiro de 2007 a 14 de janeiro de 2007. Essa condição pode ser usada como [!DNL Log Entry Condition] para eliminar transações de um conjunto de dados durante períodos em que havia um problema conhecido com os dados coletados.

![](assets/cfg_Condition_NeitherCondition.png)

## Ou {#section-a3aa0f56b6234f2680fa81939228326b}

A condição [!DNL Or] pode ter zero ou mais condições-filho e retornará true se pelo menos uma de suas condições-filho for avaliada como true. Se a condição [!DNL Or] não contiver filhos, nenhum de seus filhos poderá retornar true. Como resultado, a condição [!DNL Or] avalia como false.

Este exemplo mostra a condição [!DNL Or] com uma condição [!DNL String Match] e uma condição [!DNL Range] como seus filhos. A condição [!DNL Or] é atendida somente se a entrada de log tiver o valor [!DNL x-hasproblem] definido como sim ou se a entrada de log tiver ocorrido durante o intervalo de tempo compreendido entre 1º de janeiro de 2007 e 10 de janeiro de 2007.

![](assets/cfg_Condition_OrCondition.png)
