---
description: Lista de arquivos instalados com o Insight Server e os arquivos presentes depois que ele foi registrado e executado pela primeira vez.
solution: Insight
title: Estrutura do Diretório do Insight Server
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Estrutura do Diretório do Insight Server{#insight-server-directory-structure}

Lista de arquivos instalados com o Insight Server e os arquivos presentes depois que ele foi registrado e executado pela primeira vez.

## Arquivos incluídos no pacote de instalação {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Os seguintes diretórios estão incluídos no pacote de [!DNL Insight Server] instalação:

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Diretório </th> 
   <th colname="col2" class="entry"> Descrição do conteúdo do diretório </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Controle de acesso </td> 
   <td colname="col2"> <span class="keyword"> Arquivo de configuração do Insight Server </span> que especifica uma lista de Grupos de Acesso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereços </td> 
   <td colname="col2"> Endereço(s) usado(s) para comunicação com o <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auditoria </td> 
   <td colname="col2"> Logs de acesso diários contendo detalhes sobre todas as tentativas de conexão com o <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> compartimento </td> 
   <td colname="col2"> <span class="keyword"> Arquivos de programa executáveis do Insight Server </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificados </td> 
   <td colname="col2"> Certificados digitais SSL. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componentes </td> 
   <td colname="col2"> <span class="keyword"> Arquivos de configuração do componente do Insight Server </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componentes para servidores de processamento </td> 
   <td colname="col2"> <span class="keyword"> Arquivos de configuração de componente do Insight Server </span> para processar Servidores <span class="keyword"> Insight </span> em um cluster do <span class="keyword"> Insight Server </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Events </td> 
   <td colname="col2"> Registros diários de eventos contendo mensagens detalhadas de status de eventos, incluindo mensagens de erro. Os eventos capturados e registrados pelo <span class="keyword"> Insight Server também </span> são exibidos no Visualizador de eventos do Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Logs </td> 
   <td colname="col2"> <p>Registre os arquivos produzidos pelo <span class="wintitle"> Sensor </span>(s). </p> <p>"Logs" é o diretório de log padrão, mas um diretório alternativo pode ter sido especificado no arquivo <span class="filepath"> Communications.cfg </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pesquisas </td> 
   <td colname="col2"> Arquivos de pesquisa, como listas de robôs e mecanismos de pesquisa. <span class="keyword"> O Insight Server </span> deve carregar todos os arquivos de pesquisa na memória. O tamanho total de todos os arquivos de pesquisa referenciados nos arquivos de configuração do componente, além da sobrecarga (por exemplo, 12 bytes por linha para <span class="filepath"> </span> arquivos FlatFileLookup), não deve exceder a memória física ou virtual disponível que está disponível depois que todos os outros aplicativos de software são carregados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perfis </td> 
   <td colname="col2"> <p>Arquivos relacionados a cada perfil (configuração, espaço de trabalho e arquivos de visualização). Os perfis são preenchidos pelos dados de um conjunto de dados. Os conjuntos de dados incluem dados de eventos ("Dados de registro"); esses dados podem ser capturados por <span class="wintitle"> </span>Sensores instalados, transmitidos por beacons da Web ou por tags de página, ou por entradas de data warehouses. <span class="keyword"> Os </span> usuários do Insight com acesso a um determinado perfil podem usar o conjunto de dados processados para esse perfil, bem como os Espaços de trabalho e as visualizações definidos dentro desse perfil. </p> <p>Os espaços de trabalho são áreas de trabalho para administração ou análise do sistema. Uma Workspace pode conter várias interfaces que mostram detalhes diferentes sobre o desempenho do sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software </td> 
   <td colname="col2"> <span class="keyword"> Atualizações </span> de software do Insight. As atualizações de software de relatório também são armazenadas aqui. </td> 
  </tr> 
 </tbody> 
</table>

## Diretórios e arquivos criados após a inicialização {#section-ef7408e8fae64454b326ec07453d4628}

Os diretórios listados abaixo são criados depois de [!DNL Insight Server] serem registrados e executados pela primeira vez:

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Diretório </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Estado </td> 
   <td colname="col2"> Informações de processamento geradas pelo <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>Local dos arquivos temporários usados pelo <span class="keyword"> Insight Server </span> durante o reprocessamento e a operação. Geralmente há um arquivo (chamado <span class="filepath"> temp.db </span> por padrão) por unidade física. </p> <p> <span class="keyword"> O Insight Server </span> deve estar configurado para gravar neste diretório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rastreamento </td> 
   <td colname="col2"> Dados de log e evento sobre o <span class="keyword"> Insight Server </span>. Útil para solução de problemas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usuários </td> 
   <td colname="col2"> Usuários nomeados ( <span class="keyword"> Insight </span>) com acesso aos perfis no servidor. Um diretório para cada usuário autorizado nomeado é criado no diretório Usuários\ quando o usuário acessa pela primeira vez o <span class="keyword"> Insight Server </span> via <span class="keyword"> Insight </span>. O diretório de cada usuário nomeado contém diretórios que correspondem a todos os perfis que o usuário acessou no <span class="keyword"> Insight Server </span> e seus arquivos de endereço locais. </td> 
  </tr> 
 </tbody> 
</table>

