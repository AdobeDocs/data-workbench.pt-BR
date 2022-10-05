---
description: O parâmetro ExpCookieURL pode ser usado para testar se seu experimento controlado está funcionando corretamente.
solution: Analytics
title: Modificar o parâmetro ExpCookieURL (opcional)
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# Modificar o parâmetro ExpCookieURL (opcional){#modifying-the-expcookieurl-paramter-optional}

{{eol}}

O parâmetro ExpCookieURL pode ser usado para testar se seu experimento controlado está funcionando corretamente.

Esse parâmetro define o URL de uma página virtual que, quando solicitado, o coloca em um experimento e grupo especificado e o redireciona para a raiz do site. Daí até o fim do experimento, você faz parte do experimento e grupo especificados.

A página padrão desse parâmetro é [!DNL setcookie.htm], mas você pode usar qualquer URL virtual válido.

>[!NOTE]
>
>Esse deve ser um URL virtual e não deve ser uma página real ou parte do conteúdo existente. Não deve haver nenhum arquivo no servidor da Web no caminho especificado com o nome especificado.

A seguir, um exemplo do parâmetro ExpCookieURL :

[!DNL ExpCookieURL /setcookie.htm]
