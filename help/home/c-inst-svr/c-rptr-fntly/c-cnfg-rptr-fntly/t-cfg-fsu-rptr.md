---
description: Instruções para instalar e configurar uma FSU do servidor Insight para uso com o Repetidor.
title: Configurar uma FSU do servidor Insight para repetidor
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# Configurar uma FSU do servidor Insight para repetidor{#configuring-an-insight-server-fsu-for-repeater}

{{eol}}

Instruções para instalar e configurar uma FSU do servidor Insight para uso com o Repetidor.

Conclua as tarefas a seguir em ordem. Quaisquer exceções ou alterações que você deve fazer para que a variável [!DNL Insight Server] A FSU pode ser usada como um servidor repetidor é anotada após cada etapa.

1. Instale o [!DNL Insight Server] arquivos de programa, conforme descrito em [Instalar o servidor Insight](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Como a máquina na qual você instala esses arquivos é usada para executar o Repetidor, é útil dar ao diretório de instalação um nome descritivo como [!DNL D:\Adobe\Repeater].

1. Instale o [!DNL Insight Server] certificado digital conforme descrito em [Baixar e instalar certificados digitais](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   Depois de fazer logon no Adobe License Server, lembre-se de procurar o nome do certificado que corresponde ao nome comum do servidor do computador repetidor designado.

1. Verifique as configurações da porta no [!DNL Communications.cfg] como descrito em [Verificar as configurações de porta](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   Se as portas atribuídas (Porta e Porta SSL) forem usadas por outro processo em execução na mesma máquina, você deverá alterar as atribuições de porta para um par não utilizado.

1. Se necessário, altere o diretório de log para a variável [!DNL Sensor] dados a serem coletados e armazenados neste computador. Para obter instruções, consulte [Monitorar o espaço de dados do evento](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. Modifique o [!DNL Access Control.cfg] para permitir acesso administrativo ao [!DNL Insight Server] from [!DNL Insight] conforme descrito em [Atualizar o arquivo de controle de acesso](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifique o [!DNL server.address] para definir o local de rede do servidor, conforme definido em [Definir o local de rede do servidor](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. Defina os parâmetros de utilização da memória do Windows.
1. Registrar [!DNL Insight Server] como um serviço do Windows conforme descrito em [Registrar o servidor Insight como um serviço do Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
