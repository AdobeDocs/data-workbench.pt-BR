---
description: Os administradores podem conferir aos usuários da estação de trabalho a capacidade parcial de gerenciar o controle de acesso para grupos personalizados.
title: Administração do usuário de acesso do membro do grupo
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# Administração do usuário de acesso do membro do grupo{#user-administration-of-group-member-access}

{{eol}}

Os administradores podem conferir aos usuários da estação de trabalho a capacidade parcial de gerenciar o controle de acesso para grupos personalizados.

**Autoadministração do acesso dos membros do grupo** concede direitos a não administradores para adicionar e excluir membros em um grupo personalizado. O administrador cria um **Lista de usuários** e configura o acesso de grupo no [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) para os novos membros do grupo.

**Acesso ao gerenciador de servidores**

Configurar o **[!DNL User List]** e sincronizá-lo com o **[!DNL Communications.cfg]** O arquivo é feito na variável **Gerenciador de servidores** espaço de trabalho.

1. Na bancada, clique no botão **Administrador** guia > **Conjunto de dados e perfil** guia .

1. Abra o **Gerenciador de servidores** espaço de trabalho.
1. Clique com o botão direito do mouse em >*nome do servidor*> no diagrama e selecione **Arquivos**.

   Os arquivos do servidor serão abertos em uma tabela com colunas *Arquivo*, *`<server name>`* e *Temp*.

1. **Tornar local** clicando com o botão direito do mouse na coluna servidor de um arquivo de servidor (para este recurso) **[!DNL Access Control]** e **[!DNL Components/Communications.cfg)]**.

   Uma marca de seleção branca aparecerá no **Temp** coluna. Você pode editar na pasta Temp. Em seguida, clique com o botão direito do mouse na marca de seleção e **Salvar em** o servidor. (Fica vermelho quando sincronizado com o servidor).

## Criar um arquivo User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

O administrador precisa criar um **[!DNL User List.cfg]** no **[!DNL Access Control]** pasta.

1. Clique com o botão direito do mouse na linha Controle de acesso** na **Temp** e selecione **Abrir** > **Pasta**. ![](assets/6_4_workstation_groups_3.png)

   A pasta Controle de acesso na **Temp** abrirá a listagem de um único **[!DNL Access Control.cfg]** arquivo.

1. Adicionar outro arquivo de texto a esta pasta e nomeá-la **[!DNL User List.cfg]** (ao lado do **[!DNL Access Control.cfg]**).

1. Adicione os seguintes parâmetros ao **[!DNL User List.cfg]** arquivo.

O arquivo de Lista de usuários deve conter um vetor de **AccessGroup** objetos e cada **AccessGroup** objeto deve ter um nome e um vetor de sequências de caracteres chamado **Membros**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Em seguida, você pode editar e adicionar usuários isso na exibição Estação de trabalho do **[!DNL User List.cfg]**arquivo.

![](assets/6_4_workstation_groups_4.png)

Estes são os parâmetros mais básicos a serem adicionados ao **[!DNL User List.cfg]** arquivo. Os Membros podem então ser adicionados na exibição Estação de trabalho.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Como em qualquer **[!DNL .cfg]** arquivos que você edita manualmente, certifique-se de usar espaços em vez de guias e prestar muita atenção ao espaço em branco e à sintaxe. Um erro nesse arquivo causará *Servidor Adobe Insight* para ignorar o arquivo Lista de usuários.

O **Nome** em cada **Grupo de acesso** serão referenciadas no [!DNL Access Control.cfg] arquivo.

>[!NOTE]
>
>Somente membros válidos com prefixos de serviço de diretório, como **NC:** ou **OU:** são aceitos e não podem conter caractere curinga (&#42;).

## Configurar o arquivo Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

Primeiro, um administrador ativa esse recurso abrindo o **[!DNL Components]>[!DNL Communications.cfg]** e adicionar uma nova chave com o nome **[!DNL Access Control User List File]**. O valor da string dessa chave é o caminho onde esse novo arquivo será localizado.

1. Nos arquivos do servidor, clique em **Componentes** e clique com o botão direito do mouse na marca de seleção na coluna do servidor. Clique em **Tornar local**.

   Uma marca de seleção branca aparecerá no **Temp** coluna.

1. Clique com o botão direito do mouse na marca de seleção no **Temp** e selecione **Abrir** > **na estação de trabalho**.

1. No **Communication.cfg** , clique com o botão direito do mouse **componente** e selecione **Adicionar chave personalizada.** ![](assets/6_4_workstation_groups.png)

1. Digite o **Nome** as *Arquivo de Lista de Usuários de Controle de Acesso* e definir **Tipo** as *String*.

   >[!NOTE]
   >
   >Não é possível criar o novo arquivo de lista como um Caminho. Para corrigir isso, você precisa salvar o arquivo, abri-lo em um editor (Bloco de notas) e alterar &quot;Cadeia de caracteres&quot; para &quot;Caminho&quot;:

   Antes:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <string>: Access Control\\User List.cfg
   ```

   Depois:

   ```
   component = CommServer:  
     Access Control File = Path: Access Control\\Access Control.cfg 
     Access Control User List File =  
    <Path>: Access Control\\User List.cfg
   ```

1. Salve as **[!DNL Communications.cfg]** e (se necessário) salvá-lo no servidor. Isso reiniciará os componentes no servidor para garantir que você não tenha cometido nenhum erro que possa impedir o **[!DNL Communications.cfg]** de ser analisado.
1. Se o sistema incluir servidores de processamento, modifique o arquivo de configuração no **[!DNL Components for Processing Servers.cfg]** arquivo.
1. Clique com o botão direito do mouse **[!DNL Communications.cfg]** e salvar no servidor.

O administrador do Data Workbench agora pode confirmar que os usuários pretendidos têm acesso ao arquivo da lista de usuários e permitem que os usuários gerenciem o grupo. Os usuários poderão abrir o arquivo da Lista de usuários, editá-lo e adicionar e remover membros CN ou OU, conforme necessário.

## Sincronizar o arquivo Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

O administrador pode editar a variável **[!DNL Access Control.cfg]** e inserir referências aos grupos definidos pelo *Lista de usuários* arquivo.

As referências aos grupos devem ser inseridas como qualquer outro membro, mas com a seguinte sintaxe:

```
$(Group Name)
```

Onde &quot;Nome do grupo&quot; corresponde ao definido no arquivo da lista de usuários, incluindo espaços em branco. ![](assets/6_4_workstation_groups_2.png)

Nesse ponto, o administrador do Data Workbench pode confirmar que os usuários do grupo selecionado têm acesso ao arquivo da lista de usuários. Os usuários selecionados podem então abrir o **[!DNL User List.cfg]** arquivo, edite-o e adicione e remova membros CN ou OU conforme necessário.
