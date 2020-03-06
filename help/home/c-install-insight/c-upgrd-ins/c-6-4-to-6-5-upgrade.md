---
description: Siga estas etapas para atualizar para o Análise de big data v6.5.
title: Atualização de 6.4 para 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Upgrading 6.4 to 6.5{#upgrading-to}

Siga estas etapas para atualizar para o Análise de big data v6.5.

## Requisitos e recomendações de atualização {#section-8704a9ac358246cd81233dd0982d534f}

Siga estes requisitos e recomendações ao atualizar para o Análise de big data 6.5.

* As alterações no **[!DNL Components for Processing Servers\Communications.cfg]** arquivo exigem que você atualize esse arquivo para a versão DWB 6.5. As entradas *SourceListServer*, *SegmentExportServer* e *NormalizeServer* foram removidas. (Os DPUs não devem estar executando *servidores* de origem, exportação *de* segmento ou *normalização*. )

* Correlação entre a Corda, a Matriz de correlação, a Corda de associação, a Matriz de associação, a Pontuação de propensão e as visualizações da Atribuição de melhor ajuste agora são visualizações de várias etapas.

   Quando há mais de uma visualização de várias etapas em um espaço de trabalho, o Servidor de relatórios não gera relatórios por padrão com o erro:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Evite esse erro atualizando seu [!DNL ReportServer.cfg] arquivo ou adicionando essa linha ao arquivo existente na seção *Relatório* .

   ```
   Max Multipass Per Slice = int: n
   ```

   em que n é o número máximo de visualizações de várias etapas suportadas pelo Servidor de relatórios em um espaço de trabalho.

