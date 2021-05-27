---
description: As notas de versão do Data Workbench 6.1 incluem novos recursos, requisitos de atualização, correções de erros e problemas conhecidos.
title: Notas de versão do Data Workbench 6.1
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
exl-id: ed37a00f-b4cd-428e-abb7-7c52d5cfd2f9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 2%

---

# Notas de versão do Data Workbench 6.1{#data-workbench-release-notes}

As notas de versão do Data Workbench 6.1 incluem novos recursos, requisitos de atualização, correções de erros e problemas conhecidos.

## Novos recursos {#section-1225066ea8f44cf68e42e019d0bca816}

A Data Workbench 6.1 inclui estes novos recursos:

| Recursos | Descrição |
|--- |--- |
| Atualização do Windows de 64 bits | O servidor do Data Workbench, o servidor de relatórios e os componentes do cliente são atualizados para serem executados somente em sistemas operacionais Windows de 64 bits. |
| Pontuação de propensão | A pontuação do público-alvo permite identificar a fidelidade do cliente e a percepção estatística de quem tem probabilidade de converter uma venda ou interagir com uma história ou campanha. A pontuação de propensão agora inclui essas visualizações para visualizar modelos e mostrar a correlação de alteração das métricas selecionadas.<ul><li>O Visualizador de Modelo examina um modelo de regressão logística gerado com Pontuação de Propensão, exibindo os pesos de coeficiente de cada variável de entrada (incluindo o termo constante) e seu intervalo de erros estatísticos. </li><li>Os gráficos de incentivo e ganho são usados para avaliar o aumento potencial de um modelo de dados pontuado.</li><li>A Matriz de Confusão fornece quatro contagens pela combinação de Positivo Real (AP), Negativo Real (AN), Positivo Previsto (PP) e Negativo Previsto (PN).</li> <li>A partir da v6.1, agora há uma opção Salvar para salvar pontuações de propensão com base em dois tipos: dimensões ou dimensões e métricas.</li><li>Agora você pode clicar em Ctrl-Alt e arrastar e soltar para adicionar elementos na Pontuação de propensão e no Construtor de cluster. Antes para adicionar elementos de tabela, era necessário arrastar a tabela para a caixa Elementos .</li></ul> |
| Data Workbench agora em chinês | O Data Workbench agora oferece suporte ao idioma chinês simplificado para o aplicativo cliente. O Data Workbench também oferece suporte ao Editor de método de entrada (IME) como um processo de entrada de texto secundário para idiomas internacionais. |
| Funções matemáticas | Agora é possível adicionar funções Matemáticas às métricas, transformações matemáticas e células da planilha para calcular ainda mais os conjuntos de dados. |
| Chamadas estatísticas | As tabelas agora oferecem uma chamada resumida de estatística para colunas de métrica. A chamada pode exibir a média, o desvio padrão, os valores mínimo e máximo, a variação e a contagem total da coluna. Ele pode ser fatorado em qualquer seleção e avaliação. |
| Filtro de matriz de correlação | A Matriz de correlação foi atualizada com um Filtro binário para permitir que você restrinja valores para uma ou ambas as métricas correlacionadas, permitindo que você concentre melhor sua comparação. Além disso, agora é possível adicionar elementos Dimension de uma tabela de Dimension, clicando em Ctrl + Alt e arrastando os elementos para a coluna ou linha da matriz a ser avaliada. |
| Ocultar rótulo de Fallout na visualização do funil | Alterne entre exibir e ocultar rótulos de fallout em uma visualização de Funil clicando com o botão direito do mouse no título e selecionando Ocultar Fallout. |

## Classificação de Colunas da Tabela{#sorting-table-columns}

Classifique as colunas da tabela alfabeticamente ou por ordinais.

Para selecionar melhor os elementos em uma tabela Dimension, é possível ordenar a primeira coluna alfabeticamente ou por ordinais selecionando a opção de menu **[!UICONTROL Sort]**.

O caractere # será exibido quando uma coluna for classificada por ordinais (o padrão).

**Selecionar Opção de Classificação**

Para alterar as opções de classificação entre ordinal e alfabeto, clique com o botão direito do mouse e selecione **[!UICONTROL Sort]**. Clique na seta para inverter a ordem.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>Você pode classificar outras colunas por comum clicando no nome da coluna.

## Ocultar rótulos de fallout no funil

Alterne para abrir rótulos de fallout em uma visualização de Funil .

A visualização de Funil permite identificar onde um cliente abandona uma campanha de marketing ou é desviado de um caminho de conversão definido ao interagir com seu site ou com sua campanha entre canais. O lado esquerdo da visualização de Funil exibe os resultados de uma visita ou visitantes, enquanto o lado direito exibe o &quot;Fallout&quot; daqueles que abandonam um caminho especificado.

![](assets/c_funnel_hide_fallout.png)

Em uma visualização **[!UICONTROL Funnel]**, é possível clicar com o botão direito do mouse no título e selecionar **[!UICONTROL Hide Fallout]** no menu para ocultar os rótulos de fallout.

## Problemas conhecidos {#section-ff2180c6871c413480e15fa915c253b9}

* Ao importar um espaço de trabalho, uma mensagem de erro é exibida mesmo que a importação tenha sido bem-sucedida.

   Solução alternativa: Clique em OK para ignorar o erro. O espaço de trabalho é importado com êxito.

**Problemas de localização em chinês simplificado**

* O título da caixa de diálogo e a mensagem exibidas após clicar em &quot;Enviar&quot; ao definir o público-alvo na visualização de Pontuação são ilegíveis.

   Solução alternativa: Nenhum.
* Ao usar quebra automática de texto na visualização da Planilha, as palavras localizadas não estão sendo vinculadas corretamente. Caracteres de lixo extra estão sendo adicionados à cadeia de caracteres.

   Solução alternativa: Nenhum
* Não é possível iniciar [!DNL Insight.exe] se o diretório de instalação for nomeado com caracteres que não sejam em inglês.

   Solução alternativa: Mantenha os nomes padrão ou renomeie usando apenas caracteres em inglês no caminho da pasta para iniciar executáveis.
