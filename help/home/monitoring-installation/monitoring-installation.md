---
description: Instruções para instalar o Perfil de monitoramento do Data Workbench.
title: Instalar o perfil de monitoramento
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# Instalar o perfil de monitoramento{#installing-the-monitoring-profile}

Instruções para instalar o Perfil de monitoramento do Data Workbench.

## Etapas de instalação {#section-d4355dbea8a447f48ab168db6ccff612}

1. Configure uma nova instância do Sensor como se ela fosse ser usada para a coleta de dados de páginas da Web com tags. Certifique-se de que o arquivo zip.gif esteja na raiz do documento do servidor Web do Sensor. O sensor pode ser executado no mesmo host que os perfis do monitor. (Esse não é um problema se estiver usando um arquivo de texto para essa finalidade.)

   >[!NOTE]
   >
   >Essa instância do sensor deve ser dedicada ao recebimento de tráfego somente dos Agentes de monitoramento. Além disso, o Sensor pode ser configurado para ser executado em uma porta diferente se você redefinir o objetivo de um servidor da Web para essa coleção.

1. No arquivo [!DNL txlogd.conf] há a linha padrão:

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Para o aplicativo de Perfil de monitoramento do Data Workbench (ou qualquer implementação de página &quot;marcada&quot;), o tipo de imagem deve ser removido para ser coletado por meio de um arquivo GIF. A linha atualizada é:

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. Copie o [!DNL insight_monitor.zip/insight_monitor_agent] para um local temporário.
1. Atualize o arquivo [!DNL insight_monitor_agent.cfg] para seu ambiente. Siga os comentários dentro do arquivo de configuração:

   **O arquivo de configuração Monitoring:**

   ![](assets/monitor_agent_cfg_sensor.png)

   Defina onde você está coletando todas as informações e forneça o endereço de URL. Isso precisa ser um sensor dedicado e não deve receber tráfego exceto para esse aplicativo.

   ![](assets/monitor_agent_cfg_dump.png)

   Existem caminhos supondo que haja um e: disco. Talvez você queira alterar esse caminho para seu ambiente.

   ![](assets/monitor_agent_cfg_quickcheck.png)

   Às vezes, ao executar um perfil de Transformação, o Data Workbench pode não responder. Esse valor permite enviar um alerta se, três vezes seguidas, o processo não responder. Essa é uma maneira de reduzir alertas falsos positivos.

   ![](assets/monitor_agent_cfg_groups.png)

   É aqui que você define o ambiente e as dimensões do grupo. Isso pode ser diferente de host para host.

   Aqui você pode ver exatamente o que o agente do monitor está fazendo ao visualizar registros de erros neste caminho.![](assets/monitor_agent_cfg_debug.png)

   ![](assets/monitor_agent_cfg_tempdb.png)

   Isso é para usar o db temporário internamente. Ele pode ser alertado ao atingir a capacidade. Isso é diferente do uso do disco físico.

1. Copie a pasta *insight_monitor_agent* para cada host DPU e FSU que executa o servidor do Data Workbench. O local padrão, conforme indicado no arquivo de configuração, é [!DNL e:\insight_monitor_agent], mas você pode alterar esse local.

1. Adicione uma tarefa agendada do Windows para chamar o agente a cada 10 minutos (esse período é considerado nos cálculos de taxa de processamento). O programa é [!DNL e:insight_monitor/insight_monitor_agent.exe]. O argumento é config-file e:\insight_monitor\insight_monitor.cfg. Comece em e:\insight_monitor. O usuário que está executando a tarefa deve ter permissão para ler/gravar [!DNL e:\insight_monitor] e ler o objeto OLE Win32 [!DNL root\CIMV2] (necessário para determinar o modo de início do serviço do servidor do Data Workbench e verificar a porcentagem de espaço em discos locais)

1. Confirme se o arquivo de VSL está começando a crescer à medida que os registros do monitor são acumulados. Isso levará algum tempo, pois o volume de tráfego será extremamente baixo em uma pequena instalação (a cada 10 minutos o agente envia apenas uma ocorrência para os dados específicos do host, além de uma ocorrência por perfil de processamento).
1. Descompacte insight_monitor.zip\profiles\Insight Historic to a temporary location.
1. Atualize o nome do host em [!DNL profile.cfg], [!DNL dataset\cluster.cfg] e [!DNL dataset\segment export.cfg].

1. Atualize os arquivos para o diretório de perfis do Data Workbench.
1. Atualize o servidor de log e o caminho em [!DNL dataset\log processing.cfg] para o local onde o Sensor VSL está se acumulando.
1. [] Opcionalmente, faça o mesmo com os perfis  [!DNL Insight Profile Status] e  [!DNL Insight Server Status]. Além disso, os perfis de status devem ser reprocessados noturnos com uma janela de dois dias à direita. Adicionar uma tarefa agendada do Windows: O programa é [!DNL e:\insight_monitor\insight_reprocess.exe]. O argumento é [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Deixe [!DNL start in] em branco. Adicione outra tarefa agendada para *&quot;status do servidor insight&quot;*. *insight_reprocess.* existe a necessidade de acesso de leitura/gravação ao  *log processing.* cfgpara atualizar o horário de início.

1. Além disso, os perfis de status devem ser reprocessados noturnos com uma janela de dois dias à direita. Adicionar uma tarefa agendada do Windows: O programa é *e:\insight_monitor\insight_reprocess.exe*. O argumento é - [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Deixe *iniciar em* em branco. Adicione outra tarefa agendada para [!DNL "insight server status"]. [!DNL insight_reprocess.exe] requer acesso de leitura/gravação  [!DNL log processing.cfg] para atualizar a hora de início. Confirme se cada perfil está lendo o monitor VSL à medida que ele é acumulado. Mais uma vez, isso levará algum tempo — provavelmente horas — devido ao volume extremamente baixo.

## Notas de instalação {#section-17722441ab0046fcbcb46b957d56230a}

* **Configuração do perfil de monitoramento em um ambiente** de teste licenciado. O pacote de ambiente de teste é incluído com sua implementação do Data Workbench, permitindo instalar e configurar o aplicativo. Se estiver instalando em um servidor FSU ou DPU de produção, será necessário configurar o servidor para ser executado em uma porta separada.
* **Implantação de um novo sensor especificamente para o perfil** de monitoramento. Será necessário instalar uma nova instância do Sensor no servidor que executa o Perfil de monitoramento. Isso ocorre além da instância de produção do Sensor. (Não há custo adicional para instalar o Sensor em um servidor de produção ou não de produção especificamente para o Perfil de monitoramento.)
* **Desative o agente de monitor durante a manutenção** do Data Workbench. Para evitar a poluição do tempo de atividade e das métricas de desempenho, você pode definir o modo de início do serviço como manual para o serviço InsightServer (Omniture Insight Server). Um comando útil do PowerShell é *set-service -name insightserver -startuptype manual*. Defina-o novamente como automático após a manutenção: *set-service -name insightserver -startuptype automatic*. Outra opção é desativar temporariamente a tarefa agendada do agente de monitor.
* **Os perfis de status precisam de uma** janela à direita para soltar hosts e perfis antigos, bem como mapeamentos de perfil de host antigos. No entanto, se a quantidade de dados do evento for tão pequena que o Data Workbench não o armazenará em buffer, talvez seja necessário estender o tamanho da janela um pouco para processá-la.
* **O agente coleta o status** detalhado geral e o mais antigo de tempo do Data Workbench, que é reportado no horário do host local, assumindo que os carimbos de hora do log de dados do evento estão em UTC (como em arquivos de VSL). Se os carimbos de data e hora dos dados do evento estiverem em um fuso horário que não seja UTC, a hora de início será deslocada no perfil de status do perfil de insight resultante. Se **todos** dos carimbos de data e hora do evento estiverem no mesmo fuso horário, você poderá adicionar esse deslocamento a *Perfil do Insight Status\metrics\as of delay minutes.metric*.

* **Duas novas dimensões foram introduzidas para ajudar o cliente a agrupar seus servidores se eles estiverem em estados** diferentes, como produção, armazenamento temporário, servidores de teste e servidores em outros estados. Por exemplo, se você estiver procurando por &quot;tempo de atividade&quot;, você verá os servidores somente no modo de produção. Como resultado, a dimensão Grupo é apenas outra maneira de agrupar servidores arbitrariamente para suas necessidades. Por exemplo, no arquivo de Configuração de monitoramento, é possível definir qual host seu departamento está oferecendo serviço, como Operações, Desenvolvimento ou Marketing.
