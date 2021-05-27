---
description: As máquinas do Servidor Insight do Target que executam o Serviço de Replicação do Servidor Insight devem ser capazes de ler os arquivos de log neste servidor repetidor.
title: Configurar o controle de acesso para máquinas de direcionamento
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# Configurar o controle de acesso para máquinas de direcionamento{#configuring-access-control-for-target-machines}

As máquinas do Servidor Insight do Target que executam o Serviço de Replicação do Servidor Insight devem ser capazes de ler os arquivos de log neste servidor repetidor.

O acesso às máquinas de destino é concedido usando o arquivo [!DNL Access Control.cfg].

**Configurar o Controle de Acesso para acesso por  [!DNL Insight Server] máquinas de destino**

1. Navegue até a pasta [!DNL Access Control] no diretório em que você instalou a funcionalidade do repetidor.

   Exemplo: [!DNL D:\Adobe\Repeater\Access Control]

1. Abra [!DNL Access Control.cfg] em um editor de texto, como o Bloco de notas.
1. Crie um grupo de acesso para as máquinas [!DNL Insight Server] que devem acessar os arquivos de log neste servidor repetidor. Dê um nome a esse grupo de acesso como &quot;Metas de replicação&quot;.

   O fragmento de arquivo a seguir mostra como o grupo de acesso deve ser exibido.

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

   1. Na seção Membros , especifique o endereço IP de cada máquina.
   1. Atualize a contagem de itens para o vetor Membros para refletir o número de endereços IP de máquina inseridos.
   1. Na seção Acesso Somente Leitura , especifique o local dos dados de evento que a replicação direciona para acessar. Use barras na especificação do caminho (/). O local padrão é a pasta [!DNL Logs] no computador repetidor (/Logs/).
   1. Atualize a contagem de itens para o vetor de acesso somente leitura para refletir o número de locais inseridos.

1. Atualize o número de grupos de acesso no vetor de Grupos de controle de acesso na parte superior do arquivo para refletir a adição do novo grupo de acesso.

   ```
   Access Control Groups = vector: n items
   ```

1. Salve o arquivo.
