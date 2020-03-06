---
description: As máquinas do Servidor do Target Insight que executam o Serviço de Replicação do Insight Server devem ser capazes de ler os arquivos de log neste servidor repetidor.
solution: Insight
title: Configurando o controle de acesso para computadores de destino
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurando o controle de acesso para computadores de destino{#configuring-access-control-for-target-machines}

As máquinas do Servidor do Target Insight que executam o Serviço de Replicação do Insight Server devem ser capazes de ler os arquivos de log neste servidor repetidor.

O acesso aos computadores de destino é concedido usando o [!DNL Access Control.cfg] arquivo.

**Para configurar o controle de acesso para acesso por[!DNL Insight Server]máquinas de destino**

1. Navegue até a [!DNL Access Control] pasta no diretório onde você instalou a funcionalidade do repetidor.

   Exemplo: [!DNL D:\Adobe\Repeater\Access Control]

1. Abra [!DNL Access Control.cfg] em um editor de texto, como o Bloco de notas.
1. Crie um grupo de acesso para as [!DNL Insight Server] máquinas que devem acessar os arquivos de registro neste servidor repetidor. Dê um nome a esse grupo de acesso, como &quot;Metas de Replicação&quot;.

       O fragmento de arquivo a seguir mostra a aparência do grupo de acesso.
       
       ```
       . . .
       6 = AccessGroup:
       Membros = vetor: N itens
     0 = string: IP:Machine0IPAddress
     1 = string: IP:Machine1IPAddress
     . . .
       N = string: IP:MachineNIPAddress
     Name = string: Direcionamentos
 de replicação Acesso somente     leitura = vetor: 1 itens
     0 = string: EventDataLocation
 Acesso de Gravação de     Leitura = vetor: 0 itens
     . . .
       &quot;
   
   1. Na seção Membros, especifique o endereço IP para cada máquina.
   1. Atualize a contagem de itens do vetor Membros para refletir o número de endereços IP do computador inseridos.
   1. Na seção Acesso somente leitura, especifique o local dos dados de evento que a replicação direciona para acessar. Use barras na especificação do caminho (/). O local padrão é a [!DNL Logs] pasta no computador Repeater (/Logs/).
   1. Atualize a contagem de itens do vetor de Acesso Somente Leitura para refletir o número de locais inseridos.

1. Atualize o número de grupos de acesso no vetor de Grupos de controle de acesso na parte superior do arquivo para refletir a adição do novo grupo de acesso.

   ```
   Access Control Groups = vector: n items
   ```

1. Salve o arquivo.
