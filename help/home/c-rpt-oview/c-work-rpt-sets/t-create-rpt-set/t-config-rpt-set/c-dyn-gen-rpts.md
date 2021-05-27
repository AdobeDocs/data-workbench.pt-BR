---
description: Você pode gerar relatórios dinamicamente para os elementos de dimensão especificados em um arquivo de pesquisa ou para um número específico de elementos de dimensão, como para os usuários com as 10 contagens de ordem mais altas.
title: Gerar relatórios dinamicamente
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
exl-id: c14d93cd-212d-44a1-aff9-652e5c4fbda0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---

# Gerar relatórios dinamicamente{#dynamically-generating-reports}

Você pode gerar relatórios dinamicamente para os elementos de dimensão especificados em um arquivo de pesquisa ou para um número específico de elementos de dimensão, como para os usuários com as 10 contagens de ordem mais altas.

>[!NOTE]
>
>O Adobe desencoraja a criação de conjuntos de relatórios dinâmicos para a geração diária (ou mais frequente) de relatórios. A geração de relatórios dinâmicos pode consumir muitos recursos se você configurar relatórios com consultas grandes ou complexas.

* [Relatórios de elemento do Dimension de arquivo de pesquisa](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Principais relatórios de elementos do Dimension](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Relatórios de Dimension de elemento do arquivo de pesquisa {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Para configurar um conjunto de relatórios para gerar e distribuir relatórios dinamicamente (opcionalmente) para os elementos de uma dimensão especificada em um arquivo de pesquisa, especifique os seguintes parâmetros no arquivo [!DNL Report.cfg]:

* [!DNL Dimension Name]
* [!DNL Lookup File]

Para obter descrições detalhadas desses parâmetros, consulte [Parâmetros Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Para criar um conjunto de relatórios dinâmico usando um arquivo de pesquisa**

1. Crie um arquivo de pesquisa de duas colunas para uma determinada dimensão. Esse arquivo deve conter duas colunas delimitadas por tabulação, sem uma linha de cabeçalho.

   * A coluna 1 deve conter uma lista de elementos de dimensão.
   * A coluna 2 deve conter os endereços de email dos recipients do relatório. Um relatório para um determinado elemento na coluna 1 é enviado para o(s) endereço(s) de email na mesma linha da coluna 2. É possível inserir vários endereços de email separando-os por vírgulas (sem espaços).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Para que os relatórios não sejam enviados por email, a coluna 2 pode estar vazia, mas deve existir.
      >    * Esse arquivo pode conter linhas em branco.




1. Opcional. Para habilitar o envio por email dos relatórios, você deve fazer o seguinte na seção [!DNL Mail Report] do arquivo [!DNL Report.cfg] para esse conjunto de relatórios específico:

   * No parâmetro Servidor SMTP , liste o servidor SMTP apropriado a ser usado para distribuir relatórios por email.
   * No parâmetro Recipients , liste pelo menos um endereço de email para permitir que os relatórios sejam distribuídos via email. Os relatórios não são enviados por email para o endereço listado. Você define este parâmetro somente para permitir que os relatórios sejam enviados por email. Pode ser um endereço fictício, mas deve estar em um formato permitido (por exemplo, [!DNL jsmith@company.com]).

1. Salve o arquivo de pesquisa na pasta do conjunto de relatórios.
1. Abra o arquivo [!DNL Report.cfg] para o conjunto de relatórios.
1. No parâmetro Nome do Dimension, digite o nome da dimensão para a qual deseja gerar um relatório dinamicamente.
1. No parâmetro Arquivo de pesquisa, digite o local e o nome do arquivo de pesquisa que contém os elementos de dimensão que você deseja no relatório e os endereços de email do destinatário.
1. Repita essas etapas para conjuntos de relatórios adicionais.

>[!NOTE]
>
>Os relatórios dinâmicos não são enviados por email para os recipients até que todo o conjunto de relatórios seja concluído.

## Principais relatórios de elemento do Dimension {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Para configurar um conjunto de relatórios para gerar relatórios dinamicamente para os elementos de dimensão principais, contando pela métrica especificada, especifique os seguintes parâmetros no arquivo [!DNL Report.cfg]:

* Nome da dimensão
* Métrica N principais
* Valor N Superior
* (Opcional) Filtro de Consulta de Pré-carregamento

Para obter descrições detalhadas desses parâmetros, consulte [Parâmetros Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Para criar um conjunto de relatórios dinâmico para os elementos principais**

1. Abra o arquivo [!DNL Report.cfg] do conjunto de relatórios.
1. No parâmetro Nome do Dimension, digite o nome da dimensão para a qual deseja gerar dinamicamente um conjunto de relatórios.
1. No parâmetro As N métricas principais , digite o nome da métrica pela qual deseja classificar a dimensão.
1. No parâmetro Valor N Superior , digite o número de elementos de dimensão que deseja incluir no conjunto de relatórios.
1. (Opcional) No parâmetro Filtro de consulta de pré-carregamento , digite o nome do filtro desejado.
1. Repita essas etapas para conjuntos de relatórios adicionais.
1. Para obter informações sobre como usar uma visualização dinâmica de título com seu relatório, consulte o *Guia do Usuário da Data Workbench*.
