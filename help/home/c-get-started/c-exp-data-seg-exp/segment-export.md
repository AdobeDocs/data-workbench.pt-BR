---
description: Exportar segmentos usando o assistente de exportação de segmentos
title: Assistente de exportação de segmentos
uuid: 705bdf00-54e5-4992-8978-91afda8c7543
exl-id: 6f42c5c6-a158-4ddd-8949-4ef55a44ed1c
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 6%

---

# Assistente de exportação de segmentos{#segment-export-wizard}

Exportar segmentos usando o assistente de exportação de segmentos

O assistente de exportação de segmentos fornece um processo passo a passo para configurar e exportar segmentos em vez de [exportar segmentos de uma tabela detalhada](https://experienceleague.adobe.com/docs/data-workbench/using/client/export-data/c-sgmt-expt.html).

## Exportar segmentos usando o assistente {#section-b30f2699dbc7490bad18512b91cb0cb3}

Para abrir o assistente, clique com o botão direito do mouse em um espaço de trabalho e selecione **Admin** > **Assistentes** > **Assistente de exportação de segmentos**.

>[!NOTE]
>
>Somente os segmentos aplicados antes da abertura do assistente serão capturados. Além disso, as exportações de segmento criadas no assistente não podem gerar comandos externos.

1. Selecione os vários níveis principais das dimensões e métricas a serem adicionadas à exportação.

   Os níveis exibidos dependem do perfil selecionado. Você pode selecionar vários níveis de dimensão com base no perfil.

   ![](assets/seg_wizard_1.png)

1. Clique em **Avançar**.
1. Selecione o Dimension e as Métricas para os níveis selecionados.

   Por exemplo, depois de selecionar Exibição de página como o nível principal, você pode selecionar as dimensões e métricas secundárias disponíveis para serem exportadas.

1. Clique em **Avançar**.

   ![](assets/seg_wizard_2.png)

   ![](assets/seg_wizard_2_1.png)

1. Selecione o formato de exportação e insira um nome para o arquivo de exportação.

   ![](assets/seg_wizard_3.png)

   Os tipos CSV, TSV, Exportação de segmentos e Exportação de segmentos com cabeçalho não precisam de configuração extra. No entanto, a exportação de perfis e públicos-alvo, o serviço de registro personalizado e a exportação do Adobe Target precisam ser configurados na etapa 3. Por exemplo, consulte os campos de configuração para Perfis e Exportação de público-alvo. Configure esses tipos de exportação e clique em **Next**.

   ![](assets/seg_wizard_3_1.png)

   ![](assets/seg_wizard_3_2.png)

   ![](assets/seg_wizard_3_3.png)

1. Configure o tipo de exportação selecionado.

   Cabeçalho — Se o Cabeçalho for Verdadeiro, nomeie o campo **Arquivo de Saída**.

   Campo de escape — Definido como **True** ou **False**.

   Ordem dos Campos — Selecione um campo e mova para cima ou para baixo para definir a ordem no arquivo de exportação.

   ![](assets/seg_wizard_4.png)

   Clique em **Avançar**.

1. Visualize o Nível e os filtros aplicados nesta caixa de diálogo. Clique em **Avançar**. ![](assets/seg_wizard_5.png)

1. Se **CSV**, **TSV**, **Exportação de segmento** ou **Exportação de segmento com cabeçalho** estiver selecionada, há três opções:

   Exportação Genérica - O arquivo de saída será gerado pelo servidor na pasta Servidor/Exportação.

   ![](assets/seg_wizard_6.png)

   Exportação de FTP - O arquivo de saída será transferido para o servidor selecionado. (A lista do servidor será extraída do arquivo FTPServerInfo.cfg.)

   ![](assets/seg_wizard_6_1.png)

   Exportação SFTP - O arquivo de saída será transferido com segurança para o servidor selecionado.

1. Clique em **Avançar**

   **Observação:** se o tipo de exportação selecionado for  **Perfis e exportação** de público-alvo, serviço de registro  **personalizado** e exportação do  **Adobe Target**, o texto será estático com base na exportação selecionada.

1. Configure os parâmetros de agendamento.

   **Um** Shotcan pode ser definido como Verdadeiro ou Falso.

   **O Advanced** Scheduling pode ser ativado ou desativado clicando no botão Advanced Scheduling Configuration.

   ![](assets/seg_wizard_7.png)

   Como exportar a partir da Tabela de detalhes, um instantâneo desaparecerá se a Configuração avançada estiver ativada. Clique em **Avançar**.

1. Visualize o arquivo de exportação e clique em **Executar Exportação**.

   ![](assets/seg_wizard_8.png)

   ![](assets/seg_wizard_8_1.png)

Os seguintes tipos de exportações estão disponíveis usando o assistente:

**Tipos de exportação de segmento**

* Genérico
* FTP
* SFTP

**Exportar segmento com cabeçalho**

* Genérico
* FTP
* SFTP

**Exportação de CSV**

* Genérico
* FTP
* SFTP

**Exportação de TSV**

* Genérico
* FTP
* SFTP
