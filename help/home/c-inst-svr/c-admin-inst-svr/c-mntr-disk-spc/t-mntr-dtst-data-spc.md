---
description: Informações sobre monitoramento de conjuntos de dados e adição de novos locais para armazenamento de dados de conjuntos de dados.
solution: Analytics
title: Monitorar o espaço de dados do conjunto de dados
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---


# Monitorar o espaço de dados do conjunto de dados{#monitoring-dataset-data-space}

Informações sobre monitoramento de conjuntos de dados e adição de novos locais para armazenamento de dados de conjuntos de dados.

**Frequência recomendada:** A cada 5 a 10 minutos

Por padrão, [!DNL Insight Server] grava seu conjunto de dados no [!DNL temp.db] arquivo na mesma unidade dos arquivos de [!DNL Insight Server] programa na unidade de processamento de dados. A quantidade de dados do conjunto de dados por [!DNL Insight Server] máquina é limitada ao seguinte, o que ocorrer primeiro:

* Quinhentos (500) milhões de registros de entrada de dados para esse conjunto de dados
* Quinhentos (500) GB de dados de conjunto de dados armazenados
* Um (1) MB de dados de conjunto de dados armazenados por qualquer dimensão de nível raiz (por exemplo, 5.000 registros por Visitante em uma média de 200 bytes por registro)

Se quiser manter [!DNL Insight Server] o conjunto de dados em uma unidade diferente, ou se a quantidade de dados que espera coletar exigir o uso de várias unidades, atualize o arquivo de configuração Arquivos de Disco ( [!DNL Disk Files.cfg]) para especificar onde deseja [!DNL Insight Server] gravar o(s) [!DNL temp.db] arquivo(s). O [!DNL Disk Files.cfg] arquivo lista os arquivos de disco (um vetor de sequências de caracteres) e especifica o local dos dados do conjunto de dados usados [!DNL Insight Server] durante o reprocessamento e a operação. Geralmente há um arquivo por unidade física.

>[!NOTE]
>
>O conteúdo do [!DNL Disk Files.cfg] arquivo pode ter sido modificado durante a instalação [!DNL Insight Server]. Para obter mais informações, consulte [Configuração da localização do conjunto de dados (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Para adicionar novos locais ao armazenamento de dados do conjunto de dados**

1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], clique **[!UICONTROL Components]** para visualização do conteúdo. O [!DNL Disk Files.cfg] arquivo está localizado dentro deste diretório.
1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor para [!DNL Disk Files.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Disk Files.cfg].
1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Na [!DNL Disk Files.cfg] janela, clique **[!UICONTROL component]** para visualização do conteúdo.

   ![Informações da etapa](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >O parâmetro Detect Disk Corruption (Detectar corrupção de disco) é definido como true por padrão. O parâmetro Tamanho do cache de disco (MB) controla a quantidade de memória que [!DNL Insight Server] usa para aumentar a velocidade de acesso ao disco e é definido como 128 por padrão. Entre em contato com a Adobe antes de alterar qualquer um desses parâmetros.

1. Para alterar os arquivos de disco na [!DNL Insight Server] máquina, clique com o botão direito do mouse **[!UICONTROL Disk Files]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Para excluir um arquivo de disco, clique com o botão direito do mouse no número do arquivo de disco e clique em **[!UICONTROL Remove]**.

1. Para o novo arquivo de disco, digite o diretório e o nome do arquivo a ser usado [!DNL Insight Server] durante o reprocessamento e a operação.

   ![Informações da etapa](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >O parâmetro Detect Disk Corruption (Detectar corrupção de disco) é definido como true por padrão. O parâmetro Tamanho do cache de disco (MB) controla a quantidade de memória que [!DNL Insight Server] usa para aumentar a velocidade de acesso ao disco e é definido como 128 por padrão. Entre em contato com a Adobe antes de alterar qualquer um desses parâmetros.

1. Salve as alterações no servidor da seguinte maneira:

   1. Clique com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

   1. Na [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL Temp] coluna e selecione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

