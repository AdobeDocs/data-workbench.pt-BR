---
description: O sensor, quando usado em um servidor, pode coletar campos de dados do evento de qualquer solicitação HTTP ou cabeçalho de resposta ou variável HTTP válida disponível para ele por meio da API do servidor.
title: Campos extensíveis
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---

# Campos extensíveis{#extensible-fields}

{{eol}}

O sensor, quando usado em um servidor, pode coletar campos de dados do evento de qualquer solicitação HTTP ou cabeçalho de resposta ou variável HTTP válida disponível para ele por meio da API do servidor.

Para coletar esses campos de dados, você deve especificar os campos ou variáveis de cabeçalho desejados na variável [!DNL txlogd.conf] arquivo de configuração para [!DNL Sensor].

* [Cabeçalhos de solicitação](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Variáveis de servidor](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## Cabeçalhos de solicitação {#section-22766692b45546d8bfc93dbe3bc9368f}

A seguir está a sintaxe para especificar um campo de cabeçalho de solicitação a ser coletado (por exemplo, Host, Aceitar-Codificação, Manter-Vivo e assim por diante) em [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

Os dados coletados são registrados por [!DNL Sensor] para um campo chamado &quot;cs(RequestHeaderName)&quot; no [!DNL .vsl] arquivos criados pela [!DNL data workbench server]. Por exemplo, para coletar o valor do cabeçalho da solicitação específico do cabeçalho da solicitação &quot;Host&quot;, você digita &quot;LogHeader Host&quot; em [!DNL txlogd.conf]. Os dados são registrados no campo &quot;cs(Host)&quot; no registro de dados do evento.

## Variáveis de servidor {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] O pode coletar campos de dados de cabeçalhos de resposta ou variáveis de servidor acessíveis para API usando entradas SpecialLogField que você inclui na variável [!DNL txlogd.conf] arquivo. Você também pode usar entradas &quot;SpecialLogField&quot; além ou em vez de entradas &quot;LogHeader&quot; para coletar cabeçalhos de solicitação. Consulte [Cabeçalhos de solicitação](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). A opção de cabeçalhos de solicitação permanece disponível para compatibilidade com versões anteriores.

A seguir está a sintaxe para especificar um &quot;SpecialLogField&quot; em [!DNL txlogd.conf]:

```
SpecialLogField cs(log field) = serverVariable stage
```

A tabela a seguir inclui descrições dos componentes de uma entrada &quot;SpecialLogField&quot;.

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(log field) </td> 
   <td colname="col2"> O nome do campo no qual os dados coletados são registrados no registro de dados do evento e o <span class="filepath"> .vsl </span> arquivos criados pela <span class="keyword"> servidor do Data Workbench </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Qualquer variável de servidor que esteja disponível para <span class="wintitle"> Sensor </span> por meio da API do servidor </p> <p>Exemplo: response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>Vys_log ou vys_cookie </p> <p>A especificação do estágio requer que você saiba quais variáveis de servidor estão disponíveis para vys_log e vys_cookie. </p> <p>Exemplo: Para serverVariable response.p3p, você deve inserir vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

Para obter ajuda na configuração [!DNL Sensor] para coletar campos extensíveis de registro de dados do evento, entre em contato com os Serviços de consultoria do Adobe.
