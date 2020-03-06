---
description: O aplicativo cliente da análise de big data agora suporta chinês simplificado.
solution: Analytics
title: Localização simplificada em chinês
topic: Data workbench
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Localização simplificada em chinês{#simplified-chinese-localization}

O aplicativo cliente da análise de big data agora suporta chinês simplificado.

**Para instalar o chinês** simplificado:

Antes de configurar [!DNL Insight.exe] e suportar arquivos, você deve sair do aplicativo cliente.

1. Crie um atalho que passe na configuração da linha de comando para o [!DNL insight.exe] arquivo.

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] para suportar caracteres de fonte de byte único e duplo.

   Atualmente, a análise de big data suporta inglês e chinês simplificado. Você pode selecionar fontes para suportar ambos os idiomas:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Reiniciar [!DNL Insight.exe].

