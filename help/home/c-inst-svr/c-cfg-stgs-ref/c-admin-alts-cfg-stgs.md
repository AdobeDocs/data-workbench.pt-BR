---
description: Instruções para configurar alertas administrativos para Servidor Insight, Repetidor ou Transformar.
title: Configurações de alertas administrativos
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Configurações de alertas administrativos{#administrative-alerts-configuration-settings}

Instruções para configurar alertas administrativos para Servidor Insight, Repetidor ou Transformar.

Complete os parâmetros no seguinte arquivo:

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Categoria </td> 
   <td colname="col2"> O nome da categoria. É necessária uma categoria de Padrão. Consulte Categorias de erro nesta tabela. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Categorias de erros </td> 
   <td colname="col2"> Permite categorizar os erros junto com o Arquivo de Categorização de erros. Cada Categoria de Erro pode ter seu próprio conjunto de Recipients e seu próprio Atraso de Controle. Por exemplo, você pode criar uma categoria Crítica com um atraso de aceleração de 0, para que cada erro crítico seja enviado por email imediatamente para os recipients especificados na lista Recipients. Erros que não correspondem a uma substring no Arquivo de Categorização de Erro são atribuídos à categoria Padrão. Para adicionar uma nova categoria, clique com o botão direito do mouse em um número e clique em <span class="uicontrol"> Adicionar Novo </span> &gt; <span class="uicontrol"> Categoria de Erro </span>. Também é possível copiá-los ou removê-los usando a ação de clique com o botão direito do mouse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo de Categorização de Erro </td> 
   <td colname="col2"> <p>O nome do arquivo que deseja usar para categorizar cada alerta. Crie este arquivo usando o Bloco de notas. Esse arquivo deve ter três colunas em cada linha, separadas por guias. A primeira coluna é uma string que deve corresponder a erros. Um sinal ^ corresponde ao início e um $ corresponde ao final da string; todos os outros caracteres são correspondidos literalmente. A segunda coluna é uma categoria para erros que correspondem, que está em Categorias de erro. O terceiro é uma mensagem alternativa, que é anexada à mensagem de erro real em emails enviados. Se nenhum arquivo for especificado, todos os erros serão categorizados como Padrão. </p> <p>Para ver um exemplo desse arquivo, consulte o arquivo <span class="filepath"> Error Categories.txt </span> no diretório Lookups . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> De </td> 
   <td colname="col2"> <p>Endereço que aparece no parâmetro "de" da mensagem de email. </p> <p>Exemplo: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espaço Mínimo em Disco (MB) </td> 
   <td colname="col2"> O servidor gera um alerta de e-mail quando o armazenamento em disco disponível em qualquer diretório usado pelo servidor fica abaixo desse valor. O valor padrão é 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo limite do alerta do sensor (min) </td> 
   <td colname="col2"> <p>O servidor gera um alerta de email quando não recebeu dados de um Sensor <span class="wintitle"> previamente conectado </span> configurado nessa janela de tempo. O valor padrão é 15. </p> <p> <p>Observação:  <span class="wintitle"> Tempo limite de alerta do sensor </span> funciona somente se uma conexão existente com um <span class="wintitle"> Sensor </span> for removida. Se o serviço do servidor for interrompido e reiniciado e os <span class="wintitle"> Sensores </span> não se conectarem, o servidor não gerará alertas de email. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço do servidor </td> 
   <td colname="col2"> <p>O endereço do servidor SMTP para email de saída. </p> <p>Exemplo: <span class="filepath"> mail.mycompany.com </span></p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Senha do servidor </td> 
   <td colname="col2"> <p>A senha para fazer logon no servidor SMTP. Esse parâmetro é opcional, a menos que o logon seja necessário para enviar emails. </p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usuário do servidor </td> 
   <td colname="col2"> <p>A ID/nome de usuário para fazer logon no servidor SMTP. Esse parâmetro é opcional, a menos que o logon seja necessário para enviar emails. </p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Atraso da aceleração (segundos) </td> 
   <td colname="col2"> O número mínimo de segundos que deve decorrer entre dois erros nessa categoria para um email ser enviado. Um valor de 0 envia o email imediatamente. </td> 
  </tr> 
 </tbody> 
</table>
