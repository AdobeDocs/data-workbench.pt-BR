---
description: Normalmente, você deseja adicionar uma DPU do Insight Server a um cluster existente quando a quantidade de dados que deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade da configuração atual do cluster.
solution: Analytics
title: Adicionar uma DPU do servidor Insight a um cluster existente
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---


# Adicionar uma DPU do servidor Insight a um cluster existente{#adding-an-insight-server-dpu-to-an-existing-cluster}

Normalmente, você deseja adicionar uma DPU do Insight Server a um cluster existente quando a quantidade de dados que deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade da configuração atual do cluster.

## Atualização dos arquivos de configuração no servidor Principal {#section-7c9a23754a994d73b722d53f999f0e82}

Em [!DNL Insight], abra o [!DNL Server Files Manager] para o seu principal [!DNL Insight Server] (geralmente um [!DNL Insight Server] FSU) e faça o seguinte para cada DPU que você deseja adicionar ao cluster:

1. Edite o arquivo de endereço no principal [!DNL Insight Server] para incluir o nome e o endereço da nova DPU, conforme descrito em [Adicionar os Servidores de Informações de Processamento ao Arquivo](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)de Endereço. Adicione o nome e o endereço da nova DPU ao grupo no qual o cluster atual [!DNL Insight Servers] está listado.

1. Edite o arquivo de controle de acesso no principal [!DNL Insight Server] para incluir o endereço IP da nova DPU, conforme descrito em [Atualização do arquivo de Controle de acesso para um cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Instalação da nova DPU do Insight Server {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Esta tarefa se aplica somente ao Windows de 32 bits.

1. Copie os seguintes diretórios de uma das DPUs atuais no cluster para a nova DPU:

   * [!DNL Insight Server] diretório de instalação/bin/
   * [!DNL Insight Server] diretório de instalação/Certificados/
   * [!DNL Insight Server] diretório/Componentes/

1. Baixe e instale o certificado digital para a nova DPU, conforme descrito em [Download e instalação de certificados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitais.
1. Defina os parâmetros de utilização da memória do Windows na nova DPU.
1. Registre-se [!DNL Insight Server] como um serviço do Windows na nova máquina DPU, conforme descrito em [Registrar o Insight Server como um Serviço](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)do Windows.

1. Verifique os logs de rastreamento para verificar se a DPU está sincronizando com a principal [!DNL Insight Server].
1. Repita as etapas de 1 a 6 para cada DPU adicional que você está adicionando ao cluster.

## Adicionando a nova DPU do Insight Server aos servidores de processamento do Perfil Dataset {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Se a nova DPU processar o mesmo conjunto de dados que as outras DPUs no cluster, adicione o nome comum da nova DPU ao [!DNL profile.cfg] arquivo no principal [!DNL Insight Server] conforme descrito em [Especificação dos Servidores de Processamento no Perfil.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
