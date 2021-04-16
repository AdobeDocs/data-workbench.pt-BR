---
description: Informações sobre configurações específicas da Web definidas nos arquivos de inclusão do conjunto de dados de transformação fornecidos com perfis do Adobe para o Site.
title: Configurações específicas da Web para transformação
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 1%

---

# Configurações específicas da Web para transformação{#web-specific-settings-for-transformation}

Informações sobre configurações específicas da Web definidas nos arquivos de inclusão do conjunto de dados de transformação fornecidos com perfis do Adobe para o Site.

As condições, dimensões e parâmetros definidos por essas configurações são criados durante a fase de transformação da construção do conjunto de dados.

* [Condição de exibição de página](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [Dimension de URI](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Dimension do referenciador](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Parâmetros da sessão](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Condição de exibição de página {#section-cc2807a12a88492f8b64a43234a1f835}

O [!DNL Page View Condition] é uma operação de condição que determina se uma entrada de log específica (ou seja, uma solicitação de página) deve ser incluída nos dados coletados sobre o histórico de exibição de página de um visitante. Quando a entrada de log satisfaz [!DNL Page View Condition], ela se torna um elemento da dimensão contável Exibição de página . Se uma entrada de log não atender a [!DNL Page View Condition], seus campos de dados ainda serão acessíveis por outras dimensões. Além da dimensão Exibição de página , as seguintes dimensões podem ser afetadas pelos resultados do [!DNL Page View Condition]:

* **[!DNL URI]e  [!DNL Page]:** essas dimensões são diretamente afetadas pelo  [!DNL Page View Condition]. Se uma determinada página não passar [!DNL Page View Condition,], ela não será incluída nas dimensões URI ou Page .

* **[!DNL Visitor Page Views]e  [!DNL Session Page Views]:** as dimensões Exibições de página do visitante e Exibições de página da sessão são uma contagem do número de páginas visualizadas por um visitante para ou em uma determinada sessão, respectivamente. As páginas filtradas pelo [!DNL Page View Condition] não fazem parte dessa contagem.

* **Número de sessão:** o  [!DNL Page View Condition] tem um efeito indireto na dimensão Número de sessão. A dimensão Número de sessão é criada antes de [!DNL Page View Condition]; portanto, ao considerar [!DNL Session Number] em relação ao [!DNL Page Views], é possível ter sessões sem exibições de página.

Sua implementação padrão de [!DNL Site] inclui um arquivo [!DNL Transformation Dataset Include] no qual a dimensão contável Exibição de página e [!DNL Page View Condition] relacionadas são definidas.

Para obter informações sobre dimensões contáveis, consulte [Dimension estendido](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar as configurações da condição de Exibição de página**

1. Abra o [!DNL Profile Manager] no perfil do conjunto de dados e abra o arquivo [!DNL Dataset\Transformation\Traffic\Page View.cfg] .

   >[!NOTE]
   >
   >Se você personalizou sua implementação de [!DNL Site], o arquivo no qual essas configurações existem pode ser diferente do local descrito.

1. Revise ou edite os valores dos parâmetros do [!DNL Page View Condition] conforme necessário. Use o exemplo a seguir como guia. Neste arquivo, o [!DNL Page View Condition] é definido por uma transformação [!DNL Copy]. Observe que esse arquivo também contém a definição da dimensão contável Exibição de página .

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Para obter informações sobre dimensões contáveis, consulte [Dimension estendido](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Para obter informações sobre a transformação [!DNL Copy], consulte [Transformações de dados](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Salve o arquivo clicando com o botão direito do mouse em **[!UICONTROL (modified)]** na parte superior da janela e clique em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente tenham efeito, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, onde o nome do perfil é o nome do perfil do conjunto de dados ou do perfil herdado ao qual pertence o arquivo de inclusão do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.

## Dimension do URI {#section-348f7e9099d049d197a7cdcbc8a6c234}

Se você estiver trabalhando com [!DNL Site], precisará definir a dimensão URI cujos elementos são os sistemas URI das páginas do site visualizadas. Sua implementação padrão inclui um arquivo [!DNL Transformation Dataset Include] no qual a dimensão simples de URI é definida.

Para obter informações sobre dimensões simples, consulte [Dimension estendido](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar as configurações da dimensão URI**

1. Abra o [!DNL Profile Manager] no perfil do conjunto de dados e abra o arquivo [!DNL Dataset\Transformation\Traffic\URI.cfg] .

   >[!NOTE]
   >
   >Se você personalizou sua implementação de [!DNL Site], o arquivo no qual essas configurações existem pode ser diferente do local descrito.

1. Revise ou edite os valores dos parâmetros do arquivo, conforme desejado. Use o exemplo a seguir e as informações como guias.

![](assets/cfg_WebParameters_URI.png)

As configurações da dimensão URI incluem os dois parâmetros a seguir:

* **Diferenciação de maiúsculas e minúsculas:** verdadeiro ou falso. Se verdadeiro, letras maiúsculas e minúsculas são consideradas na identificação de páginas exclusivas. O valor padrão é true.
* **Elementos máximos:** o número máximo de elementos (ou seja, URIs) para a dimensão URI. O valor padrão é 32768.

   >[!NOTE]
   >
   >Alterar esse valor pode causar sérios problemas de desempenho. Não altere esse valor sem consultar o Adobe.

* Salve o arquivo [!DNL URI.cfg] clicando com o botão direito do mouse em **[!UICONTROL (modified)]** na parte superior da janela e, em seguida, clique em **[!UICONTROL Save]**.

* Para que as alterações feitas localmente tenham efeito, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, onde o nome do perfil é o nome do perfil do conjunto de dados ou do perfil herdado ao qual pertence o arquivo de inclusão do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.

## Dimension do referenciador {#section-8a97ec34d18b4814b5f95495ac4f8638}

Se estiver trabalhando com [!DNL Site], será necessário definir a dimensão Referenciador cujos elementos consistem nos domínios de segundo nível dos referenciadores das primeiras entradas de log em todas as sessões. Sua implementação padrão inclui um arquivo [!DNL Transformation Dataset Include] no qual a dimensão simples do Referenciador é definida.

Para obter informações sobre dimensões simples, consulte [Dimension estendido](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar as configurações da dimensão Referenciador**

1. Abra o [!DNL Profile Manager] no perfil do conjunto de dados e abra o arquivo [!DNL Dataset\Transformation\Traffic\Referrer.cfg] .

   >[!NOTE]
   >
   >Se você personalizou sua implementação de [!DNL Site], o arquivo no qual essas configurações existem pode ser diferente do local descrito.

1. Revise ou edite os valores dos parâmetros do arquivo, conforme desejado. Use o exemplo a seguir e as informações como guias.

   ![](assets/cfg_WebParameters_Referrer.png)

   As configurações da dimensão Referenciador incluem o parâmetro Elementos Máximos, que especifica o número máximo de elementos (ou seja, referenciadores) para a dimensão Referenciador. O valor padrão é 32768.

   >[!NOTE]
   >
   >No exemplo acima, o parâmetro [!DNL Maximum Elements] é definido como 0. Quando esse parâmetro é definido como 0, o servidor do Data Workbench usa seu valor padrão interno de 32768.

1. Salve o arquivo [!DNL Referrer.cfg] clicando com o botão direito do mouse em **[!UICONTROL (modified)]** na parte superior da janela e, em seguida, clique em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente tenham efeito, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, onde o nome do perfil é o nome do perfil do conjunto de dados ou do perfil herdado ao qual pertence o arquivo de inclusão do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.

## Parâmetros da sessão {#section-0a209b0c504041a5801f7f71a963c8b1}

Se você estiver trabalhando com [!DNL Site], poderá especificar parâmetros que definem os limites da sessão de um visitante em um site. Esses parâmetros são válidos somente quando definidos em um arquivo [!DNL Transformation Dataset Include] em sua implementação [!DNL Site].

Os parâmetros a seguir são exclusivos, pois podem ser membros do [!DNL Transformation Dataset Include] vetor [!DNL Parameters] do arquivo ou podem ser listados como parâmetros individuais no arquivo [!DNL Transformation.cfg]. Um parâmetro pode ser definido exatamente uma vez, de modo que esses parâmetros sejam definidos no arquivo [!DNL Transformation.cfg]ou no vetor [!DNL Parameters] do arquivo de inclusão do conjunto de dados - não em ambos os arquivos.
**Duração máxima da sessão e Tempo limite da sessão**

Duração máxima da sessão e Tempo limite da sessão são parâmetros de string que definem a duração da sessão de um visitante. Esses parâmetros funcionam com o parâmetro Domínios internos para determinar a duração da sessão.

Duração máxima da sessão especifica a duração mais longa da sessão antes de uma nova sessão ser iniciada. Isso mantém as páginas da Web que têm atualização automática de conteúdo da criação de sessões que são arbitrariamente longas. Se o referenciador de um clique for definido como uma das entradas no parâmetro Domínios internos, esse tempo limite será usado para definir o fim de uma sessão. Nenhuma sessão pode ser maior do que a Duração máxima da sessão especificada, independentemente de quantos cliques ela contém. O valor recomendado é de 48 horas.

O Tempo limite da sessão especifica a quantidade de tempo que precisa ser passada entre as entradas de log de um determinado visitante para determinar o fim de uma sessão e o início de uma nova sessão (ou seja, o tempo limite típico usado para definir uma sessão de usuário). O valor recomendado desse parâmetro é de 30 minutos. Se o referenciador de um clique não estiver definido como um dos referenciadores no parâmetro Domínios internos, esse tempo limite será usado para definir a sessão. Se cs(referrer-domain) para uma entrada de log estiver na lista de domínios internos, a Duração máxima da sessão determinará se a entrada de log atual faz parte de uma sessão existente ou se inicia uma nova sessão.

Considere uma situação em que um visitante é chamado de fora do computador por um período maior que o Tempo limite da sessão enquanto está no meio da navegação no site. Ao voltar, ele continua navegando onde parou. Como o visitante nunca sai do site ou fecha seu navegador, o cs(referrer-domain) desse próximo clique é o mesmo que o domínio interno e sua sessão original permanece ativa, desde que a configuração Duração máxima da sessão não seja alcançada. Se o domínio do site for listado como um domínio interno e o tempo limite máximo não for atingido, a interação do visitante será exibida como uma única sessão e não como duas sessões separadas. No entanto, se o visitante retornar ao computador e o próximo clique tiver um referenciador externo (ou em branco), uma nova sessão será iniciada.

>[!NOTE]
>
>A [!DNL Sessionize] transformação [!DNL Timeout Condition] também desempenha um papel na determinação da duração de uma sessão do visitante. Se Tempo limite da sessão e Duração máxima da sessão não se aplicarem, [!DNL Timeout Condition] é verificado para determinar se uma entrada de log deve ser considerada o início de uma nova sessão. Para obter mais informações, consulte [Transformações de dados](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Para editar os parâmetros Duração máxima da sessão e Tempo limite da sessão**

Se você estiver trabalhando com [!DNL Site], sua implementação padrão provavelmente incluirá um arquivo [!DNL Transformation Dataset Include] no qual os nomes e os valores recomendados desses parâmetros serão especificados.

1. Abra o [!DNL Profile Manager] no perfil do conjunto de dados e vá para [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Se você personalizou a implementação de [!DNL Site], o arquivo no qual esses parâmetros são definidos pode ser diferente do local descrito.

1. Edite os valores dos parâmetros conforme desejado. Certifique-se de especificar as unidades desejadas (minutos, horas e assim por diante).

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Salve o arquivo [!DNL Session Parameters.cfg] clicando com o botão direito do mouse em **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente tenham efeito, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, onde o nome do perfil é o nome do perfil do conjunto de dados ou do perfil herdado ao qual pertence o arquivo de inclusão do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.

**[!DNL Internal Domains]**

[!DNL Internal Domains] é um parâmetro de vetor que lista hosts de nível de domínio (referenciadores internos) que devem ser tratados como parte de um site específico. Esses hosts são removidos da dimensão do referenciador (que é uma lista das informações externas do referenciador). Quando cs(referrer-domain) corresponde a qualquer uma das strings listadas no conjunto de domínios internos, o Tempo limite da sessão é ignorado e a Duração máxima da sessão é usada para determinar a duração da sessão.

O parâmetro de Domínios internos também pode ser usado para impedir o início de uma nova sessão quando os visitantes se movem entre os vários domínios associados de uma empresa, de forma a exceder o tempo limite da sessão. Por exemplo, considere uma empresa que tem partes de seu site divididas em dois domínios: um é registrado ( [!DNL xyz.com]) e o outro não é registrado ( [!DNL xyz-unlogged.com]). Se esses sites forem integrados de forma a facilitar a movimentação contínua de tráfego entre os dois domínios, não é desejável gerar uma sessão diferente sempre que o visitante se mover do domínio [!DNL xyz-unlogged.com] de volta para o domínio [!DNL xyz.com]. Listar [!DNL xyz-unlogged.com] como um domínio interno impede que as sessões sejam divididas em várias sessões como resultado do tráfego nesses dois domínios, desde que a configuração Duração máxima da sessão não seja alcançada.

**Para adicionar um domínio interno**

Se você estiver trabalhando com [!DNL Site], sua implementação padrão incluirá um arquivo [!DNL Transformation Dataset Include] para definir o parâmetro Domínios internos . Nesse arquivo, o parâmetro é nomeado; basta inserir os domínios internos que deseja incluir e salvar o arquivo atualizado.

1. Abra o [!DNL Profile Manager] no perfil do conjunto de dados e vá para [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Se você personalizou a implementação de [!DNL Site], o arquivo no qual o parâmetro de Domínios internos é definido pode ser diferente do local descrito.

1. Clique com o botão direito do mouse **[!UICONTROL Value]** para o parâmetro de vetor de Domínios internos e clique em **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Edite os valores conforme desejado.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Salve o arquivo [!DNL Internal Domains.cfg] clicando com o botão direito do mouse em **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente tenham efeito, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na coluna [!DNL User] e clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***, onde o nome do perfil é o nome do perfil do conjunto de dados ou do perfil herdado ao qual pertence o arquivo de inclusão do conjunto de dados.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pelo Adobe, pois as alterações são substituídas ao instalar atualizações nesses perfis.
