---
description: O marketing do seu site pode envolver a colocação de anúncios na forma de imagem ou outros arquivos de mídia avançada (servidos do seu servidor da Web) em sites de terceiros.
title: Medir impressão de anúncio
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# Medir impressão de anúncio{#measuring-advertisement-impression}

O marketing do seu site pode envolver a colocação de anúncios na forma de imagem ou outros arquivos de mídia avançada (servidos do seu servidor da Web) em sites de terceiros.

Nesses casos, você pode medir a impressão do anúncio em um navegador e o click-through subsequente, se ocorrer, no URL de destino do anúncio no site.

Para anúncios no formato de imagens, anexar [!DNL Log=1] à sequência de consulta resulta na solicitação de imagem e, portanto, na impressão do anúncio, sendo capturado por [!DNL Sensor] para fins de análise.

```
<!—REFERENCE IMPRESSION TAG->
<IMG SRC="https://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=https://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| Dados Coletados | Explicação | Exemplo |
|---|---|---|
| v_ic= | Valor que indica a campanha de impressão | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | Valor que indica o ativo da campanha de impressão | v_ica=&quot;72890ab&quot; |
| v_icr= | Valor que indica o referenciador da campanha de impressão | v_icr=&quot;https://money.cnn.com/markets/ |

Além de anexar [!DNL Log=1] à solicitação de imagem, um identificador deve ser adicionado ao URL que leva do anúncio à página de destino em seu site para rastrear o anúncio que levou ao click-through e rastrear o click-through de volta para a campanha específica desse anúncio.

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=https://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Dados Coletados </th>
   <th colname="col2" class="entry"> Explicação </th>
   <th colname="col3" class="entry"> Exemplo </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> v_c= </td>
   <td colname="col2"> Valor que indica a campanha Click-through </td>
   <td colname="col3"> v_c="CAMPAIGN1" </td>
  </tr>
  <tr>
   <td colname="col1"> v_ca= </td>
   <td colname="col2"> Valor que indica o ativo de campanha Click-through </td>
   <td colname="col3"> v_ca="72890ab" </td>
  </tr>
  <tr>
   <td colname="col1"> v_cr= </td>
   <td colname="col2"> Valor que indica o referenciador de campanha Click-through </td>
   <td colname="col3"> <p> <span class="filepath"> v_cr="https://money.cnn.com/</span> </p> <p>mercados/ </p> </td>
  </tr>
 </tbody>
</table>
