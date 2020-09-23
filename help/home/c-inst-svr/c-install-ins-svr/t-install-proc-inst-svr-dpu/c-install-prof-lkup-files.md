---
description: Os perfis e arquivos de pesquisa desenvolvidos pelo Adobe para seu aplicativo em particular são perfis internos que fornecem as métricas, dimensões e espaços de trabalho que permitem a análise do seu conjunto de dados.
solution: Analytics
title: Instalar perfis e arquivos de pesquisa
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---


# Instalar perfis e arquivos de pesquisa{#installing-profiles-and-lookup-files}

Os perfis e arquivos de pesquisa desenvolvidos pelo Adobe para seu aplicativo em particular são perfis internos que fornecem as métricas, dimensões e espaços de trabalho que permitem a análise do seu conjunto de dados.

Como acontece com todos os outros perfis internos fornecidos pelo Adobe, esses perfis não devem ser alterados. Toda a personalização deve ocorrer em seu conjunto de dados ou em perfis específicos da função ou em outros perfis criados.

O Adobe distribui os arquivos de perfil e pesquisa para seu aplicativo como um [!DNL .zip] arquivo. Cada arquivo zip é nomeado para o aplicativo cujos arquivos de perfil e pesquisa ele contém. (Por exemplo, [!DNL Site52.zip] contém os arquivos de perfil para Site v5.2.) O [!DNL .zip] arquivo contém duas pastas ( [!DNL Lookups] e [!DNL Profiles]).

>[!NOTE]
>
>Se você ainda não tiver o arquivo de instalação que contém os perfis e os arquivos de pesquisa para seu aplicativo, baixe-os do site FTP da Adobe antes de começar.

É necessário instalar o perfil e seus arquivos de pesquisa na [!DNL Insight Server] máquina em que você processa e executa o perfil do conjunto de dados. Se estiver executando um [!DNL Insight Server] cluster, você deverá instalar os arquivos no servidor principal. Para obter informações sobre perfis de conjuntos de dados, consulte o Guia *de configuração de* conjuntos de dados.

**Para instalar perfis para seu aplicativo Adobe**

1. Abra a [!DNL Profiles] pasta do [!DNL .zip] arquivo fornecido a você por Adobe.

1. Copie todas as pastas dentro da [!DNL Profiles] pasta no [!DNL .zip] arquivo para a [!DNL Profiles] pasta no diretório de [!DNL Insight Server] instalação. Você deseja terminar com  [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>* pastas em seu [!DNL Insight Server] , como mostrado no exemplo a seguir. Seus nomes de perfis reais podem ser diferentes.

   ![](assets/win_installprofiles.png)

1. Navegue até a pasta  [!DNL Profiles\]*&lt;[!DNL dataset profile name]>* no diretório em que você instalou [!DNL Insight Server] e localize o [!DNL profile.cfg] arquivo neste diretório.

   >[!NOTE]
   >
   >Se estiver instalando perfis pela primeira vez, você pode usar o perfil de amostra fornecido como perfil de conjunto de dados. Você pode encontrar o [!DNL profile.cfg] arquivo (ele pode ter o nome [!DNL profile.cfg.offline]) para o perfil Sample na [!DNL Profiles\Sample] pasta do diretório de [!DNL Insight Server] instalação.

1. Abra o [!DNL profile.cfg] arquivo usando um editor de texto, como o Bloco de notas, e faça o seguinte:

   1. Adicione entradas para os perfis internos no vetor Diretórios. Os nomes dos perfis correspondem aos nomes dos diretórios que você copiou para a [!DNL Profiles] pasta no [!DNL Insight Server] computador.

   1. Atualize o número de diretórios conforme apropriado.
   1. Adicione o nome comum do servidor à linha Common Name (Nome comum) neste arquivo, como destacado abaixo:

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
      >O *serverCommonName* especificado para o Nome comum no [!DNL profile.cfg] arquivo corresponde ao nome comum do servidor para a [!DNL Insight Server] máquina na qual você está processando e executando o perfil do conjunto de dados. Para obter instruções sobre como atualizar [!DNL profile.cfg] para que o perfil do conjunto de dados seja executado em um [!DNL Insight Server] cluster, consulte [Insight Server Clusters](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Salve o arquivo. Certifique-se de salvar o arquivo como [!DNL profile.cfg] se ele tivesse um nome diferente.

**Para instalar os arquivos de pesquisa do aplicativo Adobe**

1. Abra a [!DNL Lookups] pasta do [!DNL .zip] arquivo fornecido a você por Adobe.

1. Copie todas as pastas dentro da [!DNL Lookups] pasta no [!DNL .zip] arquivo para a [!DNL Lookups] pasta no diretório de [!DNL Insight Server] instalação. Você deseja terminar com  [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>* pastas em seu [!DNL Insight Server] , como mostrado no exemplo a seguir. Seus nomes de perfis reais podem ser diferentes.

   ![](assets/win_installLookups.png)

