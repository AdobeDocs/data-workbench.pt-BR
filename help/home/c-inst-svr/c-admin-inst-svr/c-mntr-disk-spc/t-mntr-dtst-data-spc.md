---
description: Informações sobre o monitoramento do conjunto de dados e a adição de novos locais para o armazenamento de dados do conjunto de dados.
title: Monitorar o espaço de dados do conjunto de dados
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# Monitorar o espaço de dados do conjunto de dados{#monitoring-dataset-data-space}

{{eol}}

Informações sobre o monitoramento do conjunto de dados e a adição de novos locais para o armazenamento de dados do conjunto de dados.

**Frequência recomendada:** A cada 5-10 minutos

Por padrão, [!DNL Insight Server] grava seu conjunto de dados no [!DNL temp.db] na mesma unidade da [!DNL Insight Server] arquivos de programa na unidade de processamento de dados. A quantidade de dados do conjunto de dados por [!DNL Insight Server] A máquina é limitada ao seguinte, consoante o que ocorrer primeiro:

* Quinhentos (500) milhões de registros de entrada de dados para esse conjunto de dados
* Quinhentos (500) GB de dados do conjunto de dados armazenados
* Um (1) MB de dados do conjunto de dados armazenados por qualquer dimensão de nível raiz (por exemplo, 5.000 registros por visitante em uma média de 200 bytes por registro)

Se desejar [!DNL Insight Server] para manter o conjunto de dados em uma unidade diferente ou se a quantidade de dados que você espera coletar exigir o uso de várias unidades, você deve atualizar o arquivo de configuração Arquivos de Disco ( [!DNL Disk Files.cfg]) para especificar onde deseja [!DNL Insight Server] para gravar o [!DNL temp.db] arquivo(s). O [!DNL Disk Files.cfg] O arquivo lista os arquivos de disco (um vetor de sequências de caracteres) e especifica o local dos dados do conjunto de dados usados por [!DNL Insight Server] durante o reprocessamento e a operação. Geralmente há um arquivo por unidade física.

>[!NOTE]
>
>O conteúdo do [!DNL Disk Files.cfg] O arquivo pode ter sido modificado durante a instalação [!DNL Insight Server]. Para obter mais informações, consulte [Configurar a localização do conjunto de dados (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Para adicionar novos locais para armazenamento de dados do conjunto de dados**

1. Em [!DNL Insight], no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] você deseja configurar e clicar em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique em **[!UICONTROL Components]** para visualizar seu conteúdo. O [!DNL Disk Files.cfg] O arquivo está localizado dentro desse diretório.
1. Clique com o botão direito do mouse na marca de seleção no *nome do servidor* coluna para [!DNL Disk Files.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece no [!DNL Temp] coluna para [!DNL Disk Files.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. No [!DNL Disk Files.cfg] , clique em **[!UICONTROL component]** para visualizar seu conteúdo.

   ![Informações da etapa](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >O parâmetro Detect Disk Corruption é definido como true por padrão. O parâmetro Tamanho do Cache de Disco (MB) controla a quantidade de memória que [!DNL Insight Server] O usa o para aumentar a velocidade de acesso ao disco e é definido como 128 por padrão. Entre em contato com o Adobe antes de alterar qualquer um desses parâmetros.

1. Para alterar os arquivos de disco na [!DNL Insight Server] máquina, clique com o botão direito do mouse **[!UICONTROL Disk Files]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Para excluir um arquivo de disco, clique com o botão direito do mouse no número do arquivo de disco e clique em **[!UICONTROL Remove]**.

1. Para o novo arquivo de disco, insira o diretório e o nome do arquivo a ser usado por [!DNL Insight Server] durante o reprocessamento e a operação.

   ![Informações da etapa](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >O parâmetro Detect Disk Corruption é definido como true por padrão. O parâmetro Tamanho do Cache de Disco (MB) controla a quantidade de memória que [!DNL Insight Server] O usa o para aumentar a velocidade de acesso ao disco e é definido como 128 por padrão. Entre em contato com o Adobe antes de alterar qualquer um desses parâmetros.

1. Salve as alterações no servidor fazendo o seguinte:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. No [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo no [!DNL Temp] e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
