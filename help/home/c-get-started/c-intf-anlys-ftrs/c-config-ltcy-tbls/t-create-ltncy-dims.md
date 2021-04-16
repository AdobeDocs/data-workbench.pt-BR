---
description: As dimensões de latência são construídas de uma dimensão contável principal, como Sessões, e uma dimensão de tempo, como Dia.
title: Criar uma dimensão de latência
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
exl-id: 38b470ef-9409-455b-b2b8-b0391f80b800
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 2%

---

# Criar uma dimensão de latência{#create-a-latency-dimension}

As dimensões de latência são construídas de uma dimensão contável principal, como Sessões, e uma dimensão de tempo, como Dia.

Ao criar uma tabela de latência no Data Workbench, você adiciona automaticamente uma dimensão de latência ao arquivo de visualização (.vw). É possível editar a dimensão de latência de uma tabela seguindo as etapas abaixo.

**Para editar uma dimensão de latência**

1. Abra a tabela de latência criada em um editor de texto, como o Bloco de notas. Ela está localizada na pasta User > `working profile name` > Work no diretório de instalação do Data Workbench.

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

1. Edite os valores dos parâmetros Nome, Nível, Clipe, Tempo, Formato, Tempo antes ou Tempo após usando a tabela a seguir como guia:

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Para este parâmetro... </th> 
      <th colname="col2" class="entry"> Fornecer essas informações... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Nome </p> </td> 
      <td colname="col2"> <p>Opcional. O nome da dimensão de latência que aparece no menu de contexto ao clicar com o botão direito do mouse no rótulo ou nos elementos da dimensão. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Nível </p> </td> 
      <td colname="col2"> <p>Uma dimensão contável que é a principal da dimensão de latência. Os exemplos incluem Sessão, Visitante e Exibição de página. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Clip </p> </td> 
      <td colname="col2"> <p>Uma dimensão contável que tem uma relação um para muitos com o nível da dimensão de latência. A latência não é calculada entre os limites dessa dimensão. Por exemplo, se você especificar um nível de Exibição de página e um clipe de Sessão, as latências são calculadas para as exibições de página que ocorreram durante a mesma sessão do evento. </p> <p>Para obter informações sobre as dimensões um para muitos (simples), consulte o <i>Guia de Configuração do Conjunto de Dados</i>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Hora </p> </td> 
      <td colname="col2"> <p>A dimensão usada para medir o tempo decorrido da dimensão de latência. Essa dimensão pode ser uma dimensão de tempo, como Dia ou Hora, ou uma dimensão contável, como Visitante, Sessão ou Exibição de página. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Formato </td> 
      <td colname="col2"> <p>Opcional. Especifica a aparência da visualização de latência no Data Workbench. No parâmetro Format , é possível editar os seguintes valores: 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Sequência de caracteres de hora. A unidade de tempo mostrada na visualização de latência, como dia ou semana. Certifique-se de alterar a string de hora quando alterar a dimensão de tempo. </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Deslocamento. Um número inteiro igual ao negativo do valor para Tempo antes. Por exemplo, se Tempo antes for 7, o deslocamento deverá ser -7. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Hora antes </p> </td> 
      <td colname="col2"> <p>A quantidade máxima de tempo (expressa nas unidades da dimensão Tempo) antes do evento para o qual a latência é calculada. Se esse valor for definido como 0 ou não estiver definido, a latência será calculada somente para a direção direta. </p> <p>Se você alterar esse valor, altere o valor de deslocamento no parâmetro Format : O deslocamento é o negativo do valor para Tempo antes. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Hora após </p> </td> 
      <td colname="col2"> <p>A quantidade máxima de tempo (expressa nas unidades da dimensão Tempo) após o evento para o qual a latência é calculada. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Salve o arquivo [!DNL .vw] na pasta User\*nome do perfil de trabalho*\Work .

   A seguir estão as configurações para a dimensão de latência padrão:

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
