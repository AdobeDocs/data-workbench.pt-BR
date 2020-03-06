---
description: Os administradores podem conferir aos usuários da estação de trabalho a capacidade parcial de gerenciar o controle de acesso para grupos personalizados.
title: Administração do usuário do acesso do membro do grupo
uuid: c31128f9-1094-4337-9bf6-96401278df33
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# User Administration of Group Member Access{#user-administration-of-group-member-access}

Os administradores podem conferir aos usuários da estação de trabalho a capacidade parcial de gerenciar o controle de acesso para grupos personalizados.

**A autoadministração do acesso** do membro do grupo concede direitos a não administradores para adicionar e excluir membros em um grupo personalizado. O administrador cria um arquivo de Lista **de** usuários e configura o acesso de grupo no arquivo [Access Control.cfg](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/c-config-acs-ctrl.html) para os novos membros do grupo.

**Acesso ao gerenciador de servidores**

A configuração do **[!DNL User List]** arquivo e sua sincronização com o **[!DNL Communications.cfg]** arquivo é feita na área de trabalho **do Gerenciador** de Servidores.

1. Na área de trabalho, clique na guia **Admin** > **Conjunto de dados e na guia Perfil** .

1. Abra a área de trabalho **do Gerenciador** de Servidores.
1. Clique com o botão direito do mouse em >*seu nome* de servidor> no diagrama e selecione **Arquivos**.

   Os arquivos do servidor serão abertos em uma tabela com colunas *Arquivo*, *`<server name>`* e *Temp*.

1. **Tornar local** clicando com o botão direito do mouse na coluna do servidor de um arquivo de servidor (para este recurso **[!DNL Access Control]** e **[!DNL Components/Communications.cfg)]**.

   Uma marca de seleção branca será exibida na coluna **Temp** . Você pode editar na pasta Temp. Em seguida, clique com o botão direito do mouse na marca de seleção e em **Salvar** no servidor. (Fica vermelho quando sincronizado com o servidor).

## Criar um arquivo User List.cfg {#section-c25bcaf34f4546e6b8b65f5e7f69ac09}

O administrador precisa criar um **[!DNL User List.cfg]** arquivo na **[!DNL Access Control]** pasta.

1. Clique com o botão direito do mouse na linha Controle de acesso** na coluna **Temp** e selecione **Abrir** > **Pasta**. ![](assets/6_4_workstation_groups_3.png)

   A pasta Controle de acesso na pasta **Temp** abrirá listando um único **[!DNL Access Control.cfg]** arquivo.

1. Adicione outro arquivo de texto a esta pasta e o nomeie **[!DNL User List.cfg]** (ao lado da **[!DNL Access Control.cfg]**).

1. Add the following parameters to the **[!DNL User List.cfg]** file.

O arquivo Lista de usuários deve conter um vetor de objetos **AccessGroup** e cada objeto **AccessGroup** deve ter um nome e um vetor de strings chamados de **Membros**.

```
Access Control Groups = vector: 1 items 
  0 = AccessGroup:  
    Name = string: Group 1 
    Members = vector: 1 items 
      0 = string: CN:Joe User
```

Em seguida, você pode editar e adicionar usuários na exibição Estação de trabalho do arquivo **[!DNL User List.cfg]**s.

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
>Assim como em qualquer **[!DNL .cfg]** arquivo que você edita manualmente, certifique-se de usar espaços em vez de guias e de prestar muita atenção ao espaço em branco e à sintaxe. Um erro nesse arquivo fará com que o *Adobe Insight Server* ignore o arquivo da Lista de usuários.

O campo **Nome** em cada Grupo **de** acesso será referenciado dentro do [!DNL Access Control.cfg] arquivo.

>[!NOTE]
>
>Somente membros válidos com prefixos de serviço de diretório, como **CN:** ou **OU:** são aceitos e não podem conter caractere curinga (*).

## Configurar o arquivo Communications.cfg {#section-9d6f05ba81c14f15be63e361533459e8}

Primeiro, um administrador ativa esse recurso abrindo o arquivo **[!DNL Components]>[!DNL Communications.cfg]**e adicionando uma nova chave com o nome **[!DNL Access Control User List File]**. O valor da string dessa chave é o caminho no qual o novo arquivo será localizado.

1. Nos arquivos do servidor, clique em **Componentes** e clique com o botão direito do mouse na marca de seleção na coluna do servidor. Clique em **Tornar local**.

   Uma marca de seleção branca será exibida na coluna **Temp** .

1. Clique com o botão direito do mouse na marca de seleção na coluna **Temp** e selecione **Abrir** > **na estação de trabalho**.

1. No arquivo **Communication.cfg** , clique com o botão direito do mouse no **componente** e selecione **Adicionar chave personalizada.** ![](assets/6_4_workstation_groups.png)

1. Digite o **Nome** como Arquivo *de lista de usuários do controle de* acesso e defina **Do tipo** como *String*.

   >[!NOTE]
   Não é possível criar o novo arquivo de lista como um Caminho. Para corrigir isso, é necessário salvar o arquivo, abri-lo em um editor (Bloco de notas) e alterar &quot;String&quot; para &quot;Caminho&quot;:

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

1. Salve o **[!DNL Communications.cfg]** arquivo e (se necessário) salve-o no servidor. Isso reiniciará os componentes no servidor para garantir que você não tenha cometido nenhum erro que possa impedir a análise do **[!DNL Communications.cfg]** arquivo.
1. Se o sistema incluir servidores de processamento, modifique o arquivo de configuração no **[!DNL Components for Processing Servers.cfg]** arquivo.
1. Clique com o botão direito do mouse **[!DNL Communications.cfg]** e salve no servidor.

O administrador da Análise de big data agora pode confirmar se os usuários desejados têm acesso ao arquivo da lista de usuários e permitem que os usuários gerenciem o grupo. Os usuários poderão abrir o arquivo Lista de usuários, editá-lo e adicionar e remover membros CN ou OU, conforme necessário.

## Sincronizar o arquivo Access Control.cfg {#section-ca6da453dfb4432bb40b86ef15ede872}

Em seguida, o administrador pode editar **[!DNL Access Control.cfg]** e inserir referências aos grupos definidos pelo arquivo Lista *de* usuários.

As referências aos grupos devem ser inseridas como qualquer outro membro, mas com a seguinte sintaxe:

```
$(Group Name)
```

Onde &quot;Nome do grupo&quot; corresponde ao que é definido no arquivo da lista de usuários, incluindo espaços em branco. ![](assets/6_4_workstation_groups_2.png)

Neste ponto, o administrador da Análise de big data pode confirmar que usuários selecionados do grupo têm acesso ao arquivo da lista de usuários. Os usuários selecionados podem então abrir o **[!DNL User List.cfg]** arquivo, editá-lo e adicionar e remover membros da CN ou OU, conforme necessário.
