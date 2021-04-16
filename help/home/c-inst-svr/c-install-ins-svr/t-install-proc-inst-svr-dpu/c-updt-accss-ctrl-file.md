---
description: O arquivo Access Control.cfg gerencia o acesso a determinados recursos no servidor Insight.
title: Atualizar o arquivo de controle de acesso
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Atualizar o arquivo de controle de acesso{#updating-the-access-control-file}

O arquivo Access Control.cfg gerencia o acesso a determinados recursos no servidor Insight.

Ele define entidades chamadas AccessGroups. Um AccessGroup identifica um grupo de usuários com permissão para usar determinados recursos do servidor.

Antes de se conectar a [!DNL Insight Server] com [!DNL Insight], você deve atualizar o Grupo de acesso de administradores para incluir uma das licenças [!DNL Insight] emitidas pelo Adobe para sua organização. Este AccessGroup identifica usuários com permissão para executar funções administrativas por meio de [!DNL Insight].

O procedimento a seguir descreve como adicionar uma licença ao Grupo de acesso de administradores. Para concluir essa tarefa, você deve determinar qual licença [!DNL Insight] tem privilégios administrativos para sua organização. (Para a instalação e configuração iniciais, é suficiente conceder privilégios administrativos a uma única licença. Posteriormente, você poderá conceder privilégios administrativos a licenças adicionais.) Você também precisa saber o &quot;nome comum&quot; atribuído a esta licença. Para obter esse valor, você pode examinar os certificados de licença de sua conta em [https://aap.adobe.com](https://aap.adobe.com).

A finalidade deste procedimento é simplesmente identificar uma cópia licenciada de [!DNL Insight] que pode ser usada para configurar e configurar [!DNL Insight Server] inicialmente. Depois de identificar essa licença, você pode executar todas as configurações subsequentes do servidor (incluindo a configuração adicional do AccessGroup) usando a cópia licenciada de [!DNL Insight]. Para obter informações adicionais sobre como controlar o acesso ao servidor usando Grupos de Acesso, consulte [Configurar Controle de Acesso](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Para atualizar o arquivo de controle de acesso**

1. Navegue até a pasta [!DNL Access Control] no diretório em que você instalou [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\Access Control]

1. Abra o arquivo [!DNL Access Control.cfg] em um editor de texto, como o Bloco de notas.
1. Localize a entrada CN no Grupo de acesso de administradores e substitua o valor existente desta entrada pelo nome comum que identifica o [!DNL Insight] que você usará para configurar e administrar inicialmente [!DNL Insight Server]. O fragmento de arquivo a seguir ilustra onde você insere o nome comum no arquivo [!DNL Access Control.cfg].

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   ```

   Se você estiver usando a autenticação baseada em credenciais, algumas entradas adicionais estarão disponíveis para configuração. Essas entradas são:

   * O (ID da organização): Essa entrada representa a ID da organização. Por exemplo, `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Essa ID pode ser encontrada no Admin Console.
   * PLC - Esta entrada permite o acesso aos usuários provisionados para uma configuração de produto específica. Ele pode ser usado no formato `Organization_Id-PLC`. Por exemplo, `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Os usuários provisionados para a Data Workbench usando o PLC `DataworkbenchAdminUsers` obterão acesso em seus servidores.
   * Email - Essa entrada permite acesso a qualquer usuário individual. Seu valor deve ser o endereço de email do usuário provisionado. Por exemplo, `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * As entradas fazem distinção entre maiúsculas e minúsculas. Você deve garantir que os valores especificados para O, PLC e Email sejam exatamente os mesmos mostrados no Admin Console.
   >    * Digite o nome comum exatamente como ele aparece no certificado.
   >    * Não use a tecla Tab para gerar espaço em branco no arquivo [!DNL Access Control.cfg] (ou em qualquer outro arquivo de configuração para um componente Adobe). Use apenas espaços para criar espaços em branco. Um caractere de tabulação impede que o sistema leia o arquivo corretamente.


1. Salve e feche o arquivo.
