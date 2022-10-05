---
description: Normalmente, você deseja adicionar uma DPU do servidor Insight a um cluster existente quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade da configuração atual do cluster.
title: Adicionar uma DPU do servidor Insight a um cluster existente
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# Adicionar uma DPU do servidor Insight a um cluster existente{#adding-an-insight-server-dpu-to-an-existing-cluster}

{{eol}}

Normalmente, você deseja adicionar uma DPU do servidor Insight a um cluster existente quando a quantidade de dados que você deseja processar e tornar acessível aos usuários do Insight e do Relatório excede a capacidade da configuração atual do cluster.

## Atualização dos arquivos de configuração no servidor Principal {#section-7c9a23754a994d73b722d53f999f0e82}

Em [!DNL Insight], abra o [!DNL Server Files Manager] para seu principal [!DNL Insight Server] (normalmente um [!DNL Insight Server] FSU) e faça o seguinte para cada DPU que deseja adicionar ao cluster:

1. Edite o arquivo de endereço na principal [!DNL Insight Server] para incluir o nome e o endereço da nova DPU, conforme descrito em [Adicionar os servidores Insight de processamento ao arquivo de endereço](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Adicione o nome e o endereço da nova DPU ao grupo no qual o cluster atual [!DNL Insight Servers] estão listadas.

1. Edite o arquivo de controle de acesso na principal [!DNL Insight Server] para incluir o endereço IP da nova DPU, conforme descrito em [Atualização do Arquivo de Controle de Acesso para um Cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Instalar a nova DPU do servidor Insight {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Esta tarefa aplica-se apenas ao Windows 32 bits.

1. Copie os seguintes diretórios de uma das DPUs atuais no cluster para a nova DPU:

   * [!DNL Insight Server] diretório de instalação/bin/
   * [!DNL Insight Server] diretório de instalação/Certificados/
   * [!DNL Insight Server] diretório/Componentes/

1. Baixe e instale o certificado digital para a nova DPU, conforme descrito em [Baixar e instalar certificados digitais](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Defina os parâmetros de utilização da memória do Windows na nova DPU.
1. Registrar [!DNL Insight Server] como um serviço do Windows na nova máquina DPU, conforme descrito em [Registrar o servidor Insight como um serviço do Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Verifique os logs de rastreamento para verificar se a DPU está sincronizando com o principal [!DNL Insight Server].
1. Repita as etapas de 1 a 6 para cada DPU adicional que você está adicionando ao cluster.

## Adicionar a nova DPU do servidor Insight aos servidores de processamento do perfil do conjunto de dados {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Se a nova DPU processar o mesmo conjunto de dados que as outras DPUs no cluster, adicione o nome comum da nova DPU à [!DNL profile.cfg] arquivo no principal [!DNL Insight Server] conforme descrito em [Especificação dos servidores de processamento no Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
