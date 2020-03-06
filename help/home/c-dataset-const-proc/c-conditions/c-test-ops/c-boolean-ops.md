---
description: As operações Booleanas combinam os resultados das operações de teste, que funcionam como filhos das operações booleanas.
solution: Analytics
title: Operações Booleanas
topic: Data workbench
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Operações Booleanas{#boolean-operations}

As operações Booleanas combinam os resultados das operações de teste, que funcionam como filhos das operações booleanas.

Para obter informações sobre as operações de teste, consulte [Testar operações](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Ao definir uma [!DNL boolean] operação, você pode definir zero ou mais filhos para a operação.

**Para adicionar uma condição filho a uma operação Booleana**

1. Clique com o botão direito do mouse no nome ou no número correspondente à [!DNL Boolean] operação.
1. Clique **[!UICONTROL Add new child]** e escolha um dos tipos de condição disponíveis para adicionar.
1. Repita as etapas 1 e 2 até ter adicionado todas as condições filho desejadas para a [!DNL Boolean] operação.

   >[!NOTE]
   >
   >Ao clicar com o botão direito do mouse no nome ou no número correspondente a uma [!DNL Boolean] operação, você verá a opção de [!DNL Add new sibling] menu. Um irmão é outra condição na mesma posição relativa na hierarquia da condição que a [!DNL Boolean] operação em que você clicou com o botão direito do mouse. Adicionar um novo irmão para uma [!DNL Boolean] operação é o mesmo que adicionar uma nova condição clicando com o botão direito do mouse no parâmetro [!DNL Condition] ou [!DNL Log Entry Condition] .

**Para remover uma condição filho de uma operação Booleana:**

1. Clique com o botão direito do mouse no nome da condição filho ou no número correspondente à condição filho que você deseja remover da [!DNL Boolean] operação.
1. Clique em **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, onde number é o número correspondente à condição filho que você deseja remover.

Esta seção aborda as seguintes condições:

* [E](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [nor](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [Ou](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## E {#section-a14dba4b07cc4ab9aeb20868f773db7c}

A [!DNL And] condição pode ter zero ou mais condições-filho e retorna true quando nenhum de seus nós-filho retorna false.

A [!DNL And] condição forma a operação raiz de todos os testes de condição no servidor da análise de big data. Se a [!DNL And] condição não contiver filhos, a condição será avaliada como true e a operação associada continuará. É por isso que as ações que têm somente a [!DNL And] condição como teste de condição sempre são executadas e por que são usadas como a raiz para todos os testes de condição.

Este exemplo mostra como uma [!DNL And] condição é usada para garantir que a [!DNL Copy] transformação ocorra quando apenas a data da entrada do log ocorreu no ano de 2006 e que a página solicitada foi [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Neither {#section-7e48b61266aa43ecbc48b979bf5e939b}

A [!DNL Neither] condição pode ter zero ou mais condições-filho e retorna false se qualquer uma de suas condições-filho for avaliada como true. Se a [!DNL Neither] condição não contiver filhos, nenhum de seus filhos poderá retornar verdadeiro. Como resultado, a [!DNL Neither] condição avalia como verdadeira.

O exemplo a seguir mostra uma [!DNL Neither] condição com duas [!DNL Range] condições como filhos. Conforme definido, a [!DNL Neither] condição exclui as entradas de log que ocorreram entre 1º de janeiro de 2007 e 10 de janeiro de 2007 ou durante o período de 12 de janeiro de 2007 até 14 de janeiro de 2007. Essa condição pode ser usada como [!DNL Log Entry Condition] a eliminação de transações de um conjunto de dados durante períodos em que se sabe que houve um problema com os dados coletados.

![](assets/cfg_Condition_NeitherCondition.png)

## Ou {#section-a3aa0f56b6234f2680fa81939228326b}

A [!DNL Or] condição pode ter zero ou mais condições-filho e retorna true se pelo menos uma de suas condições-filho for avaliada como true. Se a [!DNL Or] condição não contiver filhos, nenhum de seus filhos poderá retornar verdadeiro. Como resultado, a [!DNL Or] condição resulta em falso.

Este exemplo mostra a [!DNL Or] condição com uma [!DNL String Match] condição e uma [!DNL Range] condição como filhos. A [!DNL Or] condição é atendida somente se a entrada do registro tiver o [!DNL x-hasproblem] valor definido como yes ou se a entrada do registro tiver ocorrido durante o intervalo de tempo entre 1º de janeiro de 2007 e 10 de janeiro de 2007.

![](assets/cfg_Condition_OrCondition.png)

