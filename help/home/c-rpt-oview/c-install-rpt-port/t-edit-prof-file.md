---
description: Para especificar os perfis que você deseja que estejam disponíveis no Portal de relatórios, configure o arquivo profile.xml.
solution: Analytics
title: Editar o arquivo Profiles.xml
topic: Data workbench
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Editar o arquivo Profiles.xml{#edit-the-profiles-xml-file}

Para especificar os perfis que você deseja que estejam disponíveis no Portal de relatórios, configure o arquivo profile.xml.

O [!DNL profiles.xml] arquivo reside na pasta designada para saída. Por padrão, ele reside no diretório \*PortalName*\PortalFiles\Output folder.

**Para adicionar nomes de perfil ao arquivo profile.xml**

1. Na máquina em que o IIS está sendo executado, abra o [!DNL profiles.xml] arquivo em um editor de texto, como o Bloco de notas.
1. Adicione um elemento de perfil e uma tag para cada um [!DNL Profile] em seu portal, como no exemplo a seguir:

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
