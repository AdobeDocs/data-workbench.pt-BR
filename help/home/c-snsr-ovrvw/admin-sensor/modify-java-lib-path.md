---
description: Instruções para adicionar o visual_sciences.dll ao caminho da biblioteca java Tomcat.
title: Modificar o caminho da biblioteca Java
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
exl-id: bd853d95-3f44-4860-9965-c3210ec4adcf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 12%

---

# Modificar o caminho da biblioteca Java{#modify-the-java-library-path}

{{eol}}

Instruções para adicionar o visual_sciences.dll ao caminho da biblioteca java Tomcat.

1. No servidor Windows, navegue até o diretório de instalação do Tomcat. (Tomcat > bin)
1. Na pasta bin, execute Tomcat9w.exe (gerenciador de serviços daemon comum).

Na guia Java , em opções de Java, adicione uma nova linha:

```
-Djava.library.path=C:\Sensor directory
```

Onde C:\Sensor directory is the directory containing the visual_sciences.dll arquivo.
