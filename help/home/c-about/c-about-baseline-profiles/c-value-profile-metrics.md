---
description: 'null'
solution: Analytics
title: Métricas de perfil de valor
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Métricas de perfil de valor{#value-profile-metrics}

| Métrica | Fórmula | Nível | Descrição |
|---|---|---|---|
| Conversão | [!DNL[Sessões sem Session_Value=#0]/Sessões] | Sessão | A porcentagem de sessões que gerou valor comercial (conforme definido pelo Business Value Model). |
| Ponto de valor | [!DNL Value/total(Value)] | Sessão | A porcentagem do valor geral que foi gerada a partir do conjunto de sessões selecionado. |
| Valor | [!DNL sum(Session_Value, Session)*0.01] | Sessão | O valor total de negócios gerado, em dólares (conforme definido pelo Business Value Model). |
| Eventos de valor | [!DNL[Sessionsnot Session_Value=#0]] | Sessão | A contagem de sessões que gerou valor comercial (conforme definido pelo Business Value Model). |
| Eventos de valor por visitante | [!DNL (Value_Events/Visitors) by Visitor] | Visitante | O número médio de sessões para cada visitante que gerou valor comercial (conforme definido pelo Business Value Model). |
| Valor por visitante | [!DNL (Value/Visitors) by Visitor] | Visitante | O valor médio de negócios gerado, em dólares, por cada visitante. |
