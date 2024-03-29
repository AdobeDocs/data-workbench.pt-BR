---
description: Para se conectar a um servidor do Data Workbench, o Servidor de Relatórios deve ter permissão para acessar esse servidor.
title: Ativar o acesso ao servidor do Data Workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Ativar o acesso ao servidor do Data Workbench{#enabling-access-to-the-data-workbench-server}

{{eol}}

Para se conectar a um servidor do Data Workbench, o Servidor de Relatórios deve ter permissão para acessar esse servidor.

Você concede acesso a um servidor do Data Workbench adicionando o nome comum do Servidor de Relatório (como atribuído no certificado digital do Servidor de Relatório) ao arquivo de controle de acesso do servidor.

>[!NOTE]
>
>Ao trabalhar em um ambiente em cluster, o Servidor de Relatórios deve ser configurado para acessar o servidor do Data Workbench principal para evitar problemas de sincronização. No Data Workbench, é possível exibir informações sobre servidores de processamento em seu cluster usando o [!DNL Related Servers] item de menu na [!DNL Servers Manager]. Para obter mais informações sobre o [!DNL Servers Manager], consulte o capítulo Interfaces administrativas do *Guia do usuário do Data Workbench*.

O procedimento a seguir descreve como adicionar manualmente o Report Server ao arquivo de controle de acesso em um servidor do Data Workbench. Para atualizar o arquivo de controle de acesso dessa maneira, você deve ter acesso ao sistema de arquivos na máquina em que o servidor do Data Workbench está instalado.

Você também pode atualizar o arquivo de controle de acesso do servidor usando o [!DNL Server Files Manager] no Data Workbench. Para fazer isso, o cliente do Data Workbench deve ter privilégios administrativos no servidor.

Para obter mais informações sobre o [!DNL Server Files Manager], consulte o capítulo Interfaces administrativas do *Guia do usuário do Data Workbench*.

**Para configurar o acesso a um servidor do Data Workbench**

1. Navegue até a pasta Controle de acesso no diretório em que você instalou o servidor do Data Workbench (InsightServer64.exe).

   Exemplo: [!DNL C:\Adobe\Server\Access Control]

1. Abrir [!DNL Access Control.cfg] em um editor de texto como o Bloco de notas.
1. Localize a variável [!DNL Report Server AccessGroup] e adicionar [!DNL Report Server’s] nome comum para esse grupo, como destacado no fragmento de arquivo a seguir. (Digite o nome comum exatamente como ele aparece em [!DNL Report Server’s] certificado digital.)

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
