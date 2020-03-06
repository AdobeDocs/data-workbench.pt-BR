---
description: O parâmetro ExpCookieURL pode ser usado para testar se seu experimento controlado está funcionando corretamente.
solution: Insight,Analytics
title: Modificando o parâmetro ExpCookieURL (opcional)
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificando o parâmetro ExpCookieURL (opcional){#modifying-the-expcookieurl-paramter-optional}

O parâmetro ExpCookieURL pode ser usado para testar se seu experimento controlado está funcionando corretamente.

Esse parâmetro define o URL de uma página virtual que, quando solicitado, coloca você em um experimento e grupo especificados e o redireciona para a raiz do site. Daquele ponto até o final do experimento, você faz parte do experimento e grupo especificados.

A página padrão desse parâmetro é [!DNL setcookie.htm], mas você pode usar qualquer URL virtual válido.

>[!NOTE]
>
>Esse deve ser um URL virtual e não deve ser uma página real ou um conteúdo existente. Não deve haver nenhum arquivo no servidor Web no caminho especificado com o nome especificado.

Veja a seguir um exemplo do parâmetro ExpCookieURL:

[!DNL ExpCookieURL /setcookie.htm]
