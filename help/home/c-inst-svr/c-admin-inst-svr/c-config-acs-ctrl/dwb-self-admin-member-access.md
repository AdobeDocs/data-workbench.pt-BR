---
description: Os administradores podem conferir aos usuários da estação de trabalho a capacidade parcial de gerenciar o controle de acesso para grupos personalizados.
title: Administração do usuário de acesso do membro do grupo
uuid: c31128f9-1094-4337-9bf6-96401278df33
exl-id: 6d2a0f19-a33c-49f6-a470-c95d2c1532c7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---

# Administração do usuário de acesso do membro do grupo{#user-administration-of-group-member-access}

Os administradores podem conferir aos usuários da estação de trabalho a capacidade parcial de gerenciar o controle de acesso para grupos personalizados.

**A autoadministração do** acesso do membro do grupo dá direitos a não administradores para adicionar e excluir membros em um grupo personalizado. O administrador cria um arquivo **Lista de usuários** e configura o acesso de grupo no arquivo [Access Control.cfg](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) para os novos membros do grupo.

**Acesso ao gerenciador de servidores**

A configuração do arquivo **[!DNL User List]** e a sincronização com o arquivo **[!DNL Communications.cfg]** são feitas no espaço de trabalho **Gerenciador de Servidores**.

1. Na bancada, clique na guia **Admin** > **Conjunto de dados e Perfil**.

1. Abra o espaço de trabalho **Gerenciador de Servidores**.
1. Clique com o botão direito do mouse em >*nome do servidor*> no diagrama e selecione **Arquivos**.

   Os arquivos do servidor serão abertos em uma tabela com as colunas *File*, *`<server name>`* e *Temp*.

1. **Faça clique com o botão** Local clicando com o botão direito do mouse na coluna do servidor de um arquivo do servidor (para esse recurso  **[!DNL Access Control]** e  **[!DNL Components/Communications.cfg)]**.

   Uma marca de seleção branca aparecerá na coluna **Temp**. Você pode editar na pasta Temp. Em seguida, clique com o botão direito do mouse na marca de seleção e **Salve em** no servidor. (Fica vermelho quando sincronizado com o servidor).

## Criar um arquivo User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

O administrador precisa criar um arquivo **[!DNL User List.cfg]** na pasta **[!DNL Access Control]**.

1. Clique com o botão direito do mouse na linha Controle de Acesso** na coluna **Temp** e selecione **Abrir** > **Pasta**. ![](assets/6_4_workstation_groups_3.png)

   A pasta Controle de acesso na pasta **Temp** abrirá a listagem de um único arquivo **[!DNL Access Control.cfg]**.

1. Adicione outro arquivo de texto a essa pasta e o nomeie como **[!DNL User List.cfg]** (ao lado de **[!DNL Access Control.cfg]**).

1. Adicione os seguintes parâmetros ao arquivo **[!DNL User List.cfg]**.

O arquivo Lista de usuários deve conter um vetor de objetos **AccessGroup** e cada objeto **AccessGroup** deve ter um nome e um vetor de sequências de caracteres chamado **Members**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Em seguida, você pode editar e adicionar usuários isso na exibição Estação de trabalho do arquivo **[!DNL User List.cfg]**.

![](assets/6_4_workstation_groups_4.png)

Estes são os parâmetros mais básicos a serem adicionados ao arquivo **[!DNL User List.cfg]**. Os Membros podem então ser adicionados na exibição Estação de trabalho.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string:  
    Members = vector: 0 items
```

>[!IMPORTANT]
>
>Assim como em qualquer arquivo **[!DNL .cfg]** que você edita manualmente, certifique-se de usar espaços em vez de guias e prestar muita atenção ao espaço em branco e à sintaxe. Um erro nesse arquivo fará com que *Adobe Insight Server* ignore o arquivo de Lista de usuários.

O campo **Nome** em cada **Grupo de Acesso** será referenciado dentro do arquivo [!DNL Access Control.cfg].

>[!NOTE]
>
>Somente membros válidos com prefixos de serviço de diretório, como **CN:** ou **OU:**, são aceitos e não podem conter caractere curinga (*).

## Configurar o arquivo Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

Primeiro, um administrador ativa esse recurso, abrindo o arquivo **[!DNL Components]>[!DNL Communications.cfg]** e adicionando uma nova chave com o nome **[!DNL Access Control User List File]**. O valor da string dessa chave é o caminho onde esse novo arquivo será localizado.

1. Nos arquivos do servidor, clique em **Components** e clique com o botão direito do mouse na marca de seleção na coluna do servidor. Clique em **Tornar Local**.

   Uma marca de seleção branca aparecerá na coluna **Temp**.

1. Clique com o botão direito do mouse na marca de seleção na coluna **Temp** e selecione **Abrir** > **na estação de trabalho**.

1. No arquivo **Communication.cfg**, clique com o botão direito do mouse **component** e selecione **Adicionar chave personalizada.** ![](assets/6_4_workstation_groups.png)

1. Digite o **Name** como *Access Control User List File* e defina **Of Type** como *String*.

   >[!NOTE]
   Não é possível criar o novo arquivo de lista como um Caminho. Para corrigir isso, você precisa salvar o arquivo, abri-lo em um editor (Bloco de notas) e alterar &quot;Cadeia de caracteres&quot; para &quot;Caminho&quot;:

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

1. Salve o arquivo **[!DNL Communications.cfg]** e (se necessário) salve-o no servidor. Isso reiniciará os componentes no servidor para garantir que você não tenha cometido nenhum erro que possa impedir a análise do arquivo **[!DNL Communications.cfg]**.
1. Se o sistema incluir servidores de processamento, modifique o arquivo de configuração no arquivo **[!DNL Components for Processing Servers.cfg]**.
1. Clique com o botão direito do mouse em **[!DNL Communications.cfg]** e salve no servidor.

O administrador do Data Workbench agora pode confirmar que os usuários pretendidos têm acesso ao arquivo da lista de usuários e permitem que os usuários gerenciem o grupo. Os usuários poderão abrir o arquivo da Lista de usuários, editá-lo e adicionar e remover membros CN ou OU, conforme necessário.

## Sincronizar o arquivo Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

O administrador pode editar o **[!DNL Access Control.cfg]** e inserir referências aos grupos definidos pelo arquivo de *Lista de usuários*.

As referências aos grupos devem ser inseridas como qualquer outro membro, mas com a seguinte sintaxe:

```
$(Group Name)
```

Onde &quot;Nome do grupo&quot; corresponde ao definido no arquivo da lista de usuários, incluindo espaços em branco. ![](assets/6_4_workstation_groups_2.png)

Nesse ponto, o administrador do Data Workbench pode confirmar que os usuários do grupo selecionado têm acesso ao arquivo da lista de usuários. Os usuários selecionados podem então abrir o arquivo **[!DNL User List.cfg]**, editá-lo e adicionar e remover membros CN ou OU, conforme necessário.
