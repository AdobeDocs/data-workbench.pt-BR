---
description: Exportar segmentos usando o assistente de exportação de segmentos
title: Assistente de exportação de segmentos
uuid: 705bdf00-54e5-4992-8978-91afda8c7543
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Segment export wizard{#segment-export-wizard}

Exportar segmentos usando o assistente de exportação de segmentos

O assistente de exportação de segmentos fornece um processo passo a passo para configurar e exportar segmentos, em vez de [exportar segmentos de uma tabela](https://docs.adobe.com/content/help/en/data-workbench/using/client/export-data/c-sgmt-expt.html)detalhada.

## Exportar segmentos usando o assistente {#section-b30f2699dbc7490bad18512b91cb0cb3}

Para abrir o assistente, clique com o botão direito do mouse em uma área de trabalho e selecione **Admin** > **Assistentes** > Assistente **de exportação** de segmento.

>[!NOTE]
>
>Somente os segmentos aplicados antes da abertura do assistente serão capturados. Além disso, as exportações de segmento criadas a partir do assistente não podem gerar comandos externos.

1. Selecione os vários níveis principais das dimensões e métricas a serem adicionadas à sua exportação.

   Os níveis exibidos dependem do perfil selecionado. É possível selecionar vários níveis de dimensão com base no perfil.

   ![](assets/seg_wizard_1.png)

1. Clique em **Próximo**.
1. Selecione a Dimensão e as Métricas para os níveis selecionados.

   Por exemplo, depois de selecionar Exibição de página como o nível pai, você pode selecionar as dimensões e métricas secundárias disponíveis para serem exportadas.

1. Clique em **Próximo**.

   ![](assets/seg_wizard_2.png)

   ![](assets/seg_wizard_2_1.png)

1. Selecione o formato de exportação e digite um nome para o arquivo de exportação.

   ![](assets/seg_wizard_3.png)

   Os tipos CSV, TSV, Exportação de segmentos e Exportação de segmentos com cabeçalho não precisam de configuração extra. No entanto, os Perfis e a Exportação de público-alvo, o Serviço de registro personalizado e o Adobe Target Export precisam ser configurados na Etapa 3. Por exemplo, consulte os campos de configuração para Perfis e Exportação de público-alvo. Configure esses tipos de exportação e clique em **Avançar**.

   ![](assets/seg_wizard_3_1.png)

   ![](assets/seg_wizard_3_2.png)

   ![](assets/seg_wizard_3_3.png)

1. Configure o tipo de exportação selecionado.

   Cabeçalho — Se o Cabeçalho for Verdadeiro, nomeie o campo Arquivo **de** Saída.

   Campo de escape — definido como **Verdadeiro** ou **Falso**.

   Ordem dos campos — Selecione um campo e mova-se para cima ou para baixo para definir a ordem no arquivo de exportação.

   ![](assets/seg_wizard_4.png)

   Clique em **Próximo**.

1. Visualize o Nível e os filtros aplicados nesta caixa de diálogo. Clique em **Próximo**. ![](assets/seg_wizard_5.png)

1. Se **CSV**, **TSV**, Exportação **de** segmento ou Exportação de **segmento com cabeçalho** estiver selecionado, há três opções:

   Exportação genérica - o arquivo de saída será gerado pelo servidor na pasta Servidor/Exportação.

   ![](assets/seg_wizard_6.png)

   Exportação FTP - o arquivo de saída será transferido para o servidor selecionado. (A lista do servidor será selecionada do arquivo FTPServerInfo.cfg.)

   ![](assets/seg_wizard_6_1.png)

   Exportação SFTP - o arquivo de saída será transferido com segurança para o servidor selecionado.

1. Clique em **Próximo**

   **Observação:** Se o tipo de exportação selecionado for **Perfis e Exportação** de público-alvo, Serviço **de registro** personalizado e Exportação **do** Adobe Target, o texto será estático com base na exportação selecionada.

1. Configure os parâmetros de agendamento.

   **Uma foto** pode ser definida como Verdadeiro ou Falso.

   **O Advanced Scheduling** pode ser ativado ou desativado clicando-se no botão Advanced Scheduling Configuration (Configuração avançada de agendamento).

   ![](assets/seg_wizard_7.png)

   Como exportar da Tabela de detalhes, uma foto desaparecerá se a Configuração avançada estiver ativada. Clique em **Próximo**.

1. Visualize o arquivo de exportação e clique em **Executar exportação**.

   ![](assets/seg_wizard_8.png)

   ![](assets/seg_wizard_8_1.png)

Os seguintes tipos de exportação estão disponíveis usando o assistente:

**Tipos de exportação de segmento**

* Genérico
* FTP
* SFTP

**Exportação de segmento com cabeçalho**

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

