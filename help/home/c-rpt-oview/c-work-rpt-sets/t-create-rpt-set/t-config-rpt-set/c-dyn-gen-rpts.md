---
description: Você pode gerar relatórios dinamicamente para os elementos de dimensão especificados em um arquivo de pesquisa ou para um número específico de elementos de dimensão, como para os usuários com as 10 contagens de ordem mais altas.
solution: Analytics
title: Geração dinâmica de relatórios
topic: Data workbench
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Geração dinâmica de relatórios{#dynamically-generating-reports}

Você pode gerar relatórios dinamicamente para os elementos de dimensão especificados em um arquivo de pesquisa ou para um número específico de elementos de dimensão, como para os usuários com as 10 contagens de ordem mais altas.

>[!NOTE]
>
>A Adobe desencoraja a criação de conjuntos de relatórios dinâmicos para a geração diária (ou mais frequente) de relatórios. A geração dinâmica de relatórios pode consumir muitos recursos se você configurar relatórios com consultas grandes ou complexas.

* [Relatórios de Elemento de Dimensão de Arquivo de Pesquisa](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Principais relatórios de elementos de dimensão](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Relatórios de Elemento de Dimensão de Arquivo de Pesquisa {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Para configurar um conjunto de relatórios para gerar dinamicamente e (opcionalmente) distribuir relatórios para os elementos de uma dimensão especificada em um arquivo de pesquisa, especifique os seguintes parâmetros no [!DNL Report.cfg] arquivo:

* [!DNL Dimension Name]
* [!DNL Lookup File]

Para obter descrições detalhadas desses parâmetros, consulte Parâmetros [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

**Para criar um conjunto de relatórios dinâmico usando um arquivo de pesquisa**

1. Crie um arquivo de pesquisa de duas colunas para uma determinada dimensão. Esse arquivo deve conter duas colunas delimitadas por tabulação, sem uma linha de cabeçalho.

   * A coluna 1 deve conter uma lista de elementos de dimensão.
   * A coluna 2 deve conter os endereços de email dos destinatários do relatório. Um relatório para um dado elemento na coluna 1 é enviado para os endereços de email na mesma linha da coluna 2. Você pode inserir vários endereços de email separando-os por vírgulas (sem espaços).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Se os relatórios não forem enviados por email, a coluna 2 pode estar vazia, mas deve existir.
      >    * Esse arquivo pode conter linhas em branco.




1. Opcional. Para habilitar o envio de relatórios por email, você deve fazer o seguinte na [!DNL Mail Report] [!DNL Report.cfg] seção do arquivo para esse conjunto de relatórios específico:

   * No parâmetro Servidor SMTP, liste o servidor SMTP apropriado a ser usado para distribuir relatórios por email.
   * No parâmetro Destinatários, liste pelo menos um endereço de email para permitir que os relatórios sejam distribuídos por email. Os relatórios não são enviados para o endereço listado. Você define este parâmetro somente para permitir que os relatórios sejam enviados por email. Esse pode ser um endereço falso, mas deve estar em um formato permitido (por exemplo, [!DNL jsmith@company.com]).

1. Salve o arquivo de pesquisa na pasta do conjunto de relatórios.
1. Abra o [!DNL Report.cfg] arquivo do conjunto de relatórios.
1. No parâmetro Nome da dimensão, digite o nome da dimensão para a qual deseja gerar dinamicamente um relatório.
1. No parâmetro Arquivo de pesquisa, digite o local e o nome do arquivo de pesquisa que contém os elementos de dimensão desejados no relatório e os endereços de email do destinatário.
1. Repita essas etapas para conjuntos de relatórios adicionais.

>[!NOTE]
>
>Os relatórios dinâmicos não são enviados por email para os destinatários até que todo o conjunto de relatórios seja concluído.

## Principais relatórios de elementos de dimensão {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Para configurar um conjunto de relatórios para gerar relatórios dinamicamente para os principais elementos de dimensão, contando pela métrica especificada, especifique os seguintes parâmetros no [!DNL Report.cfg] arquivo:

* Nome da dimensão
* Métrica N superior
* Valor N Superior
* (Opcional) Filtro de consulta de pré-carregamento

Para obter descrições detalhadas desses parâmetros, consulte Parâmetros [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

**Para criar um conjunto de relatórios dinâmico para os elementos principais**

1. Abra o [!DNL Report.cfg] arquivo do conjunto de relatórios.
1. No parâmetro Nome da dimensão, digite o nome da dimensão para a qual deseja gerar dinamicamente um conjunto de relatórios.
1. No parâmetro Métrica N superior, digite o nome da métrica pela qual deseja classificar a dimensão.
1. No parâmetro N Valor Superior, digite o número de elementos de dimensão desejado no conjunto de relatórios.
1. (Opcional) No parâmetro Filtro de consulta de pré-carregamento, digite o nome do filtro desejado.
1. Repita essas etapas para conjuntos de relatórios adicionais.
1. Para obter informações sobre como usar uma visualização dinâmica de título com seu relatório, consulte o Guia *do usuário da Análise de* big data.

