---
description: Os perfis e os arquivos de pesquisa desenvolvidos pelo Adobe para seu aplicativo específico são perfis internos que fornecem as métricas, as dimensões e os espaços de trabalho que permitem a análise do conjunto de dados.
title: Instalar perfis e arquivos de pesquisa
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Instalar perfis e arquivos de pesquisa{#installing-profiles-and-lookup-files}

Os perfis e os arquivos de pesquisa desenvolvidos pelo Adobe para seu aplicativo específico são perfis internos que fornecem as métricas, as dimensões e os espaços de trabalho que permitem a análise do conjunto de dados.

Assim como em todos os outros perfis internos fornecidos pelo Adobe, esses perfis não devem ser alterados. Toda personalização deve ocorrer em seu conjunto de dados, em perfis específicos de função ou em outros perfis que você criar.

O Adobe distribui o perfil e os arquivos de pesquisa para seu aplicativo como um arquivo [!DNL .zip]. Cada arquivo zip é nomeado para o aplicativo cujo perfil e arquivos de pesquisa ele contém. (Por exemplo, [!DNL Site52.zip] contém os arquivos de perfil do Site v5.2.) O arquivo [!DNL .zip] contém duas pastas ( [!DNL Lookups] e [!DNL Profiles]).

>[!NOTE]
>
>Se você ainda não tiver o arquivo de instalação contendo os perfis e os arquivos de pesquisa do seu aplicativo, baixe-os do site Adobe FTP antes de começar.

Você deve instalar o perfil e seus arquivos de pesquisa na máquina [!DNL Insight Server] na qual você processa e executa o perfil do conjunto de dados. Se você estiver executando um cluster [!DNL Insight Server], deverá instalar os arquivos no servidor principal. Para obter informações sobre perfis do conjunto de dados, consulte o *Guia de configuração do conjunto de dados*.

**Para instalar perfis para o aplicativo Adobe**

1. Abra a pasta [!DNL Profiles] do arquivo [!DNL .zip] fornecido a você pelo Adobe.

1. Copie todas as pastas dentro da pasta [!DNL Profiles] no arquivo [!DNL .zip] para a pasta [!DNL Profiles] no diretório de instalação [!DNL Insight Server]. Você deseja acabar com as pastas  [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]* em seu [!DNL Insight Server], como mostrado no exemplo a seguir. Os nomes de perfil reais podem ser diferentes.

   ![](assets/win_installprofiles.png)

1. Navegue até a pasta  [!DNL Profiles\]*&lt; [!DNL dataset profile name]* no diretório em que você instalou [!DNL Insight Server] e localize o arquivo [!DNL profile.cfg] nesse diretório.

   >[!NOTE]
   >
   >Se você estiver instalando perfis pela primeira vez, poderá usar o perfil de amostra fornecido como seu perfil de conjunto de dados. Você pode encontrar o arquivo [!DNL profile.cfg] (ele pode ser chamado como [!DNL profile.cfg.offline]) para o perfil de amostra na pasta [!DNL Profiles\Sample] no diretório de instalação [!DNL Insight Server].

1. Abra o arquivo [!DNL profile.cfg] usando um editor de texto como o Bloco de notas e faça o seguinte:

   1. Adicione entradas para os perfis internos no vetor Diretórios . Os nomes de perfil correspondem aos nomes dos diretórios que você copiou para a pasta [!DNL Profiles] na máquina [!DNL Insight Server].

   1. Atualize o número de diretórios, conforme apropriado.
   1. Adicione o nome comum do servidor à linha Nome Comum neste arquivo, conforme destacado abaixo:

      ```
      Profile = profileInfo: 
      Directories = vector: n+1 items
        0 = string: Base\\
        1 = string: internal profile name 1\\
        2 = string: internal profile name 2\\
      . . .
        n = string: internal profile name n\\
      Processing Servers = vector: 1 items
        0 = ProfileServerInfo: 
          Common Name = string: serverCommonName
          Server = string: 
      ```

      >[!NOTE]
      >
      >O *serverCommonName* que você especifica para o Nome Comum no arquivo [!DNL profile.cfg] corresponde ao nome comum do servidor para a máquina [!DNL Insight Server] na qual você está processando e executando o perfil do conjunto de dados. Para obter instruções para atualizar [!DNL profile.cfg] para que o perfil do conjunto de dados seja executado em um cluster [!DNL Insight Server], consulte [Clusters do servidor Insight](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Salve o arquivo. Certifique-se de salvar o arquivo como [!DNL profile.cfg] se ele tiver um nome diferente.

**Para instalar os arquivos de pesquisa para o aplicativo Adobe**

1. Abra a pasta [!DNL Lookups] do arquivo [!DNL .zip] fornecido a você pelo Adobe.

1. Copie todas as pastas dentro da pasta [!DNL Lookups] no arquivo [!DNL .zip] para a pasta [!DNL Lookups] no diretório de instalação [!DNL Insight Server]. Você deseja acabar com as pastas  [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]* em seu [!DNL Insight Server], como mostrado no exemplo a seguir. Os nomes de perfil reais podem ser diferentes.

   ![](assets/win_installLookups.png)
