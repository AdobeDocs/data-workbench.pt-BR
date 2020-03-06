---
description: O sensor, quando usado em um servidor, pode coletar campos de dados de eventos de qualquer solicitação HTTP válida ou cabeçalho de resposta ou variável disponível para ele por meio da API do servidor.
solution: Insight
title: Campos extensíveis
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Campos extensíveis{#extensible-fields}

O sensor, quando usado em um servidor, pode coletar campos de dados de eventos de qualquer solicitação HTTP válida ou cabeçalho de resposta ou variável disponível para ele por meio da API do servidor.

Para coletar esses campos de dados, você deve especificar os campos de cabeçalho ou variáveis desejados no arquivo de [!DNL txlogd.conf] configuração para [!DNL Sensor].

* [Cabeçalhos de solicitação](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Variáveis de servidor](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## Request Headers {#section-22766692b45546d8bfc93dbe3bc9368f}

A seguir está a sintaxe para especificar um campo de cabeçalho de solicitação a ser coletado (por exemplo, Host, Accept-Encoding, Keep-Alive e assim por diante) em [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

Os dados coletados são registrados por [!DNL Sensor] um campo chamado &quot;cs(RequestHeaderName)&quot; nos [!DNL .vsl] arquivos criados pelo [!DNL data workbench server]. Por exemplo, para coletar o valor do cabeçalho da solicitação específica do cabeçalho da solicitação &quot;Host&quot;, digite &quot;Host LogHeader&quot; em [!DNL txlogd.conf]. Os dados são registrados no campo &quot;cs(Host)&quot; no registro de dados do evento.

## Variáveis de servidor {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] pode coletar campos de dados de cabeçalhos de resposta ou variáveis de servidor acessíveis por API usando entradas SpecialLogField que você incluir no [!DNL txlogd.conf] arquivo. Você também pode usar entradas &quot;SpecialLogField&quot; além ou em vez de entradas &quot;LogHeader&quot; para coletar cabeçalhos de solicitação. Consulte Cabeçalhos [de solicitação](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). A opção de cabeçalhos de solicitação permanece disponível para compatibilidade com versões anteriores.

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
   <td colname="col2"> O nome do campo no qual os dados coletados são registrados no registro de dados do evento e os arquivos <span class="filepath"> .vsl </span> criados pelo servidor da análise de big data <span class="keyword"> </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Qualquer variável de servidor disponível para o <span class="wintitle"> Sensor </span> por meio da API do servidor </p> <p>Exemplo: response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> estágio </td> 
   <td colname="col2"> <p>Vys_log ou vys_cookie </p> <p>A especificação do estágio exige que você saiba quais variáveis de servidor estão disponíveis para vys_log e vys_cookie. </p> <p>Exemplo: Para a serverVariable response.p3p, você deve digitar vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

Para obter ajuda sobre como configurar [!DNL Sensor] a coleta de campos extensíveis de registro de dados de eventos, entre em contato com os Serviços de consultoria da Adobe.
