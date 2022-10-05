---
description: O perfil Attribution é um perfil herdado e pronto para soltar. Em combinação com o perfil do Adobe SC e o feed de dados do Analytics (SC/Insight), o perfil pode ser implantado para expor rapidamente novos modelos de atribuição em canais digitais.
title: Implantar o perfil de atribuição
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
exl-id: 287e1710-7e74-4904-b258-7b811ad484b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 3%

---

# Implantar o perfil de atribuição{#deploying-the-attribution-profile}

{{eol}}

O perfil Attribution é um perfil herdado e pronto para soltar. Em combinação com o perfil do Adobe SC e o feed de dados do Analytics (SC/Insight), o perfil pode ser implantado para expor rapidamente novos modelos de atribuição em canais digitais.

Depois de salvar o perfil de Atribuição no servidor primário, há duas etapas adicionais necessárias para integrá-lo ao perfil atual no [!DNL Profile] diretório: (1) Configure o arquivo Profile.cfg e (2) declare os campos obrigatórios.

## Configuração do arquivo Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Como todos os perfis, o perfil de Atribuição precisa ser adicionado ao [!DNL profile.cfg] arquivo. Como o perfil Attribution depende do perfil Adobe SC, o perfil do Adobe SC precisa ser listado primeiro no arquivo de configuração, antes do perfil de Atribuição.

>[!NOTE]
>
>Essas etapas exigirão uma retransformação do conjunto de dados.

1. Abra o [!DNL profile.cfg] na pasta de perfil personalizada. (Abrir em [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Se o Perfil de atribuição não estiver listado no arquivo de configuração, adicione-o à lista. ![](assets/new_profile_cfg.png)

1. Certifique-se de que o **[!UICONTROL Attribution]** é listada abaixo da variável **[!UICONTROL Adobe SC]** sequência de caracteres do perfil.

1. Salve as [!DNL profile.cfg] e depois salve-o no servidor a partir do Gerenciador de perfis.

## Declaração dos campos obrigatórios {#section-23d4273af0c34b7a85ae3430e2c9350e}

O perfil Attribution pega campos predefinidos e com uma série de transformações expõe esses campos de maneiras novas e úteis por meio de dimensões estendidas. Para fornecer o valor mais imediato, o perfil Attribution depende dos campos disponíveis com o perfil Adobe SC.

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variáveis padrão </th> 
   <th colname="col2" class="entry"> Nome do campo e posição do decodificador (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campanha </td> 
   <td colname="col2"> <p>x-campaign, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Canais de marketing </td> 
   <td colname="col2"> <p>x-va_closer_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento de pedido </td> 
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchaseid, nº 200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Receita </td> 
   <td colname="col2"> x-revenue, nº 205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unidades </td> 
   <td colname="col2"> <p>x-units, nº 204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Verifique se esses campos estão declarados no Grupo decodificador usado para definir a fonte de dados do Adobe Analytics. O grupo decodificador padrão é fornecido em [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Verifique se esses campos estão declarados no **[!UICONTROL Fields]** da seção [!DNL SC Fields.cfg] arquivo. Esse arquivo pode ser localizado em [!DNL Dataset\Log Processing\SC Fields.cfg].

## Adições de atribuição e solução de problemas {#section-168133a8a1a54e1281e532033878d246}

O perfil Attribution adicionou um arquivo de configuração, [!DNL 0a_Marketing Channels.cfg], que copia o valor da variável [!DNL x-va_closer_detail] em um novo campo chamado [!DNL x-marketing-channel], quando a variável [!DNL x-va_instance_event] corresponde a &quot;1&quot;. Ambos [!DNL x-va_closer_detail] e [!DNL x-va_instant_event] são decodificados por padrão e passados da decodificação nos pacotes instalados disponíveis quando você atualiza para a versão 6.2.

O [!DNL x-marketing-channel] é então usado na dimensão Simples chamada Canal de marketing.

>[!IMPORTANT]
>
>Se você alterou seus perfis removendo campos não utilizados anteriormente que estão sendo usados, verifique se a variável [!DNL x-va_closer_detail] e [!DNL x-va_instance_event] Os campos estão sendo decodificados e passados para uso.

Se os campos estiverem ausentes, você receberá uma mensagem em seu status detalhado:

```
<b>x-va_closer_detail</b> is not available
```

ou

```
<b>x-va_instance_event</b> is not available
```
