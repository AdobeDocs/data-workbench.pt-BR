---
description: Siga estas etapas para atualizar para o Data Workbench v6.5.
title: Atualização da versão 6.4 para 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
exl-id: bcfd1ab1-2fb8-4bcd-b6c9-329143274ca4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 2%

---

# Atualização da versão 6.4 para 6.5{#upgrading-to}

{{eol}}

Siga estas etapas para atualizar para o Data Workbench v6.5.

## Requisitos de atualização e Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Siga estes requisitos e recomendações ao atualizar para a Data Workbench 6.5.

* Alterações na **[!DNL Components for Processing Servers\Communications.cfg]** Esse arquivo requer que você atualize esse arquivo para a versão DWB 6.5. O *SourceListServer*, *SegmentExportServer* e *NormalizarServidor* as entradas foram removidas. ( Os DPUs não devem estar em execução *sourcelist*, *exportação de segmento* ou *normalizar servidores*. )

* Correlação de corda, Correlação de matriz, Corda de associação, Matriz de associação, Pontuação de propensão e Visualizações de Melhor Ajuste de atribuição agora são visualizações de várias etapas.

   Quando há mais de uma visualização de várias etapas em um espaço de trabalho, o Servidor de relatórios não consegue gerar relatórios por padrão com o erro:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Evite esse erro atualizando seu [!DNL ReportServer.cfg] ou adicione esta linha ao seu arquivo existente na *Relatório* seção.

   ```
   Max Multipass Per Slice = int: n
   ```

   onde n é o número máximo de visualizações de multi-pass suportadas pelo Servidor de relatórios em um espaço de trabalho.
