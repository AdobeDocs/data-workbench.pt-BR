---
description: Usando o novo perfil de Atribuição baseado em regras no Data Workbench, é possível analisar rapidamente os eventos de atribuição e atribuir a responsabilidade que resultam em uma conversão bem-sucedida definida por você. O perfil Attribution vem completo com as informações necessárias para que o seu arquiteto de dados configure e estenda seus recursos e inclui espaços de trabalho pré-criados para que seu analista comece a analisar.
title: Perfil de atribuição
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
exl-id: 29946f22-1d39-44ca-9474-13dbe228751c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# Perfil de atribuição{#attribution-profile}

Usando o novo perfil de Atribuição baseado em regras no Data Workbench, é possível analisar rapidamente os eventos de atribuição e atribuir a responsabilidade que resultam em uma conversão bem-sucedida definida por você. O perfil Attribution vem completo com as informações necessárias para que o seu arquiteto de dados configure e estenda seus recursos e inclui espaços de trabalho pré-criados para que seu analista comece a analisar.

O perfil Attribution permite que você ganhe uma nova perspectiva sobre as relações entre seus esforços de marketing e uma geração de cliente líder bem-sucedida ou conversão de vendas. O perfil Attribution ajuda a qualificar as interações que devem receber alocação de crédito para receita realizada ou participação downstream na jornada do cliente. Ele ajuda a identificar o impacto de seus esforços e custos de marketing, permitindo que você analise rapidamente os eventos de atribuição e, em seguida, atribua a responsabilidade pelo primeiro, último toque ou outros eventos que levam a uma venda bem-sucedida.

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>O perfil Atribuição é configurado para uso imediato pelos usuários que implementaram o perfil do Adobe SC que usa o feed de dados do Analytics (SC/Insight). Por padrão, os eventos de Marketing e Conversão são empregados como os tipos padrão de interações avaliadas nos modelos baseados em regras fornecidos.

Consulte [Implantação do perfil de atribuição](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) e [Modelos de atribuição](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d) para obter mais informações.

## Espaços de trabalho de arquitetura e analista {#section-27c6aff70ba147cca6e11451e127afb4}

No perfil de Atribuição, você tem espaços de trabalho de Arquiteto e Analista definidos em guias separadas no workbench.

![](assets/attribution_profile_tabs.png)

**Espaços de trabalho da arquitetura**

Na guia **Attribution**, clique na guia **[!UICONTROL Architect Workspace]** para abrir espaços de trabalho especificamente projetados para configurar seus arquivos de configuração para modelagem básica de atribuição.

![](assets/attribution_profile_arch.png)

A guia Arquitetura inclui espaços de trabalho para percorrer cada um dos arquivos de configuração na pasta do conjunto de dados do perfil. Por exemplo, **[!UICONTROL Attribution Configuration - Step 1]** permite identificar os valores de Atribuição na seção Transformation do arquivo [!DNL profile.cfg].

![](assets/attribution_profile_arch_step1.png)

**Analista** Espaços de trabalhoClique na  **[!UICONTROL Analyst]** **[!UICONTROL Workspaces]** guia para abrir a análise pré-criada dos espaços de trabalho utilizando as dimensões e métricas fornecidas com o perfil Atribuição.

Esses espaços de trabalho são organizados em quatro categorias:

1. **Reportagem básica** Representa um modelo único em um espaço de trabalho.
1. **Os** Relatórios comparativos estenderam as análises ao apresentar vários modelos em uma única visualização.
1. **Os** Relatórios de investigação expandem os modelos de relatórios para apresentar os modelos de atribuição em diferentes formatos. Esta seção também introduz e expõe as taxas de ponderação baseadas na posição.
1. **Os** Relatórios de definição de caminho oferecem visibilidade sobre a jornada de marketing do cliente com várias visualizações de definição de caminho para explorar e expressar totalmente os fluxos de processo e os caminhos de interação

![](assets/attribution_profile_analyst.png)

A guia Analista inclui espaços de trabalho pré-configurados com relatórios. Por exemplo, **[!UICONTROL First Attribution]** permite selecionar na tabela **[!UICONTROL Campaign]** para ver a atribuição **[!UICONTROL Revenue]** baseada em **[!UICONTROL Time]**.

![](assets/attribution_profile_analyst_step1.png)
