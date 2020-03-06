---
description: Instruções para configurar alertas administrativos para o Insight Server, Repeater ou Transformar.
solution: Insight
title: Configurações de alertas administrativos
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurações de alertas administrativos{#administrative-alerts-configuration-settings}

Instruções para configurar alertas administrativos para o Insight Server, Repeater ou Transformar.

Preencha os parâmetros no seguinte arquivo:

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
   <td colname="col2"> O nome da categoria. Uma categoria de Padrão é necessária. Consulte Categorias de erro nesta tabela. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Categorias de erro </td> 
   <td colname="col2"> Permite categorizar erros em conjunto com o Arquivo de Categorização de Erros. Cada categoria de erro pode ter seu próprio conjunto de destinatários e seu próprio Atraso de aceleração. Por exemplo, você pode criar uma categoria Crítica com um atraso de aceleração de 0, para que todos os erros críticos sejam enviados imediatamente por email para os destinatários especificados na lista Destinatários. Erros que não correspondem a uma substring no Arquivo de categorização de erros são atribuídos à categoria Padrão. Para adicionar uma nova categoria, clique com o botão direito do mouse em um número e clique em <span class="uicontrol"> Adicionar novo </span> &gt; <span class="uicontrol"> Categoria de erro </span>. Você também pode copiá-los ou removê-los usando a ação de clicar com o botão direito do mouse. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Arquivo de classificação de erro </td> 
   <td colname="col2"> <p>O nome do arquivo que você deseja usar para categorizar cada alerta. Crie este arquivo usando o Bloco de notas. Esse arquivo deve ter três colunas em cada linha, separadas por guias. A primeira coluna é uma string a ser correspondida em erros. Um sinal ^ corresponde ao início e um $ corresponde ao final da string; todos os outros caracteres correspondem literalmente. A segunda coluna é uma categoria para erros que correspondem, que está em Categorias de erro. O terceiro é uma mensagem alternativa, que é anexada à mensagem de erro real em emails enviados. Se nenhum arquivo for especificado, todos os erros serão classificados como Padrão. </p> <p>Para ver um exemplo desse arquivo, consulte o arquivo <span class="filepath"> Error Categories.txt </span> no diretório Lookups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> De </td> 
   <td colname="col2"> <p>Endereço que aparece no parâmetro "de" da mensagem de email. </p> <p>Exemplo: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Espaço Mínimo em Disco (MB) </td> 
   <td colname="col2"> O servidor gera um alerta de email quando o armazenamento em disco disponível em qualquer diretório usado pelo servidor cai abaixo desse valor. O valor padrão é 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo limite do alerta do sensor (min) </td> 
   <td colname="col2"> <p>O servidor gera um alerta de email quando não recebeu dados de um <span class="wintitle"> sensor configurado e conectado anteriormente </span> dentro dessa janela de tempo. O valor padrão é 15. </p> <p> <p>Observação:  O Tempo limite de alerta do <span class="wintitle"> sensor </span> funciona somente se uma conexão existente com um <span class="wintitle"> sensor </span> for interrompida. Se o serviço do servidor for interrompido e reiniciado e os <span class="wintitle"> Sensores </span> não se conectarem, o servidor não gerará alertas de email. </p> </p> </td> 
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
   <td colname="col2"> <p>A ID/nome do usuário para fazer logon no servidor SMTP. Esse parâmetro é opcional, a menos que o logon seja necessário para enviar emails. </p> <p>É necessário um servidor SMTP para usar os recursos descritos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Atraso da aceleração (segundos) </td> 
   <td colname="col2"> O número mínimo de segundos que deve decorrer entre dois erros nessa categoria para um email ser enviado. Um valor de 0 envia o email imediatamente. </td> 
  </tr> 
 </tbody> 
</table>

