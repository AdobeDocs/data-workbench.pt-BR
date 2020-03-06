---
description: Atualização de componentes do servidor para o Análise de big data 6.2 e 6.2.2.
title: Atualização do servidor DWB 6.1 para 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Atualização do servidor DWB: 6.1 a 6.2{#dwb-server-upgrade-to}

Atualização de componentes do servidor para o Análise de big data 6.2 e 6.2.2.

## Problemas de atualização da versão 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* O perfil de Atribuição é configurado para usuários que implementaram o perfil do Adobe SC para empregar o feed de dados do Analytics (SC/Insight). Por padrão, os eventos de Marketing e Conversão são empregados como interações padrão avaliadas nos modelos baseados em regras. Consulte [Implantação do perfil](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html) de atribuição para obter mais informações.
* Para usuários da atualização de perfil do Adobe SC para o Análise de big data 6.2, se você não estiver usando as configurações padrão, verifique se o [!DNL x-bot_id] valor no arquivo [!DNL SC Fields.cfg] está sendo decodificado corretamente e se o [!DNL x-bot_id] campo está listado corretamente nos arquivos [!DNL Decoding Instructions.cfg] e nos [!DNL Exclude Hit.cfg] arquivos. Isso só será um problema se você tiver modificado o arquivo de configuração da configuração padrão.
* Se você tiver excluído campos não utilizados no [!DNL Dataset > Log Processing > SC Fields.cfg] arquivo do perfil do Adobe SC, precisará atualizar para acomodar os valores de campo atualizados usados para o perfil de Atribuição (consulte [Implantação do perfil](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html)de atribuição).

## Problemas de atualização da versão 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* Os arquivos **[!UICONTROL Browsers]** e de **[!UICONTROL Operating Systems]** pesquisa não serão atualizados dentro do **[!UICONTROL Traffic]** perfil herdado (por exemplo, [!DNL Lookups\Traffic\Browsers.txt)]. Instead, configuration of the **[!UICONTROL Traffic]** profile will utilize the DeviceAtlas bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) to provide this configuration information.
* O Análise de big data 6.2.1 será a última versão a oferecer o download de um aplicativo de 32 bits. Todos os futuros downloads de aplicativos do cliente deverão ter 64 bits, e será necessário o Windows 7 ou versão mais recente. Limitações de memória do aplicativo de 32 bits são endereçadas com a introdução do aplicativo de 64 bits, a começar pela versão 6.1.

>[!NOTE]
>
>A versão de 32 bits do aplicativo cliente Análise de big data pode apresentar possíveis problemas relacionados às limitações de memória ao executar modelos preditivos usando os recursos de agrupamento e pontuação.

