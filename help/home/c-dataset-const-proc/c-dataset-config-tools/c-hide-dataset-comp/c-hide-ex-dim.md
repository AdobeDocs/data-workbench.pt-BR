---
description: Você pode usar o parâmetro Oculto ou o parâmetro Mostrar para ocultar dimensões estendidas para que elas não sejam exibidas no menu de dimensão no Data Workbench.
title: Ocultar dimensões estendidas
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# Ocultar dimensões estendidas{#hiding-extended-dimensions}

{{eol}}

Você pode usar o parâmetro Oculto ou o parâmetro Mostrar para ocultar dimensões estendidas para que elas não sejam exibidas no menu de dimensão no Data Workbench.

Quando você insere a configuração apropriada para um dos parâmetros, o nome da dimensão não é listado no menu no Data Workbench, mas ainda está no perfil e disponível para ser usado. Qualquer usuário do Data Workbench pode mostrar temporariamente as dimensões ocultas definindo o parâmetro Mostrar tudo na [!DNL Insight.cfg] para verdadeiro.

Para obter mais informações sobre o parâmetro Mostrar tudo, consulte o apêndice sobre os parâmetros de configuração do Data Workbench na *Guia do usuário do Data Workbench*.

As seções a seguir descrevem como usar os parâmetros Oculto e Mostrar para ocultar dimensões estendidas.

* [Ocultar Dimension estendidas usando o parâmetro oculto](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Ocultar Dimension estendidas usando o parâmetro Mostrar](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Ocultar Dimension estendidas usando o parâmetro oculto {#section-7167a6f6241a4bc78f2f322e048d65cf}

O parâmetro Oculto é um parâmetro opcional que pode ser usado ao definir dimensões estendidas em [!DNL Transformation Dataset Configuration] arquivos.

1. Abrir [!DNL Transformation Dataset Configuration] arquivos nos quais a dimensão estendida que você deseja ocultar é definida. Consulte [Editar arquivos de inclusão existentes do conjunto de dados](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Localize o parâmetro Oculto para a dimensão desejada na janela de configuração e digite *true*.
1. Salve o arquivo localmente e salve-o no perfil apropriado no servidor. Consulte [Editar arquivos de inclusão existentes do conjunto de dados](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

O conjunto de dados é retransformado, após o que a dimensão estendida não aparece no menu de dimensão no Data Workbench. Para obter mais informações sobre o parâmetro Oculto , consulte [Dimension estendidas](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

Se você alterar a configuração do parâmetro Oculto , deverá retransformar o conjunto de dados para que a alteração tenha efeito.

## Ocultar Dimension estendidas usando o parâmetro Mostrar {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

O parâmetro Mostrar não é um dos parâmetros disponíveis para definir dimensões estendidas no [!DNL Transformation Dataset Configuration] arquivos. Em vez disso, o parâmetro é definido na variável [!DNL .dim] arquivos para qualquer dimensão derivada que você criar. Portanto, para usar o parâmetro Mostrar para ocultar uma dimensão estendida, primeiro crie uma dimensão derivada que seja baseada na dimensão estendida, conforme descrito no seguinte procedimento:

1. Use um editor de texto como o Bloco de notas para criar um arquivo vazio chamado &lt;*nome da dimensão*>.dim O nome do arquivo deve corresponder ao nome da dimensão que você deseja ocultar. Por exemplo, para ocultar a dimensão Próxima página, você criaria um [!DNL Next Page.dim] arquivo.

1. Adicione o seguinte texto ao arquivo :

   * entity = ref: wdata/model/dim/Pai/+nome
   * show = bool: false

1. Salve o arquivo no diretório Dimension do perfil. Você pode salvar o arquivo em um subdiretório, se desejar.

Ao usar o parâmetro Mostrar para ocultar uma dimensão estendida, não é necessário retransformar seu conjunto de dados para que a alteração tenha efeito. É possível optar por ocultar ou mostrar a dimensão na versão local do perfil (ou seja, é possível salvar a variável [!DNL .dim] ou você pode salvar o arquivo na pasta do Usuário) [!DNL .dim] para o servidor para uso por outros usuários do perfil.

Você também pode usar o parâmetro Mostrar para ocultar métricas e filtros. Para obter informações, consulte o capítulo Configuração da interface e recursos de análise no *Guia do usuário do Data Workbench*.
