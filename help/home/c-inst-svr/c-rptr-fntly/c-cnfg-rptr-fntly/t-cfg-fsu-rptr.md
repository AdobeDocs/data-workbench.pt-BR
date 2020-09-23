---
description: Instruções para instalar e configurar um FSU do Insight Server para uso com o Repetidor.
solution: Analytics
title: Configurar uma FSU do servidor Insight para repetidor
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---


# Configurar uma FSU do servidor Insight para repetidor{#configuring-an-insight-server-fsu-for-repeater}

Instruções para instalar e configurar um FSU do Insight Server para uso com o Repetidor.

Conclua as seguintes tarefas em ordem. Quaisquer exceções ou alterações que você deve fazer para que o [!DNL Insight Server] FSU possa ser usado como um servidor repetidor serão anotadas após cada etapa.

1. Instale os arquivos de [!DNL Insight Server] programa conforme descrito em [Instalação do Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Como a máquina na qual você instala esses arquivos é usada para executar o Repeater, é útil fornecer ao diretório de instalação um nome descritivo, como [!DNL D:\Adobe\Repeater].

1. Instale o certificado [!DNL Insight Server] digital conforme descrito em [Download e instalação dos certificados](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitais.

   Depois de fazer logon no Adobe License Server, lembre-se de procurar o nome do certificado que corresponde ao nome comum do servidor da máquina repetidora designada.

1. Verifique as configurações de porta no [!DNL Communications.cfg] arquivo, conforme descrito em [Verificando as configurações](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)de porta.

   Se as portas atribuídas (Porta e Porta SSL) forem usadas por outro processo em execução na mesma máquina, você deverá alterar as atribuições de porta para um par não utilizado.

1. Se necessário, altere o diretório de log para os [!DNL Sensor] dados a serem coletados e armazenados neste computador. Para obter instruções, consulte [Monitoramento do espaço](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)de dados do Evento.
1. Modifique o [!DNL Access Control.cfg] arquivo para permitir acesso administrativo a [!DNL Insight Server] partir de [!DNL Insight] como descrito em [Atualização do arquivo](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)de Controle de acesso.
1. Modifique o [!DNL server.address] arquivo para definir o local de rede do servidor, conforme definido em [Definindo o local](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)de rede do servidor.
1. Defina os parâmetros de utilização da memória do Windows.
1. Registre-se [!DNL Insight Server] como um serviço do Windows conforme descrito em [Registrando o Insight Server como um Serviço](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)do Windows.
