---
description: O produto do painel requer uma licença fornecida pelo Adobe ClientCare.
title: Adicionar chave de licença do painel
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# Adicionar chave de licença do painel{#add-dashboard-license-key}

O produto do painel requer uma licença fornecida pelo Adobe ClientCare.

1. Abra **[!UICONTROL SQL Management Studio]** como um Administrador.
1. Abra o banco de dados criado pelo painel (por exemplo, thinclientdb).
1. Clique com o botão direito do mouse na tabela **[!UICONTROL Configuration]** e clique em **[!UICONTROL Edit Top 200 Rows]**.
1. Encontre o campo **[!UICONTROL licenseKey]** e insira a chave fornecida pelo Adobe ClientCare na coluna **[!UICONTROL Value]** .
1. Reinicie o **[!UICONTROL Application Pool]** no **[!UICONTROL IIS Manager Console]**.
