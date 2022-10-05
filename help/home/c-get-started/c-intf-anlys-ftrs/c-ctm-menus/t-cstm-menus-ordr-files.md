---
description: Você pode personalizar a aparência de qualquer menu editando o arquivo order.txt associado a esse menu.
title: Personalizar um menu usando arquivos order.txt
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
exl-id: 3803a56f-19b7-4792-a277-97f76c11ec0e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 2%

---

# Personalizar um menu usando arquivos order.txt{#customize-a-menu-using-order-txt-files}

{{eol}}

Você pode personalizar a aparência de qualquer menu editando o arquivo order.txt associado a esse menu.

As etapas nesta seção se aplicam a todos os tipos de menus.

**Para editar o arquivo order.txt para personalizar um menu**

1. No [!DNL Profile Manager]no *nome do perfil* , clique com o botão direito do mouse na marca de seleção do [!DNL order.txt] e clique em **[!UICONTROL Make Local]**.
1. Clique com o botão direito do mouse na marca de seleção para a [!DNL order.txt] no [!DNL User] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. O [!DNL order.txt] é exibido.

   ![Informações da etapa](assets/cfg_ordertxt.png)

1. (Opcional) Adicione ou altere a variável [Inclusivo] ou [Exclusivo] na parte superior do arquivo, se desejado. Essa configuração controla se os itens não listados na variável [!DNL order.txt] mas presente no [!DNL Profile Manager] é listada no menu . As opções incluem:

   * **[Inclusivo]:** Esta é a configuração padrão. Esta configuração resulta em itens de menu não especificados na variável [!DNL order.txt]listado na parte inferior do menu em ordem alfabética. Por exemplo, se a variável [!DNL Profile Manager] contém um item de Perfil além dos listados na [!DNL order.txt] acima, Perfil seria exibido abaixo de Dados.

   * **[Exclusivo]:** Esta configuração resulta em itens de menu não especificados na variável [!DNL order.txt] que está sendo excluído do menu. Por exemplo, se a variável [!DNL Profile Manager] contém um item de Perfil além dos listados na [!DNL order.txt] acima, o Perfil não seria exibido em nenhum lugar do menu.

   * **em branco:** Se nem [Inclusivo] ou [Exclusivo] for exibida na parte superior do arquivo, a Data Workbench exibirá os itens do menu como se a configuração estivesse [Inclusivo].

1. Conclua uma ou mais das seguintes etapas:

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Para executar esta tarefa... </th> 
    <th colname="col2" class="entry"> Faça o seguinte... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Reordenar itens do menu </p> </td> 
    <td colname="col2"> <p>Digite os nomes dos itens na ordem em que deseja que apareçam no Data Workbench. </p> <p>Por exemplo, desde que cada nome de item de menu corresponda ao nome de arquivo ou pasta correspondente, o seguinte resultará em<b> Adicionar tabela</b> aparecer primeiro, em seguida <b>Adicionar visualização</b>, <b>Adicionar legenda</b>e <b>Adicionar observação</b> aparecendo por último. </p> <p><b>Adicionar tabela </b> </p> <p><b>Adicionar visualização </b> </p> <p><b>Adicionar legenda </b> </p> <p><b>Adicionar observação </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Renomear um item de menu </p> </td> 
    <td colname="col2"> <p>Renomeie o arquivo ou a pasta correspondente no <span class="wintitle"> Gerenciador de perfis</span>, em seguida, altere o nome do item no <span class="filepath"> order.txt</span> arquivo. </p> <p>Por exemplo, para renomear Adicionar anotação a nova anotação, renomeie a pasta Adicionar anotação no <span class="wintitle"> Gerenciador de perfis</span> para Nova anotação, em seguida, altere o nome do item Adicionar anotação no <span class="filepath"> order.txt</span> para Nova anotação. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ocultar um item de menu </p> </td> 
    <td colname="col2"> <p>Para ocultar o item de menu, mas não excluir o próprio item, digite um sinal de menos (-) no início de seu nome. </p> <p>Por exemplo, os resultados a seguir em <span class="wintitle"> Adicionar anotação</span> não aparecer no menu. </p> <p>Adicionar legenda </p> <p>-Adicionar anotação </p> <p>Para mostrar novamente o item de menu oculto, basta remover o sinal de menos (-) ou usar o parâmetro Revelar tudo na <span class="filepath"> Insight.cfg</span> arquivo, consulte <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Parâmetros de configuração do Insight</a>. </p> <p>Você também pode ocultar itens de menu usando os seguintes métodos: 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>O parâmetro Mostrar em um <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span>ou <span class="filepath"> .dim</span> O arquivo oculta filtros, métricas e dimensões derivadas e dimensões estendidas de seus respectivos menus. Ao usar essa opção, o item não está listado no menu, mas ainda está no perfil e disponível para uso. </p> <p>Para usar esse parâmetro para ocultar filtros e métricas e dimensões derivadas, adicione a seguinte linha ao final da <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>ou <span class="filepath"> .filter</span> arquivo: </p> <p><span class="filepath"> show = bool: false</span> </p> <p>Para usar esse parâmetro para ocultar dimensões estendidas, consulte o Capítulo 10 da variável <i>Guia de configuração do conjunto de dados</i> para obter instruções. </p> <p>Você pode mostrar temporariamente os itens ocultos usando este método, definindo o parâmetro Mostrar tudo na <span class="filepath"> Insight.cfg</span> arquivo. Para obter mais informações sobre esse parâmetro, consulte <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Parâmetros de configuração do Insight</a>. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">O parâmetro Oculto na <span class="filepath"> Transformation.cfg</span> arquivo ou qualquer conjunto de dados incluir arquivo oculta dimensões estendidas do menu de dimensão. Ao usar essa opção, o item não está listado no menu, mas ainda está no perfil e disponível para uso. <p> <p>Observação: Ao ocultar dimensões estendidas usando esse método, você deve retransformar seu conjunto de dados para que as dimensões fiquem ocultas. </p> </p> <p>Você pode mostrar temporariamente os itens ocultos usando este método, definindo o parâmetro Mostrar tudo na <span class="filepath"> Insight.cfg</span> arquivo. Para obter mais informações sobre esse parâmetro, consulte <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Parâmetros de configuração do Insight</a>. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Arquivos com bytes zero ocultam qualquer tipo de item em qualquer menu. Ao usar essa opção, um arquivo vazio (byte zero) oculta a presença de um arquivo com o mesmo nome que contém dados. O Data Workbench trata arquivos de byte zero como se não existissem. Para obter mais informações, consulte <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ocultar arquivos usando arquivos vazios (zero bytes)</a>. </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Excluir um item de menu </p> </td> 
    <td colname="col2"> <p>Se este ficheiro estiver definido para utilizar a opção [Exclusivo], pode simplesmente eliminar o item de menu deste ficheiro. O item em si ainda está no perfil, mas não está listado no menu. </p> <p>Se este ficheiro estiver definido para utilizar a opção [Inclusivo], tem de remover o nome do item de menu deste ficheiro e eliminar ou eliminar bytes zero do ficheiro correspondente para remover o item do menu. </p> <p>Para obter informações sobre como excluir arquivos, consulte <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> Excluir arquivos do seu perfil de trabalho</a>. Para obter informações sobre arquivos de byte zero, consulte <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Ocultar arquivos usando arquivos vazios (zero bytes)</a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Adicionar um cabeçalho de grupo </p> </td> 
    <td colname="col2"> <p>Digite três hifens antes e depois do texto do cabeçalho que você deseja que apareça. </p> <p>Por exemplo, o seguinte resultaria em um cabeçalho Gerenciar grupo para um conjunto de itens de menu relacionados. </p> <p>---Gerenciar--- </p> <p>Perfil </p> <p>Conjunto de dados </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Adicionar uma linha a seções separadas de um menu </p> </td> 
    <td colname="col2"> <p>Digite três hifens onde deseja que uma linha apareça. </p> <p>Por exemplo, o seguinte resulta em uma linha que separa Adicionar anotação e Adicionar Personalizado. </p> <p>Adicionar anotação </p> <p>— </p> <p>Adicionar Personalizado </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Salve e feche o arquivo.
1. (Opcional) Para disponibilizar as alterações para todos os usuários do perfil de trabalho, clique com o botão direito do mouse na marca de seleção branca para a função [!DNL order.txt] no [!DNL User] e clique em **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
