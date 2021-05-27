---
description: O perfil Geografia fornecido com o Data WorkbenchGeografia é um perfil interno que fornece funcionalidade adicional ao aplicativo do Adobe.
title: Instalar o perfil geográfico
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# Instalar o perfil geográfico{#installing-the-geography-profile}

O perfil Geografia fornecido com o Data WorkbenchGeografia é um perfil interno que fornece funcionalidade adicional ao aplicativo do Adobe.

Assim como em todos os outros perfis internos fornecidos pelo Adobe, o perfil [!DNL Geography] não deve ser alterado. Toda personalização deve ocorrer em seu conjunto de dados, em perfis específicos de função ou em outros perfis que você criar.

O perfil [!DNL Geography] inclui vários arquivos de inclusão do conjunto de dados de transformação (localizados na pasta [!DNL Dataset\Transformation\Geography]) que definem dimensões geográficas. Veja a seguir uma lista dos arquivos de inclusão do conjunto de dados de transformação fornecidos com o perfil [!DNL Geography]:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Cada um dos arquivos é nomeado para a dimensão estendida que ela define. Um arquivo adicional, [!DNL IPLookup.cfg], define vários campos de dados geográficos usados para definir dimensões em outros arquivos de inclusão do conjunto de dados de transformação.

Para obter informações sobre arquivos de inclusão do conjunto de dados de transformação, consulte o *Guia de Configuração do Conjunto de Dados*.

**Para instalar o  [!DNL Geography] perfil no servidor do Data Workbench**

>[!NOTE]
>
>As instruções de instalação a seguir pressupõem que você instalou o Data Workbench e estabeleceu uma conexão entre o Data Workbench e o servidor do Data Workbench no qual está instalando o Data Workbench [!DNL Geography]. Se ainda não tiver feito isso, consulte o *Guia do Usuário do Data Workbench*.

1. Abra a pasta Perfis no arquivo [!DNL .zip] fornecido a você pelo Adobe.
1. Copie a pasta [!DNL Geography] para a pasta Perfis no diretório de instalação do servidor do Data Workbench. Você deseja terminar com uma pasta [!DNL ...\Profiles\Geography] no servidor do Data Workbench, como mostrado no exemplo a seguir. Os nomes das outras pastas dentro da pasta Perfis podem ser diferentes dos exibidos.

   ![Informações da etapa](assets/Geo_installProfiles_dir.png)

1. Use as etapas a seguir para atualizar o arquivo [!DNL profile.cfg] para cada perfil com o qual você deseja usar o Data Workbench [!DNL Geography].

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de verificação para este arquivo aparece na coluna [!DNL User].

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A janela [!DNL profile.cfg] é exibida.

   1. Na janela [!DNL profile.cfg], clique com o botão direito do mouse em **[!UICONTROL Directories]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para adicionar o novo diretório ao final da lista de diretórios, clique com o botão direito do mouse no número ou nome do último diretório na lista e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digite o nome do novo diretório: [!DNL Geography].
   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção de [!DNL profile.cfg] na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***.

      >[!NOTE]
      >
      >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe (incluindo o perfil [!DNL Geography]), pois as alterações são substituídas ao instalar atualizações nesses perfis.
