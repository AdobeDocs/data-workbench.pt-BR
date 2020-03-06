---
description: O produto do painel requer uma licença fornecida pelo Adobe ClientCare.
solution: Analytics
title: Adicionar chave de licença do painel
topic: Data workbench
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Adicionar chave de licença do painel{#add-dashboard-license-key}

O produto do painel requer uma licença fornecida pelo Adobe ClientCare.

1. Open **[!UICONTROL SQL Management Studio]** as an Administrator.
1. Abra o banco de dados criado pelo painel (por exemplo, thinclientdb).
1. Clique com o botão direito do mouse na **[!UICONTROL Configuration]** tabela e clique em **[!UICONTROL Edit Top 200 Rows]**.
1. Localize o **[!UICONTROL licenseKey]** campo e insira a chave fornecida pelo Adobe ClientCare na **[!UICONTROL Value]** coluna.
1. Reinicie o **[!UICONTROL Application Pool]** no **[!UICONTROL IIS Manager Console]**.
