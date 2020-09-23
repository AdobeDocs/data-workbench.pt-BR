---
description: Você pode adicionar um FSU do Insight Server a um cluster existente se quiser armazenar dados de origem em um servidor de arquivos adicional ou se quiser configurar um backup para o principal Insight Server.
solution: Analytics
title: Adicionar uma FSU do servidor Insight a um cluster existente
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---


# Adicionar uma FSU do servidor Insight a um cluster existente{#adding-an-insight-server-fsu-to-an-existing-cluster}

Você pode adicionar um FSU do Insight Server a um cluster existente se quiser armazenar dados de origem em um servidor de arquivos adicional ou se quiser configurar um backup para o principal Insight Server.

Para adicionar um [!DNL Insight Server] FSU a um cluster existente, execute os seguintes procedimentos:

1. [Atualização dos arquivos de configuração no servidor Principal](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Instalação do novo FSU do Insight Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Configuração do novo FSU do Insight Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Atualização dos arquivos de configuração no servidor Principal {#section-b5f21f2edb35493da4475de2cdeefca1}

Em [!DNL Insight], abra o [!DNL Server Files Manager] para seu principal [!DNL Insight Server] (geralmente um [!DNL Insight Server] FSU) e faça o seguinte para cada FSU que você deseja adicionar ao cluster:

1. Edite o arquivo de endereço no principal [!DNL Insight Server] para incluir o nome e o endereço do novo FSU, conforme descrito em [Adicionar os Servidores de Informações de Processamento ao Arquivo](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)de Endereço. Adicione o nome e o endereço do novo FSU ao grupo no qual o cluster atual [!DNL Insight Servers] está listado.

1. Edite o arquivo de controle de acesso no principal [!DNL Insight Server] para incluir o endereço IP do novo FSU, conforme descrito em [Atualização do arquivo de Controle de acesso para um cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Instalação do novo FSU do Insight Server {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. No FSU atual, crie um arquivo zip do diretório de [!DNL Insight Server] instalação e copie o arquivo para o novo FSU.
1. Descompacte o arquivo no local onde deseja colocar o [!DNL Insight Server] software.
1. Baixe e instale o certificado digital para o novo FSU, conforme descrito em [Download e instalação de certificados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitais.
1. Defina os parâmetros de utilização da memória do Windows no novo FSU.
1. Altere o nome do [!DNL .address] arquivo para refletir o nome do FSU, conforme descrito em [Definindo o local](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)de rede do servidor.

1. Se a estrutura da unidade no novo FSU for diferente da do FSU principal, é necessário editar o [!DNL Disk Files.cfg] arquivo.

   1. Abra o [!DNL Disk Files.cfg] arquivo no novo FSU.
   1. Atualize as configurações para que correspondam às unidades do FSU primário, conforme descrito em [Monitoramento do espaço](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03)de dados do conjunto de dados.
   1. Salve o arquivo localmente e no servidor.

1. Registre-se [!DNL Insight Server] como um serviço do Windows na nova máquina FSU, conforme descrito em [Registrar o Insight Server como um Serviço](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)do Windows.

1. Repita as etapas de 1 a 6 para cada FSU adicional que você está adicionando ao cluster.

## Configuração do novo FSU do Insight Server {#section-c39334c5bd754d5b98d41ad094333108}

Os procedimentos a seguir fornecem instruções para tarefas de configuração específicas. Siga as instruções apropriadas para sua implementação do novo FSU.

**Para configurar o FSU para o armazenamento de dados de origem**

Se o novo FSU armazenar dados de origem adicionais para o conjunto de dados em execução no cluster, você deverá concluir o processo de configuração do servidor de arquivos, conforme descrito em Configurando uma Unidade de Servidor de [!DNL Insight Server] Arquivos no capítulo Arquivo de Configuração de Processamento de Log do Guia *de Configuração do* Conjunto de Dados.

**Para fazer o backup do FSU principal no novo FSU[!DNL Insight Server]**

Se desejar tornar o novo FSU o backup para o principal [!DNL Insight Server] (que serve como FSU para o cluster), você deve modificar o arquivo de sincronização no novo FSU (backup) para que ele seja sincronizado com o FSU principal.

1. No [!DNL Insight Server] FSU de backup, use o [!DNL Server Files Manager] para copiar o [!DNL Synchronize.cfg] arquivo na [!DNL Components for Processing Servers] pasta para a [!DNL Components] pasta.

1. Abra o [!DNL Synchronize.cfg] arquivo (na [!DNL Components] pasta) em [!DNL Insight].

1. Localize SynchronizeDir que especifica o local do diretório Componentes. Pode haver vários diretórios de sincronização listados em Diretórios, portanto, talvez seja necessário visualização o conteúdo de muitos deles (clicando no número do servidor) para encontrar o servidor desejado.
1. Edite a entrada SynchronizeDir e adicione uma segunda entrada SynchronizeDir, como mostrado no exemplo abaixo.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Salve o arquivo modificado com um novo nome, como [!DNL FSU_Synchronize.cfg] para não confundi-lo com os [!DNL Synchronize.cfg] arquivos das DPUs no cluster.

1. Use o [!DNL Server Files Manager] para salvar a cópia local do arquivo renomeado no servidor. O FSU de backup baixa os arquivos nos diretórios identificados do FSU principal e recupera dinamicamente cópias atualizadas desses arquivos do FSU principal quando eles são alterados. [!DNL Insight Server] [!DNL Insight Server]

