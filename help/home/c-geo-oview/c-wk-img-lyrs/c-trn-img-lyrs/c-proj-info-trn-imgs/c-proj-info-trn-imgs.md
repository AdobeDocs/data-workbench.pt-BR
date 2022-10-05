---
description: A Geografia do Data Workbench suporta projeções de latitude e projeções do Universal Transverse Mercator (UTM) para todas as fontes de camada de imagem do terreno.
title: Especificar informações de projeção para imagens do terreno
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%

---

# Especificar informações de projeção para imagens do terreno{#specifying-projection-information-for-terrain-images}

{{eol}}

A Geografia do Data Workbench suporta projeções de latitude e projeções do Universal Transverse Mercator (UTM) para todas as fontes de camada de imagem do terreno.

As informações de projeção são necessárias para bitmaps brutos não projetados e imagens gerais, não projetadas. Você pode especificar informações de projeção para imagens com informações de projeção incorporadas, embora isso geralmente não seja necessário, pois os parâmetros da projeção são determinados automaticamente a partir de dados geodésicos incorporados na própria imagem. As seções a seguir fornecem detalhes sobre a especificação desses formatos de projeção na [!DNL Terrain Images.cfg] arquivo.
