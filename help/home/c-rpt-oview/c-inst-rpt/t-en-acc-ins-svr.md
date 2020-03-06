---
description: Para se conectar a um servidor de análise de big data, o Servidor de relatórios deve ter permissão para acessar esse servidor.
solution: Analytics
title: Ativando o Acesso ao Servidor do Análise de big data
topic: Data workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ativando o Acesso ao Servidor do Análise de big data{#enabling-access-to-the-data-workbench-server}

Para se conectar a um servidor de análise de big data, o Servidor de relatórios deve ter permissão para acessar esse servidor.

Você concede acesso a um servidor de análise de big data adicionando o nome comum do Servidor de relatórios (conforme atribuído no certificado digital do Servidor de relatórios) ao arquivo de controle de acesso do servidor.

>[!NOTE]
>
>Ao trabalhar em um ambiente clusterizado, o Servidor de Relatório deve ser configurado para acessar o servidor da análise de big data mestre para evitar problemas de sincronização. Na análise de big data, você pode exibir informações sobre o processamento de servidores em seu cluster usando o item de [!DNL Related Servers] menu na [!DNL Servers Manager]. Para obter mais informações sobre o [!DNL Servers Manager], consulte o capítulo Interfaces administrativas do Guia *do usuário da Análise de* big data.

O procedimento a seguir descreve como adicionar manualmente o Servidor de relatórios ao arquivo de controle de acesso em um servidor de análise de big data. Para atualizar o arquivo de controle de acesso dessa forma, é necessário ter acesso ao sistema de arquivos na máquina em que o servidor do análise de big data está instalado.

Você também pode atualizar o arquivo de controle de acesso do servidor usando o [!DNL Server Files Manager] em análise de big data. Para fazer isso, o cliente da análise de big data deve ter privilégios administrativos no servidor.

Para obter mais informações sobre o [!DNL Server Files Manager], consulte o capítulo Interfaces administrativas do Guia *do usuário da Análise de* big data.

**Para configurar o acesso a um servidor de análise de big data**

1. Navegue até a pasta Controle de acesso no diretório em que você instalou o servidor da análise de big data (InsightServer64.exe).

   Exemplo: [!DNL C:\Adobe\Server\Access Control]

1. Abra [!DNL Access Control.cfg] em um editor de texto, como o Bloco de notas.
1. Localize o arquivo [!DNL Report Server AccessGroup] e adicione um nome [!DNL Report Server’s] comum a esse grupo, conforme destacado no seguinte fragmento de arquivo. (Digite o nome comum exatamente como aparece no certificado [!DNL Report Server’s] digital.)

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. Salve o arquivo.
