---
description: Instruções para adicionar o visual_sciences.dll ao caminho da biblioteca java do Tomcat.
title: Modificar o caminho da biblioteca Java
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificar o caminho da biblioteca Java{#modify-the-java-library-path}

Instruções para adicionar o visual_sciences.dll ao caminho da biblioteca java do Tomcat.

1. No servidor Windows, navegue até o diretório de instalação do Tomcat. (Tomcat > bin)
1. Em bin folder, execute Tomcat9w.exe (Common daemon service manager).

Na guia Java, em Opções Java, adicione uma nova linha:

```
-Djava.library.path=C:\Sensor directory
```

Onde o arquivo C:\Sensor directory is the directory containing the visual_sciences.dll.
