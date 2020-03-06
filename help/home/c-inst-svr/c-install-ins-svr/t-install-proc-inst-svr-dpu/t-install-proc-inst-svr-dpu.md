---
description: Instruções detalhadas para instalar uma DPU do Insight Server e configurá-la para uso administrativo.
solution: Insight
title: Procedimentos de instalação para uma DPU do Insight Server
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procedimentos de instalação para uma DPU do Insight Server{#installation-procedures-for-an-insight-server-dpu}

Instruções detalhadas para instalar uma DPU do Insight Server e configurá-la para uso administrativo.

Para instalar e configurar uma [!DNL Insight Server] DPU, você deve concluir as seguintes tarefas em ordem:

1. Instale os arquivos de [!DNL Insight Server] programa. Consulte [Instalação dos arquivos](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)do programa do Insight Server.
1. Download and install the [!DNL Insight Server] digital certificate. Consulte [Download e instalação de certificados](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitais.
1. Verifique as configurações de porta no [!DNL Communications.cfg] arquivo. Consulte [Verificando as configurações](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)da porta.
1. Modifique o [!DNL Access Control.cfg] arquivo para permitir acesso administrativo a [!DNL Insight Server] partir de [!DNL Insight]. Consulte [Atualização do arquivo](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)de controle de acesso.
1. Modifique o [!DNL server.address] arquivo para definir o local de rede do servidor. Consulte [Definindo o Local](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)de Rede do Servidor.
1. (Opcional) Modifique o [!DNL Disk Files.cfg] arquivo para especificar onde os dados processados são armazenados. Consulte [Configuração da localização do conjunto de dados (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Instale os perfis e arquivos de pesquisa. Consulte [Instalação de perfis e arquivos](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc)de pesquisa.
1. Defina os parâmetros de utilização da memória do Microsoft Windows.
1. Registre-se [!DNL Insight Server] como um serviço do Windows. Consulte [Registrando o Insight Server como um Serviço](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)do Windows.
