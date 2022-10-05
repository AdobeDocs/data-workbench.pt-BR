---
description: Os perfis e os arquivos de pesquisa desenvolvidos pelo Adobe para seu aplicativo específico são perfis internos que fornecem as métricas, as dimensões e os espaços de trabalho que permitem a análise do conjunto de dados.
title: Instalar perfis e arquivos de pesquisa
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 2%

---

# Instalar perfis e arquivos de pesquisa{#installing-profiles-and-lookup-files}

{{eol}}

Os perfis e os arquivos de pesquisa desenvolvidos pelo Adobe para seu aplicativo específico são perfis internos que fornecem as métricas, as dimensões e os espaços de trabalho que permitem a análise do conjunto de dados.

Assim como em todos os outros perfis internos fornecidos pelo Adobe, esses perfis não devem ser alterados. Toda personalização deve ocorrer em seu conjunto de dados, em perfis específicos de função ou em outros perfis que você criar.

O Adobe distribui o perfil e os arquivos de pesquisa para seu aplicativo como um [!DNL .zip] arquivo. Cada arquivo zip é nomeado para o aplicativo cujo perfil e arquivos de pesquisa ele contém. (Por exemplo, [!DNL Site52.zip] contém os arquivos de perfil do Site v5.2.) O [!DNL .zip] o arquivo contém duas pastas ( [!DNL Lookups] e [!DNL Profiles]).

>[!NOTE]
>
>Se você ainda não tiver o arquivo de instalação contendo os perfis e os arquivos de pesquisa do seu aplicativo, baixe-os do site Adobe FTP antes de começar.

Você deve instalar o perfil e seus arquivos de pesquisa no [!DNL Insight Server] máquina na qual você processa e executa o perfil do conjunto de dados. Se você estiver executando um [!DNL Insight Server] , você deve instalar os arquivos no servidor principal. Para obter informações sobre perfis do conjunto de dados, consulte *Guia de configuração do conjunto de dados*.

**Para instalar perfis para o aplicativo Adobe**

1. Abra o [!DNL Profiles] da pasta de [!DNL .zip] arquivo fornecido a você pelo Adobe.

1. Copie todas as pastas na [!DNL Profiles] na pasta [!DNL .zip] para [!DNL Profiles] na sua pasta [!DNL Insight Server] diretório de instalação. Você deseja terminar com [!DNL ...\Perfis\]*&lt; [!DNL internal profile name]>* nas pastas [!DNL Insight Server] como mostrado no exemplo a seguir. Os nomes de perfil reais podem ser diferentes.

   ![](assets/win_installprofiles.png)

1. Navegue até o  [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* no diretório em que você instalou o [!DNL Insight Server] e localize a [!DNL profile.cfg] neste diretório.

   >[!NOTE]
   >
   >Se você estiver instalando perfis pela primeira vez, poderá usar o perfil de amostra fornecido como seu perfil de conjunto de dados. Você pode encontrar a variável [!DNL profile.cfg] (pode ser nomeado como algo como [!DNL profile.cfg.offline]) para o perfil de amostra no [!DNL Profiles\Sample] na sua pasta [!DNL Insight Server] diretório de instalação.

1. Abra o [!DNL profile.cfg] arquivo usando um editor de texto, como o Bloco de notas, e faça o seguinte:

   1. Adicione entradas para os perfis internos no vetor Diretórios . Os nomes dos perfis correspondem aos nomes dos diretórios que você copiou para o [!DNL Profiles] na pasta [!DNL Insight Server] máquina.

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
      >O *serverCommonName* que você especifica para o Nome comum no [!DNL profile.cfg] o arquivo corresponde ao nome comum do servidor para o [!DNL Insight Server] máquina na qual você está processando e executando o perfil do conjunto de dados. Para obter instruções de atualização [!DNL profile.cfg] para que o perfil do conjunto de dados seja executado em um [!DNL Insight Server] cluster, consulte [Clusters do servidor Insight](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Salve o arquivo. Certifique-se de salvar o arquivo como [!DNL profile.cfg] se tiver sido nomeado de forma diferente.

**Para instalar os arquivos de pesquisa para o aplicativo Adobe**

1. Abra o [!DNL Lookups] da pasta de [!DNL .zip] arquivo fornecido a você pelo Adobe.

1. Copie todas as pastas na [!DNL Lookups] na pasta [!DNL .zip] para [!DNL Lookups] na sua pasta [!DNL Insight Server] diretório de instalação. Você deseja terminar com [!DNL ...\Pesquisas\]*&lt; [!DNL internal profile name]>* nas pastas [!DNL Insight Server] como mostrado no exemplo a seguir. Os nomes de perfil reais podem ser diferentes.

   ![](assets/win_installLookups.png)
