---
description: Ao criar uma camada de ponto de elemento usando pontos dinâmicos, os dados de latitude e longitude são incorporados em cada elemento da dimensão.
title: Definir camadas de ponto de elemento usando pontos dinâmicos
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
exl-id: ad849fe7-b909-40ef-835f-f1764e008de9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

---

# Definir camadas de ponto de elemento usando pontos dinâmicos{#defining-element-point-layers-using-dynamic-points}

Ao criar uma camada de ponto de elemento usando pontos dinâmicos, os dados de latitude e longitude são incorporados em cada elemento da dimensão.

Para definir uma camada de ponto de elemento usando pontos dinâmicos, você deve criar ou já ter disponível o seguinte:

* **Uma dimensão**, definida no  [!DNL Transformation.cfg] arquivo ou em um conjunto de dados de transformação, inclui um arquivo, no qual cada elemento contém a string &quot;latitude, longitude&quot; ou &quot;latitude, longitude, nome&quot;.

   Para obter etapas para criar uma dimensão, consulte o *Guia de Configuração de Conjunto de Dados*.

* **Um** arquivo de camada que especifica a dimensão relacionada.

   Para obter mais informações sobre o formato necessário do arquivo de camada, consulte [Formato de arquivo de camada de ponto de elemento](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>Ao usar [!DNL Dynamic Points], é essencial garantir que a cardinalidade da dimensão especificada no arquivo de camada seja razoável. Se cada linha de um conjunto de dados tiver uma latitude e longitude diferentes, a dimensão preenche rapidamente e a maioria das linhas se encaixa em um elemento de Elementos pequenos. Como o elemento Elementos pequenos não tem latitude e longitude, ele não aparece no globo.

## Formato de arquivo de camada de ponto de elemento {#section-bbcc2baa2f754dba81eba93339a97cbd}

Cada arquivo de camada de ponto de elemento usando pontos dinâmicos deve ser formatado usando o seguinte modelo:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_71AD13D7A9234782A4495DFBBD959F76"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parâmetro </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensão </td> 
   <td colname="col2"> <p>O nome da dimensão (definido em um arquivo de configuração de transformação), que deve conter elementos com a string "latitude, longitude" ou "latitude, longitude, nome", conforme mostrado nos exemplos a seguir: 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181, - 77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35.3317, 77.8126, Em algum lugar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Métrica </td> 
   <td colname="col2"> O nome da métrica que é avaliada pela dimensão especificada no parâmetro Dimension. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pontos dinâmicos </td> 
   <td colname="col2"> Ativa Pontos Dinâmicos. Defina como true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escala </td> 
   <td colname="col2"> Opcional. Valor usado para dimensionar os pontos na camada. O valor padrão é 100. Valores maiores tornam os pontos maiores e valores menores os tornam menores. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cor do canal </td> 
   <td colname="col2"> Opcional. O vetor de cores RGB, que é expresso como (vermelho, verde, azul). Para cada cor no vetor, você pode inserir um valor de 0,0 a 1,0. Por exemplo, (1,0, 0,0, 0,0) é vermelho vivo e (0,5, 0,5, 0,5) é cinza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modo de renderização </td> 
   <td colname="col2"> <p>Opcional. Valor inteiro que representa o modo de renderização a ser usado para a camada. Os três modos disponíveis são os seguintes: 
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">Modo de renderização 1. O tamanho dos pontos é definido no espaço da tela (os pontos permanecem com um tamanho constante em relação à tela do computador). Os pontos são renderizados usando polígonos, de modo que não há limite máximo no tamanho do ponto. Este é o modo de renderização padrão. </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">Modo de renderização 2. O tamanho do ponto é definido no espaço mundial (os pontos permanecem em um tamanho constante em relação ao globo). Os pontos são renderizados usando polígonos, de modo que não há limite máximo no tamanho do ponto. </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">Modo de renderização 3. O tamanho do ponto é definido no espaço da tela. Os pontos são renderizados usando pontos suaves do OpenGL. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

O arquivo [!DNL IP Coordinates.layer] é formatado da seguinte maneira:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
