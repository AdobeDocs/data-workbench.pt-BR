---
description: A análise de big data oferece suporte a projeções de latitude e longitude e a projeções Universal Transverse Mercator (UTM) para todas as fontes de camada de imagem do terreno.
solution: Analytics
title: Especificação de informações de projeção para imagens de terreno
topic: Data workbench
uuid: 4a476192-e749-4187-b64e-9794f39b0019
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Especificação de informações de projeção para imagens de terreno{#specifying-projection-information-for-terrain-images}

A análise de big data oferece suporte a projeções de latitude e longitude e a projeções Universal Transverse Mercator (UTM) para todas as fontes de camada de imagem do terreno.

As informações de projeção são necessárias para bitmaps brutos não projetados e imagens gerais, não projetadas. Você pode especificar informações de projeção para imagens com informações de projeção incorporadas, embora geralmente não sejam necessárias, pois os parâmetros da projeção são determinados automaticamente a partir de dados geodésicos incorporados à própria imagem. As seções a seguir fornecem detalhes sobre como especificar esses formatos de projeção no [!DNL Terrain Images.cfg] arquivo.
