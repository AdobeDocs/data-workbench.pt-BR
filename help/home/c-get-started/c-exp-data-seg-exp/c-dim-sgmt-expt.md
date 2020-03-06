---
description: Todos os dados que você deseja exportar devem ser definidos como uma dimensão dentro do perfil.
solution: Analytics
title: Criar dimensões para uso com exportação de segmentos
topic: Data workbench
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Criar dimensões para uso com exportação de segmentos{#create-dimensions-for-use-with-segment-export}

Todos os dados que você deseja exportar devem ser definidos como uma dimensão dentro do perfil.

Se a dimensão ainda não existir no perfil, você deverá criá-la. É possível criar dimensões usando qualquer um dos seguintes métodos:

* Adicione uma dimensão ao [!DNL Transformation.cfg] arquivo. Consulte o Guia *de configuração de* conjuntos de dados.

* Create a new [!DNL .dim] file. Consulte [Criação e edição de dimensões](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)derivadas.

* Faça seleções em uma visualização, como um mapa de processo ou um segmento, e salve as seleções como uma dimensão. Consulte [Salvar dimensões de mapas](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) de processo e [Criar dimensões](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e)de segmento.

Exportar um campo de dados como ID de rastreamento ou Endereço de email (que pode ter muitos elementos) requer a criação de uma dimensão desnormalizada que armazene as sequências de dados não processadas.

Para obter mais informações sobre dimensões desnormalizadas, consulte o Guia *de configuração de* conjuntos de dados.
