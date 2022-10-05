---
description: Configure as dimensões de tempo para serem exibidas corretamente na localidade.
title: Localização de dimensões de tempo
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
exl-id: 950fe70b-a687-4b9c-b29f-555139740809
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Localização de dimensões de tempo{#localizing-time-dimensions}

{{eol}}

Configure as dimensões de tempo para serem exibidas corretamente na localidade.

Você pode configurar o formato exibido das dimensões de tempo com base na localidade na variável **[!DNL Standard Time Dimensions.cfg]** (localizado por padrão em **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard Time Dimension.cfg]**).

Por exemplo, na América do Norte, você pode expressar a data em 3 de maio de 2015 como 03/05/15, ou **`%m/%d/%y`**. No entanto, em outras partes do mundo isso poderia ser interpretado como `%d/%m/%y`ou 5 de março de 2015 devido a uma ambiguidade nos valores. Para evitar essa situação, um administrador pode querer alterar o formato exibido para corresponder às expectativas dos usuários em uma localidade.

## 1. Substituir Dimension de tempo padrão no horário padrão Dimension.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

Para ativar esse recurso, o administrador deve substituir os padrões editando as dimensões de tempo existentes ou criando novas dimensões de tempo com parâmetros adicionais.

Segue-se um exemplo de uma dimensão de tempo modificada.

O **Formato** valores para Semana, Hora, Dia, Mês e Hora do dia são definidos para os padrões no exemplo.

>[!NOTE]
>
>Se essas linhas forem omitidas, o comportamento da Data Workbench não será alterado e a dimensão será compilada usando os padrões.

```
Transformation Include = TransformationInclude:  
  Extended Dimensions = vector: 1 items 
    0 = TimeDimensions:  
      Comments = Comment: 0 items 
      Dimensions = map:  
        Day = string: Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Hour of Day = string: Hour of Day 
        Month = string: Month 
        Week = string: Week 
      Hidden = bool: false 
      Input Time (1970 epoch) = string: x-unixtime 
      Week Format = string:  
  %m/%d/%y
      Hour Format = string:  
  %x %H:%M 
      Day Format = string:  
  %x
      Month Format = string:  
  %b '%y
      Hour Of Day Format = string:  
  %#H:%M
      Name = string: Visit Time 
      Parent = string: Visit 
      Week Start Day = string: Mon 
  Transformations = vector: 0 items
```

![](assets/6_4_time_format.png)

## 2. Configurar o arquivo meta.cfg {#section-5e077d3298dd48fda7f7bb16af9ea00c}

Além disso, é necessário que o administrador do pacote adicione esses parâmetros e seus padrões ao perfil **[!DNL meta.cfg]** arquivo. Isso permite editar a partir da estação de trabalho.

Aqui está um trecho de um **[!DNL meta.cfg]** arquivo.

```
dimensions = vector: 6 items 
  0 = Template: 
    ...
  ...
  5 = Template: 
    name = string: Time Dimensions 
    value = TimeDimensions: 
      Name = string:  
      Comments = Comment: 0 items 
      Hidden = bool: false 
       
  Week Format = string: %d/%m/%y 
       Hour Format = string: %x %H:%M 
       Day Format = string: %x 
       Month Format = string: %b '%y 
       Hour Of Day Format = string: %#H:%M</b> 
      Input Time (1970 epoch) = string:  
      Parent = string:  
      Week Start Day = string: Mon 
      Dimensions = map: 
        Hour of Day = string: Hour of Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Day = string: Day 
        Week = string: Week 
        Month = string: Month
```

Este é um exemplo de um **[!DNL meta.cfg]** na estação de trabalho:

![](assets/dwb_time_format.png)

O administrador poderá então acessar o **Gerenciador de arquivos**, abra o(s) arquivo(s) onde as dimensões de tempo estão configuradas (por exemplo, **[!DNL Standard Time Dimensions.cfg]**) e editá-las usando na estação de trabalho.
