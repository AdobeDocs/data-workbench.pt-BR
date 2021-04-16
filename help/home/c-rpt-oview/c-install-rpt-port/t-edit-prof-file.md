---
description: Para especificar os perfis que deseja que estejam disponíveis no portal de relatórios, é necessário configurar o arquivo profiles.xml.
title: Editar o arquivo Profiles.xml
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# Editar o arquivo Profiles.xml{#edit-the-profiles-xml-file}

Para especificar os perfis que deseja que estejam disponíveis no portal de relatórios, é necessário configurar o arquivo profiles.xml.

O arquivo [!DNL profiles.xml] reside na pasta designada para saída. Por padrão, ele reside no \*PortalName*\PortalFiles\Output folder.

**Para adicionar nomes de perfil ao arquivo profiles.xml**

1. Na máquina em que o IIS está sendo executado, abra o arquivo [!DNL profiles.xml] em um editor de texto, como o Bloco de notas.
1. Adicione um elemento de perfil e uma tag para cada [!DNL Profile] no portal, como no exemplo a seguir:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. Salve e feche o arquivo.
