---
description: Atualização dos componentes do servidor para o Data Workbench 6.2 e 6.2.2.
title: Atualização do servidor DWB 6.1 para 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 18%

---

# Atualização do servidor DWB: 6.1 para 6.2{#dwb-server-upgrade-to}

Atualização dos componentes do servidor para o Data Workbench 6.2 e 6.2.2.

## Problemas de atualização do 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* O perfil Atribuição é configurado para usuários que implementaram o perfil do Adobe SC para empregar o feed de dados do Analytics (SC/Insight). Por padrão, os eventos de Marketing e Conversão são empregados como as interações padrão avaliadas nos modelos baseados em regras. Consulte [Implantação do perfil de atribuição](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en) para obter mais informações.
* Para usuários do perfil do Adobe SC que atualizam para o Data Workbench 6.2, se você não estiver usando as configurações padrão, verifique se o valor [!DNL x-bot_id] no arquivo [!DNL SC Fields.cfg] está sendo decodificado corretamente e se o campo [!DNL x-bot_id] está listado corretamente nos arquivos [!DNL Decoding Instructions.cfg] e [!DNL Exclude Hit.cfg]. Isso só será um problema se você tiver modificado o arquivo de configuração da configuração padrão.
* Se você tiver excluído campos não utilizados no arquivo [!DNL Dataset > Log Processing > SC Fields.cfg] para o perfil do Adobe SC, será necessário atualizar para acomodar os valores de campo atualizados usados para o perfil de Atribuição (consulte [Implantando o Perfil de Atribuição](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)).

## Problemas de atualização do 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* Os arquivos de pesquisa **[!UICONTROL Browsers]** e **[!UICONTROL Operating Systems]** não serão atualizados dentro do perfil herdado **[!UICONTROL Traffic]** (por exemplo, [!DNL Lookups\Traffic\Browsers.txt)]. Em vez disso, a configuração do perfil **[!UICONTROL Traffic]** utilizará o pacote DeviceAtlas ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) para fornecer essas informações de configuração.
* O Análise de big data 6.2.1 será a última versão a oferecer o download de um aplicativo de 32 bits. Todos os futuros downloads de aplicativos do cliente deverão ter 64 bits, e será necessário o Windows 7 ou versão mais recente. Limitações de memória do aplicativo de 32 bits são endereçadas com a introdução do aplicativo de 64 bits, a começar pela versão 6.1.

>[!NOTE]
>
>A versão de 32 bits do aplicativo cliente Data Workbench pode apresentar possíveis problemas relacionados às limitações de memória ao executar modelos preditivos usando os recursos de cluster e pontuação.
