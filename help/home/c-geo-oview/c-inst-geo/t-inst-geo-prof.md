---
description: O perfil geográfico fornecido com a análise de big dataGeografia é um perfil interno que fornece funcionalidade adicional ao seu aplicativo Adobe.
solution: Analytics
title: Instalação do perfil geográfico
topic: Data workbench
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalação do perfil geográfico{#installing-the-geography-profile}

O perfil geográfico fornecido com a análise de big dataGeografia é um perfil interno que fornece funcionalidade adicional ao seu aplicativo Adobe.

Assim como com todos os outros perfis internos fornecidos pela Adobe, o [!DNL Geography] perfil não deve ser alterado. Toda personalização deve ocorrer em seu conjunto de dados ou em perfis específicos de função ou em outros perfis que você criar.

O [!DNL Geography] perfil inclui vários conjuntos de dados de transformação que incluem arquivos (localizados na [!DNL Dataset\Transformation\Geography] pasta) que definem dimensões geográficas. A seguir, uma lista do conjunto de dados de transformação inclui os arquivos fornecidos com o [!DNL Geography] perfil:

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

Cada um dos arquivos é nomeado para a dimensão estendida que ela define. Um arquivo adicional, [!DNL IPLookup.cfg], define vários campos de dados geográficos que são usados para definir dimensões em outro conjunto de dados de transformação inclui arquivos.

Para obter informações sobre como o conjunto de dados de transformação incluir arquivos, consulte o Guia *de Configuração do* Conjunto de Dados.

**Para instalar o[!DNL Geography]perfil no servidor da análise de big data**

>[!NOTE]
>
>As instruções de instalação a seguir pressupõem que você instalou a análise de big data e estabeleceu uma conexão entre a análise de big data e o servidor da análise de big data no qual você está instalando a análise de big data [!DNL Geography]. Se você não tiver feito isso, consulte o Guia ** do usuário da Análise de big data.

1. Abra a pasta Perfis a partir do arquivo [!DNL .zip] fornecido a você pela Adobe.
1. Copie a [!DNL Geography] pasta para a pasta Perfis no diretório de instalação do servidor da análise de big data. Você deseja terminar com uma [!DNL ...\Profiles\Geography] pasta no servidor do análise de big data, como mostrado no exemplo a seguir. Os nomes das outras pastas dentro da pasta Perfis podem diferir dos mostrados.

   ![Informações da etapa](assets/Geo_installProfiles_dir.png)

1. Use as seguintes etapas para atualizar o [!DNL profile.cfg] arquivo para cada perfil com o qual você deseja usar a análise de big data [!DNL Geography].

   1. Abra o [!DNL Profile Manager].
   1. Clique com o botão direito do mouse na marca de seleção ao lado de [!DNL profile.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção para este arquivo é exibida na [!DNL User] coluna.

   1. Clique com o botão direito do mouse na marca de seleção recém-criada e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A [!DNL profile.cfg] janela é exibida.

   1. Na [!DNL profile.cfg] janela, clique com o botão direito do mouse **[!UICONTROL Directories]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Para adicionar o novo diretório ao final da lista de diretórios, clique com o botão direito do mouse no número ou nome do último diretório na lista e clique em **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digite o nome do novo diretório: [!DNL Geography].
   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção para [!DNL profile.cfg] na [!DNL User] coluna e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe (incluindo o [!DNL Geography] perfil), pois suas alterações são substituídas quando você instala atualizações nesses perfis.

