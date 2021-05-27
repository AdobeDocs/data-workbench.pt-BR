---
description: Você deve garantir que as máquinas nas quais os produtos de servidor Adobe estão instalados atendam aos requisitos mínimos do sistema, conforme definido no documento Requisitos mínimos do sistema.
title: Confirmar se os sistemas estão íntegros
uuid: 6d132865-36ab-40fc-be24-e031f356fce2
exl-id: 543f7592-dd3c-47ba-b174-5f12e9586378
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 5%

---

# Confirmar se os sistemas estão íntegros{#confirming-your-systems-are-healthy}

Você deve garantir que as máquinas nas quais os produtos de servidor Adobe estão instalados atendam aos requisitos mínimos do sistema, conforme definido no documento Requisitos mínimos do sistema.

**Frequência recomendada:** a cada 5-10 minutos

Você também deve monitorar seus sistemas de acordo com as práticas recomendadas para operar esse hardware específico, incluindo, mas não se limitando a, monitorar o seguinte:

* Uso da CPU
* Espaço em disco
* Mensagens do sistema de hardware
* Temperatura interna do sistema
* Uso de memória
* Condições de alimentação elétrica
* Desempenho e erros do controlador de disco ou RAID

O Adobe recomenda configurar sua ferramenta de gerenciamento para alertar os administradores sobre quando qualquer parâmetro de sistema em uma máquina de servidor exceder o limite definido.

Para máquinas [!DNL Insight Server], o Adobe também recomenda que você configure cada [!DNL Insight Server] para indicar quando ele atinge o limite mínimo de espaço em disco definido. Para obter mais informações sobre esses alertas, consulte [Configurar Alertas Administrativos](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa).
