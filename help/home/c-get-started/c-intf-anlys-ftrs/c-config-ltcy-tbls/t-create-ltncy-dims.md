---
description: As dimensões de latência são construídas a partir de uma dimensão pai contável, como Sessões, e de uma dimensão de tempo, como Dia.
solution: Analytics
title: Criar uma dimensão de latência
topic: Data workbench
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Criar uma dimensão de latência{#create-a-latency-dimension}

As dimensões de latência são construídas a partir de uma dimensão pai contável, como Sessões, e de uma dimensão de tempo, como Dia.

Quando você cria uma tabela de latência na Análise de big data, adiciona automaticamente uma dimensão de latência ao arquivo de visualização (.vw). Você pode editar a dimensão de latência de uma tabela seguindo as etapas abaixo.

**Para editar uma dimensão de latência**

1. Abra a tabela de latência criada em um editor de texto, como o Bloco de notas. Ela está localizada em Usuário > `working profile name` > Pasta de trabalho no diretório de instalação do Análise de big data.

   A dimensão de latência definida inclui os parâmetros mostrados no exemplo a seguir. (A definição da sua dimensão de latência pode incluir parâmetros adicionais.) O [!DNL line entity = LatencyDim:] indica o início da definição da dimensão de latência.

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. Edite os valores para os parâmetros Nome, Nível, Clipe, Tempo, Formato, Tempo antes ou Tempo depois usando a seguinte tabela como guia:

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Para este parâmetro... </th> 
      <th colname="col2" class="entry"> Fornecer estas informações... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Opcional. O nome da dimensão de latência que aparece no menu de contexto quando você clica com o botão direito do mouse no rótulo ou nos elementos da dimensão. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Nível </p> </td> 
      <td colname="col2"> <p>Uma dimensão contável que é o pai da dimensão de latência. Os exemplos incluem Sessão, Visitante e Exibição de página. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Clipe </p> </td> 
      <td colname="col2"> <p>Uma dimensão contável que tem uma relação um para muitos com o nível da dimensão de latência. A latência não é calculada entre os limites dessa dimensão. Por exemplo, se você especificar um nível de Exibição de página e um clipe de Sessão, as latências serão calculadas para as exibições de página que ocorreram durante a mesma sessão do evento. </p> <p>Para obter informações sobre dimensões de um para muitos (simples), consulte o Guia <i>de Configuração de</i>Conjunto de Dados. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Hora </p> </td> 
      <td colname="col2"> <p>A dimensão usada para medir o tempo decorrido para a dimensão de latência. Essa dimensão pode ser uma dimensão de tempo, como Dia ou Hora, ou uma dimensão contável, como Visitante, Sessão ou Exibição de página. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Formato </td> 
      <td colname="col2"> <p>Opcional. Especifica a aparência da visualização de latência na Análise de big data. No parâmetro Format, é possível editar os seguintes valores: 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Sequência de caracteres de hora. A unidade de tempo mostrada na visualização de latência, como dia ou semana. Certifique-se de alterar a string de hora ao alterar a dimensão de hora. </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Deslocamento. Um número inteiro igual ao negativo do valor para Tempo anterior. Por exemplo, se a opção Tempo anterior for 7, o deslocamento deverá ser -7. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Hora anterior </p> </td> 
      <td colname="col2"> <p>O tempo máximo (expresso nas unidades da dimensão Tempo) antes do evento para o qual a latência é calculada. Se esse valor estiver definido como 0 ou não estiver definido, a latência será calculada somente para a direção direta. </p> <p>Se você alterar esse valor, certifique-se de alterar o valor de deslocamento no parâmetro Format: O deslocamento é o negativo do valor para Tempo anterior. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Hora após </p> </td> 
      <td colname="col2"> <p>A quantidade máxima de tempo (expressa nas unidades da dimensão Tempo) após o evento para o qual a latência é calculada. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salve o [!DNL .vw] arquivo na pasta Usuário\*nome do perfil de trabalho*\Work.

   Veja a seguir as configurações para a dimensão de latência padrão:

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   Na seguinte dimensão de latência, a latência de cada evento de sessão é calculada em horas e Tempo antes é definido como zero. Portanto, a latência é calculada apenas para as sessões que ocorreram dentro de 24 horas após o evento definido.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
