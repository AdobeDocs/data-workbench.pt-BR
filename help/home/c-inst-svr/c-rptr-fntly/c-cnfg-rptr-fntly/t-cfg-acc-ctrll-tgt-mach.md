---
description: As máquinas do Público alvo Insight Server que executam o Insight Server Replication Service devem ser capazes de ler os arquivos de log neste servidor repetidor.
solution: Analytics
title: Configurar o controle de acesso para máquinas de direcionamento
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---


# Configurar o controle de acesso para máquinas de direcionamento{#configuring-access-control-for-target-machines}

As máquinas do Público alvo Insight Server que executam o Insight Server Replication Service devem ser capazes de ler os arquivos de log neste servidor repetidor.

O acesso às máquinas de público alvo é concedido usando o [!DNL Access Control.cfg] arquivo.

**Para configurar o Controle de acesso para acesso por máquinas de público alvo[!DNL Insight Server]**

1. Navegue até a [!DNL Access Control] pasta no diretório onde você instalou a funcionalidade do repetidor.

   Exemplo: [!DNL D:\Adobe\Repeater\Access Control]

1. Abra [!DNL Access Control.cfg] em um editor de texto, como o Bloco de notas.
1. Crie um grupo de acesso para as [!DNL Insight Server] máquinas que devem acessar os arquivos de registro neste servidor repetidor. Dê um nome a esse grupo de acesso como &quot;Públicos alvos de replicação&quot;.

   O fragmento de arquivo a seguir mostra a aparência do grupo de acesso.

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. Na seção Membros, especifique o endereço IP para cada máquina.
   1. Atualize a contagem de itens do vetor Membros para refletir o número de endereços IP do computador inseridos.
   1. Na seção Acesso somente leitura, especifique o local dos dados do evento que os públicos alvos de replicação acessam. Use barras na especificação do caminho (/). O local padrão é a [!DNL Logs] pasta no computador Repeater (/Logs/).
   1. Atualize a contagem de itens do vetor de Acesso Somente Leitura para refletir o número de locais inseridos.

1. Atualize o número de grupos de acesso no vetor Grupos de Controles de acesso na parte superior do arquivo para refletir a adição do novo grupo de acesso.

   ```
   Access Control Groups = vector: n items
   ```

1. Salve o arquivo.
