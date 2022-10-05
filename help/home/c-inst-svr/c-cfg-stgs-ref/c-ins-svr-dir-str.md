---
description: Lista de arquivos instalados com o Insight Server e os arquivos presentes após o registro e execução pela primeira vez.
title: Estrutura do diretório do servidor Insight
uuid: 8339b275-f118-4d5d-937e-4df9f8a56b50
exl-id: 568391d0-e0f7-4a5a-ad71-de33c52968a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Estrutura do diretório do servidor Insight{#insight-server-directory-structure}

{{eol}}

Lista de arquivos instalados com o Insight Server e os arquivos presentes após o registro e execução pela primeira vez.

## Arquivos incluídos no pacote de instalação {#section-daec17dab3e34c3c9e1ef65842cb91f1}

Os seguintes diretórios estão incluídos na variável [!DNL Insight Server] pacote de instalação:

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Diretório </th> 
   <th colname="col2" class="entry"> Descrição do Conteúdo do Diretório </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Controle de acesso </td> 
   <td colname="col2"> <span class="keyword"> Servidor Insight </span> arquivo de configuração que especifica uma lista de Grupos de acesso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereços </td> 
   <td colname="col2"> Endereço(s) utilizado(s) para comunicação com <span class="keyword"> Servidor Insight </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Auditoria </td> 
   <td colname="col2"> Registros de acesso diários contendo detalhes sobre todas as tentativas de conexão com o <span class="keyword"> Servidor Insight </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> compartimento </td> 
   <td colname="col2"> <span class="keyword"> Servidor Insight </span> arquivos de programa executáveis. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificados </td> 
   <td colname="col2"> Certificados digitais SSL. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componentes </td> 
   <td colname="col2"> <span class="keyword"> Servidor Insight </span> arquivos de configuração de componente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Componentes para servidores de processamento </td> 
   <td colname="col2"> <span class="keyword"> Servidor Insight </span> arquivos de configuração de componente para processamento <span class="keyword"> Servidores Insight </span> em <span class="keyword"> Servidor Insight </span> cluster. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eventos </td> 
   <td colname="col2"> Logs de evento diários contendo mensagens detalhadas de status do evento, incluindo mensagens de erro. Eventos capturados e registrados por <span class="keyword"> Servidor Insight </span> também são exibidos no Visualizador de Eventos do Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Logs </td> 
   <td colname="col2"> <p>Arquivos de log produzidos por <span class="wintitle"> Sensor </span>(s). </p> <p>"Logs" é o diretório de log padrão, mas um diretório alternativo pode ter sido especificado no <span class="filepath"> communications.cfg </span> arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pesquisas </td> 
   <td colname="col2"> Arquivos de pesquisa, como listas de robôs e mecanismos de pesquisa. <span class="keyword"> Servidor Insight </span> O deve carregar todos os arquivos de pesquisa na memória. O tamanho total de todos os arquivos de pesquisa referenciados nos arquivos de configuração do componente, além da sobrecarga (por exemplo, 12 bytes por linha para <span class="filepath"> FlatFileLookup </span> arquivos), não deve exceder a memória física ou virtual disponível depois que todos os outros aplicativos de software forem carregados. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Perfis </td> 
   <td colname="col2"> <p>Arquivos relacionados a cada perfil (configuração, espaço de trabalho e arquivos de visualização). Os perfis são preenchidos por dados de um conjunto de dados. Os conjuntos de dados incluem dados de evento ("Dados de registro"); esses dados podem ser capturados por meio de <span class="wintitle"> Sensores </span>, transmitidos por Web beacons ou tags de página, ou entrada de data warehouses. <span class="keyword"> Insight </span> os usuários com acesso a um determinado perfil podem usar o conjunto de dados processados para esse perfil, bem como os Espaços de trabalho e as visualizações definidas dentro desse perfil. </p> <p>Os espaços de trabalho são áreas de trabalho para análise ou administração do sistema. Um espaço de trabalho pode conter várias interfaces que mostram detalhes diferentes sobre o desempenho do sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software </td> 
   <td colname="col2"> <span class="keyword"> Insight </span> atualizações de software. As atualizações de software de relatório também são armazenadas aqui. </td> 
  </tr> 
 </tbody> 
</table>

## Diretórios e arquivos criados após a inicialização {#section-ef7408e8fae64454b326ec07453d4628}

Os diretórios listados abaixo são criados após [!DNL Insight Server] está registrada e é executada pela primeira vez:

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
   <td colname="col2"> Informações de processamento geradas por <span class="keyword"> Servidor Insight </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>Localização dos arquivos temporários usados pelo <span class="keyword"> Servidor Insight </span> durante o reprocessamento e a operação. Geralmente há um arquivo (nomeado <span class="filepath"> temp.db </span> por padrão) por unidade física. </p> <p> <span class="keyword"> Servidor Insight </span> deve ser configurado para gravar nesse diretório. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rastreio </td> 
   <td colname="col2"> Dados de log e evento sobre <span class="keyword"> Servidor Insight </span>. Útil para solucionar problemas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usuários </td> 
   <td colname="col2"> Nomeado ( <span class="keyword"> Insight </span>) usuários com acesso aos perfis no servidor. Um diretório para cada usuário nomeado autorizado é criado no diretório Usuários\ quando o usuário acessa pela primeira vez <span class="keyword"> Servidor Insight </span> via <span class="keyword"> Insight </span>. O diretório de cada usuário nomeado contém diretórios correspondentes a todos os perfis que o usuário acessou nesse <span class="keyword"> Servidor Insight </span> bem como seus arquivos de endereço local. </td> 
  </tr> 
 </tbody> 
</table>
