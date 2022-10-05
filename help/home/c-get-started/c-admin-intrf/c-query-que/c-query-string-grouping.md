---
description: O Agrupamento de sequência de consulta permite integrar um grande número de campos juntos.
title: Agrupamento de sequência de consulta
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
exl-id: 4052cf7e-abdf-4e16-9f42-521c4e719786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# Agrupamento de sequência de consulta{#query-string-grouping}

{{eol}}

O Agrupamento de sequência de consulta permite integrar um grande número de campos juntos.

O Agrupamento de sequência de consulta é específico para cada perfil, mas funciona bem em transformações, como mostrado neste exemplo:

1. Crie os pares que deseja agrupar adicionando um arquivo de configuração personalizado ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]) e, em seguida, adicionar o Tipo de transformação *ParValorDoNomeDeBuild* como parâmetro.

   ```
   2 = BuildNameValuePair:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to build)
             Name = string: Custom Events 
             Output = string: x-event-list       
   ```

1. Crie um novo arquivo para extrair os dados condensados nos campos que deseja usar adicionando um arquivo de configuração personalizado ( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]) e, em seguida, adicionar o Tipo de transformação *ExtractNameValuePairs* como parâmetro.

   ```
   2 = ExtractNameValuePairs:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Field = string: x-event-list 
         Name = string: Custom Events 
         Output Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to extract) 
             Name = string: Custom Events 
             Output = string: x-event-list   
   ```

## Outros usos {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

Se você tiver muitos campos com evars, props e variáveis personalizadas, durante o processamento de log é possível criar um par de valores de nome para combinar campos em um relatório. Por exemplo, você pode criar pares de valor nomeado em campos combinados para reduzir o valor de [!DNL tempDB] tamanho do arquivo.

![](assets/query_string_grouping.png)
