---
description: O perfil de Atribuição é um perfil herdado, pronto para soltar. Em combinação com o perfil do Adobe SC e o feed de dados do Analytics (SC/Insight), o perfil pode ser implantado para expor rapidamente novos modelos de atribuição em canais digitais.
title: Implantação do perfil de atribuição
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Implantação do perfil de atribuição{#deploying-the-attribution-profile}

O perfil de Atribuição é um perfil herdado, pronto para soltar. Em combinação com o perfil do Adobe SC e o feed de dados do Analytics (SC/Insight), o perfil pode ser implantado para expor rapidamente novos modelos de atribuição em canais digitais.

Depois de salvar o perfil de Atribuição no servidor primário, há duas etapas adicionais necessárias para integrá-lo ao perfil atual no [!DNL Profile] diretório: (1) Configure o arquivo Profile.cfg e (2) Declare os campos obrigatórios.

## Configuração do arquivo Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Como todos os perfis, o perfil de Atribuição precisa ser adicionado ao [!DNL profile.cfg] arquivo. Como o perfil de Atribuição depende do perfil do Adobe SC, o perfil do Adobe SC precisa ser listado primeiro no arquivo de configuração antes do perfil de Atribuição.

>[!NOTE]
>
>Essas etapas exigirão uma retransformação do conjunto de dados.

1. Abra o [!DNL profile.cfg] arquivo na sua pasta de perfil personalizada. (Abra em [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Se o perfil de Atribuição não estiver listado no arquivo de configuração, adicione-o à lista. ![](assets/new_profile_cfg.png)

1. Verifique se a **[!UICONTROL Attribution]** string está listada abaixo da string do **[!UICONTROL Adobe SC]** perfil.

1. Salve o arquivo atualizado [!DNL profile.cfg] e salve-o no servidor a partir do Gerenciador de perfis.

## Declaração dos campos obrigatórios {#section-23d4273af0c34b7a85ae3430e2c9350e}

O perfil de Atribuição usa campos predefinidos e com uma série de transformações expõe esses campos de formas novas e úteis por meio de dimensões estendidas. Para fornecer o valor mais imediato, o perfil de Atribuição depende dos campos disponíveis com o perfil do Adobe SC.

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
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Receita </td> 
   <td colname="col2"> x-Revenue, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unidades </td> 
   <td colname="col2"> <p>x-unit, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Verifique se esses campos estão declarados no Grupo decodificador usado para definir a fonte de dados do Adobe Analytics. O grupo decodificador padrão é fornecido em [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Verifique se esses campos estão declarados na **[!UICONTROL Fields]** seção do [!DNL SC Fields.cfg] arquivo. Este arquivo pode ser localizado em [!DNL Dataset\Log Processing\SC Fields.cfg].

## Adições de atribuição e solução de problemas {#section-168133a8a1a54e1281e532033878d246}

O perfil de Atribuição adicionou um arquivo de configuração, [!DNL 0a_Marketing Channels.cfg], que copia o valor do [!DNL x-va_closer_detail] em um novo campo chamado [!DNL x-marketing-channel], quando o [!DNL x-va_instance_event] campo corresponde a &quot;1&quot;. Por padrão, [!DNL x-va_closer_detail] e ambos [!DNL x-va_instant_event] são decodificados e passados da decodificação nos pacotes instalados disponíveis quando você atualiza para a versão 6.2.

O [!DNL x-marketing-channel] campo é usado na dimensão Simples chamada de Canal de marketing.

>[!IMPORTANT]
>
>Se você alterou seus perfis removendo campos não utilizados anteriormente que estão sendo usados agora, verifique se os campos [!DNL x-va_closer_detail] e [!DNL x-va_instance_event] estão sendo decodificados e transmitidos para uso.

Se os campos estiverem ausentes, você receberá uma mensagem em seu status detalhado:

```
<b>x-va_closer_detail</b> is not available
```

ou

```
<b>x-va_instance_event</b> is not available
```

