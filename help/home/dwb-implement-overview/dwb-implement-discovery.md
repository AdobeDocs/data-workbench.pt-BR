---
description: Reúna e descreva as perguntas de negócios apropriadas ao seu ambiente de marketing ao implementar o Análise de big data.
title: Descoberta e requisitos da análise de big data
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Descoberta e requisitos da análise de big data{#data-workbench-discovery-and-requirements}

Reúna e descreva as perguntas de negócios apropriadas ao seu ambiente de marketing ao implementar o Análise de big data.

Esta seção permite que você colete informações sobre as perguntas e tarefas necessárias para desenvolver soluções no Análise de big data (DWB), que podem resolver essas perguntas de forma precisa, inequívoca e independente de tecnologia, fornecendo referências à terminologia comercial e à solução Adobe Analytics Premium. Esta seção fornece informações sobre estes objetivos e os requisitos associados.

## Fase 1: Principais objetivos/objetivos de negócios {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

As tabelas a seguir solicitam que você identifique sua base de clientes e analise a construção da implementação do DWB.

* Como entender a sua base de clientes
* Entendendo casos específicos de negócios (por exemplo, eficácia do Self-Service e de outros canais de dados/fontes de dados offline)

**Noções básicas sobre a sua base de clientes**

Entenda por que os clientes usam seu site, os desafios que você enfrenta e como a DWB o ajudará com base em seu modelo de negócios. Por exemplo, como medir, monitorar e analisar seus clientes para venda cruzada de outros produtos e serviços, obter a lista de usuários ativos e a penetração de contas e outras metas.

| ID | Pergunta/requisito comercial | Prioridade | Fase | Dependências |
|---|---|---|---|---|
| 1a | Pergunta Comercial Específica 1 | Alto/Médio/Baixo | 1 | Chave comum, dependendo de alguma outra chave etc. |
| 1b | Pergunta Comercial Específica 2 | Alto | 1 | Qualquer dependência |

Construção de análise

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">Fonte(s) de dados da Análise do espaço de trabalho</td> 
   <td colname="col2"> Adicionar nome da área de trabalho </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensões e métricas do espaço de trabalho necessárias </p> </td> 
   <td colname="col2"> <p>Identificar dimensões: </p> <p>Identificar métricas: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtros, sinalizadores e ferramentas do espaço de trabalho necessários </td> 
   <td colname="col2"> <p>Identificar segmentos: </p> <p>Identificar ferramentas: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Que ações podem ser derivadas dessa análise? </td> 
   <td colname="col2"> Entenda as tarefas e o conteúdo usando espaços de trabalho DWB específicos. </td> 
  </tr> 
 </tbody> 
</table>

## Fase 2: Entendendo casos de negócios específicos {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

Entenda outras fontes de dados e canais e saiba como eles se relacionarão aos seus casos comerciais.

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Perguntas/requisitos comerciais </th> 
   <th colname="col3" class="entry"> Prioridade </th> 
   <th colname="col04" class="entry"> Fase </th> 
   <th colname="col4" class="entry"> Dependências </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> Requisito de negócio específico 1 </td> 
   <td colname="col3"> <p>Alto/Médio/Baixo </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Chave comum, dependendo de alguma outra chave, sinalizador/identificador de conta etc. </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>Requisito de negócio específico 2 </p> </td> 
   <td colname="col3"> Alto/Médio/Baixo </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Qualquer dependência </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**Construção de análise**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">Fonte(s) de dados da Análise do espaço de trabalho
     </td> 
   <td colname="col2">
     Nome da área de trabalho de amostra </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensões e métricas do espaço de trabalho necessárias </p> </td> 
   <td colname="col2"> <p>Dimensões: Defina as dimensões necessárias. </p> <p>Métricas: Defina as métricas necessárias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtros, sinalizadores e ferramentas do espaço de trabalho necessários </td> 
   <td colname="col2"> <p>Segmentos: Identifique seus segmentos de clientes. </p> <p>Ferramentas: Selecione as ferramentas necessárias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Que ações podem ser derivadas dessa análise? </td> 
   <td colname="col2"> O que entender desta área de trabalho </td> 
  </tr> 
 </tbody> 
</table>

**Fontes de dados**

| Fontes de dados | Prioridade | Com que frequência os dados são recebidos? |
|---|---|---|
| Conjunto de relatórios de Nome do Site 1 (RSID) | 1 | Por hora |
| Nome do site 2 (se houver) (RSID) | 1 | Por hora |
| Fonte de dados 1 (se aplicável) | 2 | Diariamente? |
| Fonte de dados 2 (se aplicável) | 3 | Diariamente? |
