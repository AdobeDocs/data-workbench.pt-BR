---
description: Para especificar os perfis que deseja que estejam disponíveis no portal de relatórios, é necessário configurar o arquivo profiles.xml.
title: Editar o arquivo Profiles.xml
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# Editar o arquivo Profiles.xml{#edit-the-profiles-xml-file}

{{eol}}

Para especificar os perfis que deseja que estejam disponíveis no portal de relatórios, é necessário configurar o arquivo profiles.xml.

O [!DNL profiles.xml] O arquivo reside na pasta designada para saída. Por padrão, ele reside na pasta \*PortalName*\PortalFiles\Output .

**Para adicionar nomes de perfil ao arquivo profiles.xml**

1. Na máquina em que o IIS está em execução, abra o [!DNL profiles.xml] em um editor de texto, como o Bloco de notas.
1. Adicionar um elemento de perfil e uma tag para cada [!DNL Profile] no portal, como no exemplo a seguir:

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
