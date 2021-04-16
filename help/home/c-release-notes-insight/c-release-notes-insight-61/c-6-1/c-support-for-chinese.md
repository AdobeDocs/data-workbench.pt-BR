---
description: O aplicativo cliente do Data Workbench agora é compatível com o idioma chinês simplificado.
title: Localização simplificada em chinês
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 1%

---


# Localização simplificada do chinês{#simplified-chinese-localization}

O aplicativo cliente do Data Workbench agora é compatível com o idioma chinês simplificado.

**Para instalar o idioma chinês** simplificado:

Antes de configurar [!DNL Insight.exe] e arquivos de suporte, você deve sair do aplicativo cliente.

1. Crie um atalho que passe na configuração da linha de comando para o arquivo [!DNL insight.exe].

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] para suportar caracteres de fonte de um e dois bytes.

   Atualmente, o Data Workbench oferece suporte para inglês e chinês simplificado. Você pode selecionar fontes para oferecer suporte a ambos os idiomas:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Reiniciar [!DNL Insight.exe].

