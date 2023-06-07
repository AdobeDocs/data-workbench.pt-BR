---
description: O arquivo Access Control.cfg gerencia o acesso a determinados recursos no Servidor Insight.
title: Atualizar o arquivo de controle de acesso
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: 5ce5b8f8b35d2d4f319076f54347e300e5f133df
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 3%

---

# Atualizar o arquivo de controle de acesso{#updating-the-access-control-file}

{{eol}}

O arquivo Access Control.cfg gerencia o acesso a determinados recursos no Servidor Insight.

Ele define entidades chamadas AccessGroups. Um AccessGroup identifica um grupo de usuários que têm permissão para usar determinados recursos do servidor.

Antes de se conectar ao [!DNL Insight Server] com [!DNL Insight], você deve atualizar o Grupo de acesso de administradores para incluir um dos [!DNL Insight] que o Adobe emitiu para a sua organização. Este AccessGroup identifica os usuários que têm permissão para executar funções administrativas por meio do [!DNL Insight].

O procedimento a seguir descreve como adicionar uma licença ao Grupo de acesso de administradores. Para concluir essa tarefa, você deve determinar quais [!DNL Insight] a licença tem privilégios administrativos para sua organização. (Para a instalação e configuração iniciais, é suficiente conceder privilégios administrativos a uma única licença. Você pode conceder privilégios administrativos a licenças adicionais posteriormente.) Você também precisa saber o &quot;nome comum&quot; atribuído a esta licença.

O objetivo deste procedimento é simplesmente identificar uma cópia licenciada do [!DNL Insight] que você pode usar para instalar e configurar inicialmente [!DNL Insight Server]. Depois de identificar esta licença, você pode executar todas as configurações subsequentes do servidor (incluindo configurações adicionais do AccessGroup) usando a cópia licenciada do [!DNL Insight]. Para obter informações adicionais sobre como controlar o acesso ao servidor usando AccessGroups, consulte [Configurar o controle de acesso](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Para atualizar o arquivo de controle de acesso**

1. Navegue até a [!DNL Access Control] pasta no diretório em que você instalou o [!DNL Insight Server].

   Exemplo: [!DNL C:\Adobe\Server\Access Control]

1. Abra o [!DNL Access Control.cfg] em um editor de texto como o Notepad.
1. Localize a entrada CN no Grupo de Acesso de Administradores e substitua o valor existente dessa entrada pelo nome comum que identifica o [!DNL Insight] que você usará para configurar e administrar inicialmente [!DNL Insight Server]. O fragmento de arquivo a seguir ilustra onde você insere o nome comum no [!DNL Access Control.cfg] arquivo.

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

   Se você estiver usando autenticação baseada em credenciais, algumas entradas adicionais estarão disponíveis para configuração. Essas entradas são:

   * O (ID da Organização): essa entrada representa a ID da organização. Por exemplo, `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Essa ID pode ser encontrada no Admin Console.
   * PLC - Essa entrada permite acesso aos usuários provisionados para uma configuração de produto específica. Pode ser usado no formato `Organization_Id-PLC`. Por exemplo, `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Os usuários provisionados para o Data Workbench usando o PLC `DataworkbenchAdminUsers` terão acesso aos servidores.
   * Email - Esta entrada permite acesso a qualquer usuário individual. Seu valor deve ser o endereço de email do usuário provisionado. Por exemplo, `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * As entradas diferenciam maiúsculas de minúsculas. Você deve garantir que os valores especificados para O, PLC e Email sejam exatamente os mesmos que os mostrados no Admin Console.
   >    * Digite o nome comum exatamente como aparece no certificado.
   >    * Não use a tecla Tab para gerar espaços em branco no [!DNL Access Control.cfg] arquivo (ou em qualquer outro arquivo de configuração para um componente Adobe). Use somente espaços para criar espaços em branco. Um caractere de tabulação impede que o sistema leia o arquivo corretamente.


1. Salvar e fechar o arquivo.
