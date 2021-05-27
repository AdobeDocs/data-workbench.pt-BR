---
description: Quaisquer dados que você deseja exportar devem ser definidos como uma dimensão dentro do perfil.
title: Criar dimensões para usar com exportação de segmentos
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 8%

---

# Criar dimensões para usar com exportação de segmentos{#create-dimensions-for-use-with-segment-export}

Quaisquer dados que você deseja exportar devem ser definidos como uma dimensão dentro do perfil.

Se a dimensão ainda não existir no perfil, você deve criá-la. Você pode criar dimensões usando qualquer um dos métodos a seguir:

* Adicione uma dimensão ao arquivo [!DNL Transformation.cfg]. Consulte o *Guia de configuração do conjunto de dados*.

* Crie um novo arquivo [!DNL .dim]. Consulte [Criação e edição de Dimension derivados](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* Faça seleções em uma visualização, como um mapa de processos ou um segmento, e salve as seleções como uma dimensão. Consulte [Salvando Dimension dos mapas de processo](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) e [Criando Dimension de segmento](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

Exportar um campo de dados, como ID de rastreamento ou Endereço de email (que pode ter muitos elementos), requer a criação de uma dimensão denormal que armazene as sequências de caracteres brutas de dados.

Para obter mais informações sobre dimensões denormal, consulte o *Guia de Configuração de Conjunto de Dados*.
