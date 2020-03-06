---
description: As notas de versão do Análise de big data 6.1 incluem novos recursos, requisitos de atualização, correções de erros e problemas conhecidos.
solution: Analytics
title: Notas de versão do Análise de big data 6.2
topic: Data workbench
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Notas de versão do Análise de big data 6.2{#data-workbench-release-notes}

As notas de versão do Análise de big data 6.1 incluem novos recursos, requisitos de atualização, correções de erros e problemas conhecidos.

## Novos Recursos {#section-1225066ea8f44cf68e42e019d0bca816}

O Análise de big data 6.1 inclui estes novos recursos:

| Recursos  | Descrição |
|--- |--- |
| Atualização do Windows de 64 bits | O servidor de análise de big data, o servidor de relatório e os componentes do cliente são atualizados para serem executados somente em sistemas operacionais Windows de 64 bits. |
| Pontuação de propensão | Pontuar seu público-alvo permite identificar a fidelidade do cliente e perceber estatisticamente quem tem probabilidade de converter uma venda ou interagir com uma história ou campanha. A pontuação de propensão agora inclui essas visualizações para exibir modelos e mostrar a correlação de alteração das métricas selecionadas.<ul><li>O Visualizador de Modelo examina um modelo de regressão logística gerado com Pontuação de propensão, exibindo os pesos de coeficiente de cada variável de entrada (incluindo o termo constante) e seu intervalo de erros estatísticos. </li><li>Gráficos de incentivo e ganho são usados para avaliar o aumento potencial de um modelo de dados pontuado.</li><li>A Matriz de Confusão fornece quatro contagens pela combinação de Positivo Real (AP), Negativo Real (AN), Positivo Previsto (PP) e Negativo Previsto (PN).</li> <li>A partir da v6.1, agora você tem a opção Salvar para salvar as pontuações de propensão com base em dois tipos: dimensões ou dimensões e métricas.</li><li>Agora você pode clicar em Ctrl-Alt e arrastar e soltar para adicionar elementos na Pontuação de propensão e no Construtor de clusters. Antes de adicionar elementos de tabela, era necessário arrastar da tabela para a caixa Elementos.</li></ul> |
| Análise de big data agora em chinês | Agora, a análise de big data suporta chinês simplificado para o aplicativo cliente. A análise de big data também suporta o Editor de método de entrada (IME) como um processo de entrada de texto secundário para idiomas internacionais. |
| Funções matemáticas | Agora é possível adicionar funções Matemáticas a métricas, transformações matemáticas e células de planilhas para calcular ainda mais os conjuntos de dados. |
| Chamadas estatísticas | As tabelas agora oferecem uma chamada de resumo de estatísticas para colunas de métricas. A chamada pode exibir a média, o desvio padrão, os valores mínimo e máximo, a variação e a contagem total da coluna. Pode ser tido em conta em qualquer seleção e avaliação. |
| Matriz de correlação, filtro | A Matriz de correlação foi atualizada com um Filtro binário para permitir que você restrinja valores para uma ou ambas as métricas correlacionadas, permitindo que você concentre melhor sua comparação. Além disso, agora é possível adicionar elementos de Dimensão de uma tabela de Dimensão clicando em Ctrl + Alt e arrastando elementos para a coluna ou linha da matriz a ser avaliada. |
| Ocultar rótulo de fallout na visualização de funil | Alterne entre exibir e ocultar rótulos de fallout em uma visualização de Funil clicando com o botão direito do mouse no título e selecionando Ocultar Fallout. |

## Classificação de colunas de tabela{#sorting-table-columns}

Classifique as colunas da tabela alfabeticamente ou por ordinais.

Para selecionar melhor os elementos em uma tabela de Dimensão, é possível ordenar a primeira coluna alfabeticamente ou por ordinais selecionando a opção de **[!UICONTROL Sort]** menu.

O caractere # será exibido quando uma coluna for classificada por ordinais (o padrão).

**Selecionar opção de classificação**

Para alterar as opções de classificação entre ordinal e alfabeto, clique com o botão direito do mouse e selecione **[!UICONTROL Sort]**. Clique na seta para reverter a ordem.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>É possível classificar outras colunas por ordinal clicando no nome da coluna.

## Ocultar etiquetas de fallout no funil

Alterne para abrir rótulos de fallout em uma visualização de Funil.

A visualização de funil identifica onde um cliente abandona uma campanha de marketing ou se desvia de um caminho de conversão definido ao interagir com seu site ou campanha entre canais. O lado esquerdo da visualização Funil exibe os resultados de uma visita ou visitantes, enquanto o lado direito exibe o &quot;Fallout&quot; dos que abandonam um caminho especificado.

![](assets/c_funnel_hide_fallout.png)

Em uma **[!UICONTROL Funnel]** visualização, você pode clicar com o botão direito do mouse no título e selecionar **[!UICONTROL Hide Fallout]** no menu para ocultar os rótulos de fallout.

## Problemas conhecidos {#section-ff2180c6871c413480e15fa915c253b9}

* Ao importar um espaço de trabalho, uma mensagem de erro é exibida mesmo que a importação tenha sido bem-sucedida.

   Solução: Clique em OK para ignorar o erro. A área de trabalho foi importada com êxito.

**Problemas de localização em chinês simplificado**

* O título e a mensagem da caixa de diálogo exibidos após clicar em &quot;Enviar&quot; ao definir o destino na visualização de Pontuação são ilegíveis.

   Solução: Nenhum.
* Ao usar a quebra automática de palavras na visualização da Planilha, as palavras localizadas não estão sendo vinculadas corretamente. Caracteres de lixo eletrônico adicionais estão sendo adicionados à string.

   Solução: Nenhum
* Não é possível iniciar [!DNL Insight.exe] se o diretório de instalação for nomeado com caracteres que não sejam em inglês.

   Solução: Mantenha os nomes padrão ou renomeie usando apenas caracteres em inglês no caminho da pasta para iniciar executáveis.
