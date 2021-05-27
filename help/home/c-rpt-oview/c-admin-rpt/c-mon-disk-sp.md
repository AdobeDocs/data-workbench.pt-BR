---
description: Você deve monitorar regularmente o espaço em disco disponível para que todas as máquinas do Servidor de Relatório continuem a funcionar no mais alto nível possível.
title: Monitorar o espaço em disco
uuid: 590c8239-d20e-470e-b633-7785b75daaa6
exl-id: 0debd601-494f-4d4e-9452-c4d32678dc95
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 3%

---

# Monitorar o espaço em disco{#monitoring-disk-space}

Você deve monitorar regularmente o espaço em disco disponível para que todas as máquinas do Servidor de Relatório continuem a funcionar no mais alto nível possível.

Cada máquina [!DNL Report Server] armazena os seguintes tipos de dados:

* Dados do sistema operacional
* Dados do relatório
* Dados do sistema

>[!NOTE]
>
>Os consultores do Adobe podem avaliar seu cenário de uso para ajudá-lo a projetar a quantidade de armazenamento de dados que seu aplicativo de software Adobe gera e requer. Para solicitar essa avaliação, entre em contato com os Serviços de consultoria da Adobe.

* [Monitorar o espaço de dados do relatório](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-ad0a63f3a6824e68acd675da0b6c5c23)
* [Backup de dados do sistema operacional, relatório e sistema](../../../home/c-rpt-oview/c-admin-rpt/c-mon-disk-sp.md#section-b5efb132ca5d4ee69a8608f9b4ab245b)

## Monitorar o espaço de dados de relatório {#section-ad0a63f3a6824e68acd675da0b6c5c23}

**Frequência recomendada:** a cada 5-10 minutos

Certifique-se de fornecer espaço em disco suficiente para acomodar seus relatórios na pasta [!DNL Reports] dentro do diretório de instalação [!DNL Report].

## Backup de dados do sistema operacional, relatório e sistema {#section-b5efb132ca5d4ee69a8608f9b4ab245b}

**Frequência recomendada:** diariamente

O backup dos dados do sistema operacional, do sistema e dos relatórios deve ser feito regularmente e diligentemente usando os sistemas normais de backup e recuperação de desastres da sua empresa.
