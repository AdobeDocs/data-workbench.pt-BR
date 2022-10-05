---
description: Métricas de perfil de valor
title: Métricas de perfil de valor
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 17%

---

# Métricas de perfil de valor{#value-profile-metrics}

{{eol}}

| Métrica | Fórmula | Nível | Descrição |
|---|---|---|---|
| Conversão | `Sessions[not Session_Value=#0]/Sessions` | Sessão | A porcentagem de sessões que geraram valor de negócios (conforme definido pelo Modelo de Valor de Negócios). |
| Pct de valor | `Value/total(Value)` | Sessão | A porcentagem do valor geral gerado pelo conjunto selecionado de sessões. |
| Valor | `sum(Session_Value, Session)*0.01` | Sessão | O valor total de negócios gerado, em dólares (conforme definido pelo Business Value Model). |
| Eventos de valor | `Sessions[not Session_Value=#0]` | Sessão | A contagem de sessões que geraram valor de negócios (conforme definido pelo Modelo de Valor de Negócios). |
| Eventos de valor por visitante | `(Value_Events/Visitors) by Visitor` | Visitante | O número médio de sessões para cada visitante que gerou valor comercial (conforme definido pelo Modelo de Valor Comercial). |
| Valor por visitante | `(Value/Visitors) by Visitor` | Visitante | O valor médio de negócios gerado, em dólares, por cada visitante. |
