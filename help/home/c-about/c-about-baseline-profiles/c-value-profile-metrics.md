---
description: 'null'
solution: Analytics
title: Métricas de perfil de valor
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: 662bf8fdff196814e5a11c1f5e1ae12d4d57e1db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 16%

---


# Métricas de perfil de valor{#value-profile-metrics}

| Métrica | Fórmula | Nível | Descrição |
|---|---|---|---|
| Conversão  | `Sessions[not Session_Value=#0]/Sessions` | Sessão | A porcentagem de sessões que gerou valor comercial (conforme definido pelo Business Value Model). |
| Ponto de valor | `Value/total(Value)` | Sessão | A porcentagem do valor geral que foi gerada a partir do conjunto de sessões selecionado. |
| Valor | `sum(Session_Value, Session)*0.01` | Sessão | O valor total de negócios gerado, em dólares (conforme definido pelo Business Value Model). |
| Eventos de valor | `Sessions[not Session_Value=#0]` | Sessão | A contagem de sessões que gerou valor comercial (conforme definido pelo Business Value Model). |
| Eventos de valor por Visitante | `(Value_Events/Visitors) by Visitor` | Visitante | O número médio de sessões para cada visitante que gerou valor comercial (conforme definido pelo Business Value Model). |
| Valor por Visitante | `(Value/Visitors) by Visitor` | Visitante | O valor médio de negócios gerado, em dólares, por cada visitante. |
