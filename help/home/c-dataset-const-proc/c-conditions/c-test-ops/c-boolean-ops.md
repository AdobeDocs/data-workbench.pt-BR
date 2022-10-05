---
description: As operações booleanas combinam os resultados das operações de teste, que funcionam como filhos das operações booleanas.
title: Operações booleanas
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Operações booleanas{#boolean-operations}

{{eol}}

As operações booleanas combinam os resultados das operações de teste, que funcionam como filhos das operações booleanas.

Para obter informações sobre as operações de teste, consulte [Operações de teste](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Ao definir uma [!DNL boolean] , você pode definir zero ou mais filhos para a operação.

**Para adicionar uma condição filho a uma operação Booleana**

1. Clique com o botão direito do mouse no nome ou no número correspondente à variável [!DNL Boolean] operação.
1. Clique em **[!UICONTROL Add new child]** e escolha um dos tipos de condição disponíveis para adicionar.
1. Repita as etapas 1 e 2 até ter adicionado todas as condições secundárias desejadas para a [!DNL Boolean] operação.

   >[!NOTE]
   >
   >Ao clicar com o botão direito do mouse no nome ou no número correspondente a um [!DNL Boolean] , você verá a variável [!DNL Add new sibling] opção de menu. Um irmão é outra condição na mesma posição relativa na hierarquia de condição que a [!DNL Boolean] que você clicou com o botão direito do mouse. Adicionar um novo irmão para um [!DNL Boolean] é o mesmo que adicionar uma nova condição clicando com o botão direito do mouse no [!DNL Condition] ou [!DNL Log Entry Condition] parâmetro.

**Para remover uma condição filho de uma operação Booleana:**

1. Clique com o botão direito do mouse no nome da condição filho ou no número correspondente à condição filho que você deseja remover do [!DNL Boolean] operação.
1. Clique em **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, onde number é o número correspondente à condição filho que você deseja remover.

Esta seção discute as seguintes condições:

* [E](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Not](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [Ou](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## E {#section-a14dba4b07cc4ab9aeb20868f773db7c}

O [!DNL And] pode ter zero ou mais condições-filho e retorna true quando nenhum de seus nós-filho retornar false.

O [!DNL And] forma a operação raiz de todos os testes de condição no servidor do Data Workbench. Se a variável [!DNL And] não contém filhos, a condição é avaliada como true e a operação associada continua. É por isso que as ações que têm somente a variável [!DNL And] condição como o teste de condição sempre é executado e por que é usado como a raiz para todos os testes de condição.

Este exemplo mostra como uma [!DNL And] é usada para garantir que a variável [!DNL Copy] a transformação ocorre quando somente a data da entrada do log ocorreu em 2006 e a página solicitada foi [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Not {#section-7e48b61266aa43ecbc48b979bf5e939b}

O [!DNL Neither] pode ter zero ou mais condições-filho e retornará false se qualquer uma de suas condições-filho for avaliada como true. Se a variável [!DNL Neither] não contém filhos, nenhum de seus filhos pode retornar verdadeiro. Como resultado, a variável [!DNL Neither] condição avalia como verdadeiro.

O exemplo a seguir mostra um [!DNL Neither] condição com dois [!DNL Range] como seus filhos. Conforme definido, a variável [!DNL Neither] condição exclui entradas de log que ocorreram entre 1º de janeiro de 2007 e 10 de janeiro de 2007 ou durante o período de 12 de janeiro de 2007 a 14 de janeiro de 2007. Essa condição pode ser usada como [!DNL Log Entry Condition] para eliminar transações de um conjunto de dados durante períodos em que havia um problema conhecido com os dados coletados.

![](assets/cfg_Condition_NeitherCondition.png)

## Ou {#section-a3aa0f56b6234f2680fa81939228326b}

O [!DNL Or] pode ter zero ou mais condições-filho e retornará true se pelo menos uma de suas condições-filho for avaliada como true. Se a variável [!DNL Or] não contém filhos, nenhum de seus filhos pode retornar verdadeiro. Como resultado, a variável [!DNL Or] A condição é avaliada como false.

Este exemplo mostra o [!DNL Or] com uma [!DNL String Match] e uma [!DNL Range] como seus filhos. O [!DNL Or] A condição só será atendida se a entrada do log tiver o valor [!DNL x-hasproblem] valor definido como sim ou a entrada de log ocorreu durante o intervalo de tempo de 1º de janeiro de 2007, a 10 de janeiro de 2007.

![](assets/cfg_Condition_OrCondition.png)
