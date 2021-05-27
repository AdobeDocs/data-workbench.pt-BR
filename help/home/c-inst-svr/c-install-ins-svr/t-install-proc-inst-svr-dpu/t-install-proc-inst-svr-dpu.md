---
description: Instruções detalhadas para instalar uma DPU do servidor Insight e configurá-la para uso administrativo.
title: Procedimentos de instalação para uma DPU do servidor Insight
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
exl-id: 0bdfb598-d7eb-4e49-8d9b-4f362c3a62e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Procedimentos de instalação para uma DPU do servidor Insight{#installation-procedures-for-an-insight-server-dpu}

Instruções detalhadas para instalar uma DPU do servidor Insight e configurá-la para uso administrativo.

Para instalar e configurar uma DPU [!DNL Insight Server], você deve concluir as seguintes tarefas em ordem:

1. Instale os arquivos do programa [!DNL Insight Server]. Consulte [Instalar os arquivos de programa do servidor Insight](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Baixe e instale o certificado digital [!DNL Insight Server]. Consulte [Download e instalação de certificados digitais](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Verifique as configurações da porta no arquivo [!DNL Communications.cfg]. Consulte [Verificando as configurações de porta](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. Modifique o arquivo [!DNL Access Control.cfg] para permitir acesso administrativo a [!DNL Insight Server] de [!DNL Insight]. Consulte [Atualizando o Arquivo de Controle de Acesso](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifique o arquivo [!DNL server.address] para definir o local de rede do servidor. Consulte [Definindo o Local de Rede do Servidor](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. (Opcional) Modifique o arquivo [!DNL Disk Files.cfg] para especificar onde os dados processados são armazenados. Consulte [Configurar a localização do conjunto de dados (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Instale os perfis e os arquivos de pesquisa. Consulte [Instalar perfis e arquivos de pesquisa](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Defina os parâmetros de utilização da memória do Microsoft Windows.
1. Registre [!DNL Insight Server] como um serviço do Windows. Consulte [Registrar o servidor Insight como um serviço do Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
