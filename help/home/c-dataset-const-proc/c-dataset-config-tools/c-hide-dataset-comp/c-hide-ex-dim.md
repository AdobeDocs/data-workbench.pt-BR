---
description: Você pode usar o parâmetro Oculto ou o parâmetro Mostrar para ocultar dimensões estendidas, de modo que não sejam exibidas no menu de dimensão na análise de big data.
solution: Analytics
title: Ocultar dimensões estendidas
topic: Data workbench
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Ocultar dimensões estendidas{#hiding-extended-dimensions}

Você pode usar o parâmetro Oculto ou o parâmetro Mostrar para ocultar dimensões estendidas, de modo que não sejam exibidas no menu de dimensão na análise de big data.

Quando você insere a configuração apropriada para qualquer um dos parâmetros, o nome da dimensão não é listado no menu na análise de big data, mas ainda está no perfil e disponível para ser usado. Qualquer usuário da análise de big data pode mostrar temporariamente dimensões ocultas definindo o parâmetro Mostrar tudo no arquivo como [!DNL Insight.cfg] verdadeiro.

Para obter mais informações sobre o parâmetro Mostrar tudo, consulte o apêndice sobre os parâmetros de configuração da análise de big data no Guia *do Usuário da Análise de* big data.

As seções a seguir descrevem como usar os parâmetros Oculto e Mostrar para ocultar dimensões estendidas.

* [Ocultar dimensões estendidas usando o parâmetro oculto](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [Ocultar dimensões estendidas usando o parâmetro Mostrar](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Ocultar dimensões estendidas usando o parâmetro oculto {#section-7167a6f6241a4bc78f2f322e048d65cf}

O parâmetro Oculto é um parâmetro opcional que você pode usar ao definir dimensões estendidas em [!DNL Transformation Dataset Configuration] arquivos.

1. Abra [!DNL Transformation Dataset Configuration] os arquivos nos quais a dimensão estendida que você deseja ocultar está definida. Consulte [Edição De Conjuntos De Dados Existentes Incluir Arquivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

1. Localize o parâmetro Oculto para a dimensão desejada na janela de configuração e digite *true*.
1. Salve o arquivo localmente e salve-o no perfil apropriado no servidor. Consulte [Edição De Conjuntos De Dados Existentes Incluir Arquivos](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

O conjunto de dados é retransformado, após o qual a dimensão estendida não aparece no menu de dimensão na análise de big data. Para obter mais informações sobre o parâmetro Oculto, consulte Dimensões [](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)estendidas.

Se você alterar a configuração do parâmetro Oculto, será necessário retransformar o conjunto de dados para que a alteração tenha efeito.

## Ocultar dimensões estendidas usando o parâmetro Mostrar {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

O parâmetro Show não é um dos parâmetros disponíveis para definir dimensões estendidas em [!DNL Transformation Dataset Configuration] arquivos. Em vez disso, o parâmetro é definido nos [!DNL .dim] arquivos para qualquer dimensão derivada criada. Portanto, para usar o parâmetro Mostrar para ocultar uma dimensão estendida, primeiro é necessário criar uma dimensão derivada que seja baseada na dimensão estendida, conforme descrito no seguinte procedimento:

1. Use um editor de texto como o Bloco de notas para criar um arquivo vazio chamado &lt;nome *da* dimensão>.dim O nome do arquivo deve corresponder ao nome da dimensão que você deseja ocultar. Por exemplo, para ocultar a dimensão Próxima página, você criaria um [!DNL Next Page.dim] arquivo.

1. Adicione o seguinte texto ao arquivo:

   * entity = ref: wdata/model/dim/Parent/+name
   * show = bool: false

1. Salve o arquivo no diretório Dimensões do perfil. Se desejar, é possível salvar o arquivo em um subdiretório.

Ao usar o parâmetro Mostrar para ocultar uma dimensão estendida, não é necessário retransformar seu conjunto de dados para que a alteração tenha efeito. Você pode optar por ocultar ou mostrar a dimensão em sua versão local do perfil (ou seja, salvar o [!DNL .dim] arquivo na pasta Usuário) ou salvar o [!DNL .dim] arquivo no servidor para uso por outros usuários do perfil.

Você também pode usar o parâmetro Mostrar para ocultar métricas e filtros. Para obter informações, consulte o capítulo Configuração de recursos de interface e análise no Guia *do usuário da Análise de* big data.
