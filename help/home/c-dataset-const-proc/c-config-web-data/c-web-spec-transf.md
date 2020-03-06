---
description: Informações sobre configurações específicas da Web definidas no Conjunto de dados de transformação Incluir arquivos fornecidos com perfis da Adobe para o Site.
solution: Analytics
title: Configurações específicas da Web para transformação
topic: Data workbench
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Configurações específicas da Web para transformação{#web-specific-settings-for-transformation}

Informações sobre configurações específicas da Web definidas no Conjunto de dados de transformação Incluir arquivos fornecidos com perfis da Adobe para o Site.

As condições, dimensões e parâmetros definidos por essas configurações são criados durante a fase de transformação da construção do conjunto de dados.

* [Condição de exibição de página](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [Dimensão URI](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Dimensão do referenciador](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Parâmetros de sessão](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Condição de exibição de página {#section-cc2807a12a88492f8b64a43234a1f835}

A operação [!DNL Page View Condition] é uma condição que determina se uma entrada de log específica (ou seja, uma solicitação de página) deve ser incluída nos dados coletados sobre o histórico de visualização de página de um visitante. Quando a entrada de log atender à solicitação, [!DNL Page View Condition]ela se tornará um elemento da dimensão contável Exibição de página. Se uma entrada de log não atender a esses requisitos, [!DNL Page View Condition]seus campos de dados ainda serão acessíveis por outras dimensões. Além da dimensão Exibição de página, as seguintes dimensões podem ser afetadas pelos resultados do [!DNL Page View Condition]:

* **[!DNL URI]e[!DNL Page]:**Essas dimensões são diretamente afetadas pelo[!DNL Page View Condition]. Se a página especificada não for aprovada, não[!DNL Page View Condition,]será incluída nas dimensões URI ou Página.

* **[!DNL Visitor Page Views]e[!DNL Session Page Views]:**As dimensões Exibições de página do visitante e Exibições de página da sessão são uma contagem do número de páginas visualizadas por um visitante para ou em uma determinada sessão, respectivamente. As páginas filtradas pelo[!DNL Page View Condition]não fazem parte dessa contagem.

* **Número da sessão:** O [!DNL Page View Condition] tem um efeito indireto na dimensão Número da sessão. A dimensão Número da sessão é criada antes do [!DNL Page View Condition]; portanto, ao considerar [!DNL Session Number] em relação ao [!DNL Page Views], é possível ter sessões sem exibições de página.

A implementação padrão do inclui [!DNL Site] um [!DNL Transformation Dataset Include] arquivo no qual a dimensão contável Exibição de página e as relacionadas [!DNL Page View Condition] são definidas.

Para obter informações sobre dimensões contáveis, consulte Dimensões [estendidas](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar as configurações da Condição de exibição de página**

1. Abra o arquivo [!DNL Profile Manager] em seu perfil de conjunto de dados e abra o [!DNL Dataset\Transformation\Traffic\Page View.cfg] arquivo.

   >[!NOTE]
   >
   >Se você personalizou sua implementação do, [!DNL Site]o arquivo no qual essas configurações existem pode ser diferente do local descrito.

1. Revise ou edite os valores dos parâmetros do [!DNL Page View Condition] , conforme necessário. Use o exemplo a seguir como guia. Neste arquivo, o [!DNL Page View Condition] é definido por uma [!DNL Copy] transformação. Observe que esse arquivo também contém a definição da dimensão contável Exibição de página.

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Para obter informações sobre dimensões contáveis, consulte Dimensões [estendidas](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Para obter informações sobre a [!DNL Copy] transformação, consulte Transformações [de dados](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e, em seguida, clique em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

## Dimensão URI {#section-348f7e9099d049d197a7cdcbc8a6c234}

Se estiver trabalhando com [!DNL Site], é necessário definir a dimensão URI cujos elementos são os sistemas URI das páginas do site visualizadas. Sua implementação padrão inclui um [!DNL Transformation Dataset Include] arquivo no qual a dimensão simples de URI é definida.

Para obter informações sobre dimensões simples, consulte Dimensões [estendidas](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar as configurações da dimensão URI**

1. Abra o arquivo [!DNL Profile Manager] em seu perfil de conjunto de dados e abra o [!DNL Dataset\Transformation\Traffic\URI.cfg] arquivo.

   >[!NOTE]
   >
   >Se você personalizou sua implementação do, [!DNL Site]o arquivo no qual essas configurações existem pode ser diferente do local descrito.

1. Revise ou edite os valores dos parâmetros do arquivo, conforme desejado. Use o exemplo e as informações a seguir como guias.

![](assets/cfg_WebParameters_URI.png)

As configurações da dimensão URI incluem os dois parâmetros a seguir:

* **Diferenciação de maiúsculas e minúsculas:** Verdadeiro ou falso. Se verdadeiro, letras maiúsculas e minúsculas são consideradas na identificação de páginas exclusivas. O valor padrão é true.
* **Máximo de elementos:** O número máximo de elementos (ou seja, URIs) para a dimensão URI. O valor padrão é 32768.

   >[!NOTE]
   >
   >Alterar esse valor pode causar sérios problemas de desempenho. Não altere esse valor sem consultar a Adobe.

* Salve o [!DNL URI.cfg] arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e, em seguida, clique em **[!UICONTROL Save]**.

* Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

## Dimensão do referenciador {#section-8a97ec34d18b4814b5f95495ac4f8638}

Se você estiver trabalhando com [!DNL Site], será necessário definir a dimensão Referenciador cujos elementos consistem nos domínios de segundo nível dos referenciadores das primeiras entradas de log em todas as sessões. Sua implementação padrão inclui um [!DNL Transformation Dataset Include] arquivo no qual a dimensão simples do Referenciador é definida.

Para obter informações sobre dimensões simples, consulte Dimensões [estendidas](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar as configurações da dimensão Referenciador**

1. Abra o arquivo [!DNL Profile Manager] em seu perfil de conjunto de dados e abra o [!DNL Dataset\Transformation\Traffic\Referrer.cfg] arquivo.

   >[!NOTE]
   >
   >Se você personalizou sua implementação do, [!DNL Site]o arquivo no qual essas configurações existem pode ser diferente do local descrito.

1. Revise ou edite os valores dos parâmetros do arquivo, conforme desejado. Use o exemplo e as informações a seguir como guias.

   ![](assets/cfg_WebParameters_Referrer.png)

   As configurações da dimensão Referenciador incluem o parâmetro Elementos máximos, que especifica o número máximo de elementos (ou seja, referenciadores) para a dimensão Referenciador. O valor padrão é 32768.

   >[!NOTE]
   >
   >No exemplo acima, o [!DNL Maximum Elements] parâmetro é definido como 0. Quando esse parâmetro é definido como 0, o servidor da análise de big data usa seu valor padrão interno de 32768.

1. Salve o [!DNL Referrer.cfg] arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e, em seguida, clique em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

## Parâmetros de sessão {#section-0a209b0c504041a5801f7f71a963c8b1}

Se estiver trabalhando com [!DNL Site], você pode especificar parâmetros que definem os limites da sessão de um visitante em um site. Esses parâmetros são válidos somente quando definidos em um [!DNL Transformation Dataset Include] arquivo na sua [!DNL Site] implementação.

Os parâmetros a seguir são exclusivos porque podem ser membros do vetor do [!DNL Transformation Dataset Include] arquivo ou podem ser listados como parâmetros individuais no [!DNL Parameters] [!DNL Transformation.cfg]arquivo. Um parâmetro pode ser definido exatamente uma vez, de modo que esses parâmetros sejam definidos no [!DNL Transformation.cfg]arquivo ou no [!DNL Parameters] vetor do conjunto de dados inclua o arquivo - não em ambos os arquivos.
**Duração máxima da sessão e Tempo limite da sessão**

Duração máxima da sessão e Tempo limite da sessão são parâmetros de string que definem a duração da sessão de um visitante. Esses parâmetros funcionam com o parâmetro Domínios Internos para determinar a duração da sessão.

A Duração máxima da sessão especifica a duração mais longa da sessão antes de uma nova sessão ser iniciada. Isso mantém as páginas da Web que têm conteúdo automático atualizado ao criar sessões que são arbitrariamente longas. Se o referenciador de um clique estiver definido como uma das entradas no parâmetro Domínios internos, esse tempo limite será usado para definir o fim de uma sessão. Nenhuma sessão pode ser maior que a Duração máxima de sessão especificada, independentemente de quantos cliques ela contém. O valor recomendado é de 48 horas.

O Tempo limite da sessão especifica a quantidade de tempo que precisa ser transcorrido entre as entradas de log de um determinado visitante para determinar o fim de uma sessão e o início de uma nova sessão (ou seja, o tempo limite comum usado para definir uma sessão do usuário). O valor recomendado deste parâmetro é de 30 minutos. Se o referenciador de um clique não estiver definido como um dos referenciadores no parâmetro Domínios internos, esse tempo limite será usado para definir a sessão. Se cs(referrer-domain) para uma entrada de log estiver na lista de domínios internos, a Duração máxima da sessão determinará se a entrada de log atual faz parte de uma sessão existente ou se inicia uma nova sessão.

Considere uma situação em que um visitante é chamado fora do computador por um período maior que o Tempo limite da sessão enquanto está no meio da navegação no site. Ao voltar, ele continua navegando onde parou. Como o visitante nunca sai do site ou fecha seu navegador, o cs(referrer-domain) de seu próximo clique é o mesmo que o domínio interno e sua sessão original permanece ativa enquanto a configuração Duração máxima da sessão não for atingida. Se o domínio do site for listado como um domínio interno e o tempo limite máximo não for atingido, a interação do visitante será exibida como uma única sessão e não como duas sessões separadas. No entanto, se o visitante retornar ao computador e seu próximo clique tiver um referenciador externo (ou em branco), uma nova sessão será iniciada.

>[!NOTE]
>
>A [!DNL Sessionize] transformação [!DNL Timeout Condition] também desempenha um papel na determinação da duração da sessão de um visitante. Se o Tempo limite da sessão e a Duração máxima da sessão não se aplicarem, [!DNL Timeout Condition] é verificado se uma entrada de log deve ser considerada o início de uma nova sessão. For more information, see [Data Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Para editar os parâmetros Duração máxima da sessão e Tempo limite da sessão**

Se você estiver trabalhando com [!DNL Site], sua implementação padrão provavelmente inclui um [!DNL Transformation Dataset Include] arquivo no qual os nomes e os valores recomendados desses parâmetros são especificados.

1. Abra o [!DNL Profile Manager] seu perfil de conjunto de dados e vá para [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Se você personalizou sua implementação do, [!DNL Site]o arquivo no qual esses parâmetros são definidos pode diferir do local descrito.

1. Edite os valores dos parâmetros conforme desejado. Especifique as unidades desejadas (minutos, horas e assim por diante).

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Salve o [!DNL Session Parameters.cfg] arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o arquivo de inclusão do conjunto de dados pertence.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

**[!DNL Internal Domains]**

[!DNL Internal Domains] é um parâmetro de vetor que lista hosts de nível de domínio (referenciadores internos) que devem ser tratados como parte de um site específico. Esses hosts são removidos da dimensão do referenciador (que é uma lista das informações externas do referenciador). Quando cs(referrer-domain) corresponde a qualquer uma das strings listadas no conjunto de domínios internos, o Tempo limite da sessão é ignorado e a Duração máxima da sessão é usada para determinar a duração da sessão.

O parâmetro Domínios internos também pode ser usado para impedir o início de uma nova sessão quando os visitantes se movem entre os vários domínios de uma empresa associados de uma forma que excede o tempo limite da sessão. Por exemplo, considere uma empresa que tem partes de seu site divididas em dois domínios: um está registrado ( [!DNL xyz.com]) e o outro não está registrado ( [!DNL xyz-unlogged.com]). Se esses sites forem integrados de forma a facilitar a movimentação contínua do tráfego entre os dois domínios, não é desejável gerar uma sessão diferente sempre que o visitante voltar do [!DNL xyz-unlogged.com] domínio para o [!DNL xyz.com] domínio. A listagem [!DNL xyz-unlogged.com] como um domínio interno impede que as sessões sejam divididas em várias sessões como resultado do tráfego nesses dois domínios, desde que a configuração Duração máxima da sessão não seja atingida.

**Para adicionar um domínio interno**

Se você estiver trabalhando com [!DNL Site], sua implementação padrão incluirá um [!DNL Transformation Dataset Include] arquivo para definir o parâmetro Domínios internos. Neste arquivo, o parâmetro é nomeado; basta inserir os domínios internos que deseja incluir e salvar o arquivo atualizado.

1. Abra o [!DNL Profile Manager] seu perfil de conjunto de dados e vá para [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Se você personalizou sua implementação do, [!DNL Site]o arquivo no qual o parâmetro Domínios internos é definido pode diferir do local descrito.

1. Clique com o botão direito **[!UICONTROL Value]** do mouse no parâmetro de vetor Domínios internos e clique em **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Edite os valores conforme desejado.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Salve o [!DNL Internal Domains.cfg] arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

