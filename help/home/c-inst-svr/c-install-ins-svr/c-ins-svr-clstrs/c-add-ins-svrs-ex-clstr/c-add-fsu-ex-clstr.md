---
description: Você pode adicionar uma FSU do servidor Insight a um cluster existente se quiser armazenar dados de origem em um servidor de arquivos adicional ou se quiser configurar um backup para o servidor Insight principal.
title: Adicionar uma FSU do servidor Insight a um cluster existente
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Adicionar uma FSU do servidor Insight a um cluster existente{#adding-an-insight-server-fsu-to-an-existing-cluster}

Você pode adicionar uma FSU do servidor Insight a um cluster existente se quiser armazenar dados de origem em um servidor de arquivos adicional ou se quiser configurar um backup para o servidor Insight principal.

Para adicionar uma FSU [!DNL Insight Server] a um cluster existente, você deve executar os seguintes procedimentos:

1. [Atualização dos arquivos de configuração no servidor Principal](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Instalar a nova FSU do servidor Insight](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Configurar a nova FSU do servidor Insight](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Atualizar os arquivos de configuração no servidor Principal {#section-b5f21f2edb35493da4475de2cdeefca1}

Em [!DNL Insight], abra [!DNL Server Files Manager] para seu [!DNL Insight Server] principal (geralmente um [!DNL Insight Server] FSU) e faça o seguinte para cada FSU que deseja adicionar ao cluster:

1. Edite o arquivo de endereço no principal [!DNL Insight Server] para incluir o nome e o endereço do novo FSU, conforme descrito em [Adicionar os servidores Insight de processamento ao arquivo de endereço](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Adicione o nome e o endereço do novo FSU ao grupo no qual o [!DNL Insight Servers] atual do cluster está listado.

1. Edite o arquivo de controle de acesso no principal [!DNL Insight Server] para incluir o endereço IP do novo FSU, conforme descrito em [Atualizando o Arquivo de Controle de Acesso para um Cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Instalar o novo FSU do servidor Insight {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. No FSU atual, crie um arquivo zip do diretório de instalação [!DNL Insight Server] e copie o arquivo para o novo FSU.
1. Descompacte o arquivo no local onde deseja colocar o software [!DNL Insight Server].
1. Baixe e instale o certificado digital para o novo FSU, conforme descrito em [Download e instalação de certificados digitais](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Defina os parâmetros de utilização da memória do Windows no novo FSU.
1. Altere o nome do arquivo [!DNL .address] para refletir o nome da FSU, conforme descrito em [Definição do local de rede do servidor](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. Se a estrutura da unidade no novo FSU for diferente da do FSU principal, você precisará editar o arquivo [!DNL Disk Files.cfg].

   1. Abra o arquivo [!DNL Disk Files.cfg] no novo FSU.
   1. Atualize as configurações para corresponder às unidades da FSU primária, conforme descrito em [Monitorar espaço de dados do conjunto de dados](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Salve o arquivo localmente e no servidor.

1. Registre [!DNL Insight Server] como um serviço do Windows na nova máquina FSU, conforme descrito em [Registrar o Insight Server como um Serviço do Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Repita as etapas de 1 a 6 para cada FSU adicional que você está adicionando ao cluster.

## Configurar a nova FSU do servidor Insight {#section-c39334c5bd754d5b98d41ad094333108}

Os procedimentos a seguir fornecem instruções para tarefas de configuração específicas. Siga as instruções apropriadas para sua implementação da nova FSU.

**Para configurar a FSU para armazenamento de dados de origem**

Se a nova FSU armazenar dados de origem adicionais para o conjunto de dados em execução no cluster, você deverá concluir o processo de configuração do servidor de arquivos conforme descrito em Configurar uma [!DNL Insight Server] Unidade de Servidor de Arquivos no capítulo Arquivo de Configuração de Processamento de Log do *Guia de Configuração do Conjunto de Dados*.

**Para fazer com que a nova FSU faça o backup da  [!DNL Insight Server] FSU principal**

Se quiser fazer do novo FSU o backup do [!DNL Insight Server] principal (que serve como FSU para o cluster), você deve modificar o arquivo de sincronização no novo FSU (backup) para sincronizar com o FSU principal.

1. No FSU [!DNL Insight Server] de backup, use [!DNL Server Files Manager] para copiar o arquivo [!DNL Synchronize.cfg] na pasta [!DNL Components for Processing Servers] para a pasta [!DNL Components].

1. Abra o arquivo [!DNL Synchronize.cfg] (na pasta [!DNL Components]) em [!DNL Insight].

1. Localize o SynchronizeDir que especifica o local do diretório Componentes. Pode haver vários diretórios de sincronização listados em Diretórios, portanto, talvez seja necessário visualizar o conteúdo de muitos deles (clicando no número do servidor) para encontrar o servidor desejado).
1. Edite a entrada SynchronizeDir e adicione uma segunda entrada SynchronizeDir, como mostrado no exemplo abaixo.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Salve o arquivo modificado com um novo nome, como [!DNL FSU_Synchronize.cfg] , para não confundi-lo com os arquivos [!DNL Synchronize.cfg] nos DPUs no cluster.

1. Use o [!DNL Server Files Manager] para salvar a cópia local do arquivo renomeado no servidor. A FSU de backup baixa os arquivos nos diretórios identificados da FSU [!DNL Insight Server] principal e recupera dinamicamente cópias atualizadas desses arquivos da FSU [!DNL Insight Server] principal quando elas são alteradas.
