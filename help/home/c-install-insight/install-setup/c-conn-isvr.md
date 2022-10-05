---
description: Depois de instalar o software Insight e o certificado digital, você deve iniciar o Insight e configurar a conexão com o servidor Insight.
title: Configuração da conexão com o servidor Insight
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
exl-id: 6a87e972-069a-435c-9bac-23b20f165ebb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 1%

---

# Configuração da conexão com o servidor Insight{#configuring-the-connection-to-insight-server}

{{eol}}

Depois de instalar o software Insight e o certificado digital, você deve iniciar o Insight e configurar a conexão com o servidor Insight.

>[!NOTE]
>
>Em alguns casos, a conexão com o servidor Insight pode ter sido pré-configurada pelos Serviços de consultoria do Adobe ou pelo administrador do sistema. Nesse caso, não é necessário concluir essa tarefa.

Ao iniciar o Insight pela primeira vez, ele se conecta automaticamente ao Adobe License Server para registrar seu certificado digital. Para concluir o processo de registro com êxito, o computador tem de estar ligado à Internet quando executar as seguintes etapas.

>[!NOTE]
>
>Se você já solicitou, baixou e instalou um certificado pré-bloqueado, conforme descrito em [Download e instalação do certificado digital](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9), o Insight não tentará se conectar ao License Server e você não receberá um erro.

**Para configurar a conexão com o servidor Insight**

Ao trabalhar em um ambiente em cluster, o Insight deve ser configurado para acessar o principal servidor Insight para evitar problemas de sincronização. No Insight você pode visualizar informações sobre o processamento [!DNL Insight Servers] no seu cluster usando o [!DNL Related Servers] item de menu na [Gerenciador de servidores](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-svrs-mgr.html).

1. Iniciar Insight.
1. No [!DNL Worktop], clique em **[!UICONTROL Admin]**, em seguida **[!UICONTROL First Steps]**.

1. Clique no botão **[!UICONTROL Configure Connection to Servers]** miniatura.

   O [!DNL Servers Manager], o [!DNL Insight.cfg] e instruções para configurar seu [!DNL Insight.cfg]são exibidos.

1. No [!DNL Insight.cfg] , clique com o botão direito do mouse **[!UICONTROL Servers]** e clique em **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddChild.png)

1. Conclua ou modifique os parâmetros do servidor para fornecer ao Insight acesso ao seu servidor Insight principal. Para obter descrições detalhadas dos parâmetros no arquivo Insight.cfg, consulte [Parâmetros de configuração](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-insght-config-param.html).

   ![](assets/cfg_Workstation_AddServer.png)

1. Repita as Etapa 4 e 5 para cada Servidor Insight ao qual deseja configurar uma conexão.
1. Para salvar as alterações de configuração, clique com o botão direito do mouse **[!UICONTROL Insight.cfg (modified)]** na parte superior da janela e clique em **[!UICONTROL Save as Insight.cfg]**.

   O Insight tenta se conectar ao [!DNL Insight Server(s)] usando as configurações que você especificou. Se uma conexão for estabelecida, um nó verde aparecerá no nó [!DNL Servers Manager] conforme mostrado na página seguinte.

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **Verde:** Indica que a conexão com o servidor Insight está ativa.
   * **Vermelho claro:** Indica um possível problema com o servidor, como uma fuga no processamento do servidor, alto uso de memória ou baixo espaço em disco.
   * **Vermelho:** Indica que a conexão com o servidor Insight não está ativa.

   Se o Insight não puder se conectar usando as configurações especificadas, um nó vermelho aparecerá no [!DNL Servers Manager]. Se isso acontecer, consulte [Solução de problemas de conexão](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b).

<!--
c_dir_crt_setup.xml
-->

Ao selecionar um perfil para usar, as informações do perfil (incluindo dados relacionados e quaisquer espaços de trabalho ou visualizações específicos definidos para o perfil) são baixadas no computador. À medida que você baixa cada perfil, o Insight cria uma pasta dentro do diretório de instalação usando o nome do perfil.

Por exemplo, se você selecionar um perfil chamado Vendas, uma pasta chamada Vendas será exibida no diretório Insight . Esta pasta contém as métricas, dimensões, espaços de trabalho e visualizações definidas no perfil de Vendas. Após o carregamento inicial do perfil, o perfil pode ser usado ao trabalhar offline. Consulte [Trabalhar offline e online](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-off-on.html).

Além disso, ao se conectar ao servidor Insight pela primeira vez a partir do Insight, o servidor Insight cria os seguintes diretórios no diretório de instalação do Insight.

* **[!DNL Trace]diretório:** No [!DNL Trace] diretório é o arquivo de log do Insight ( [!DNL insight.log]). Quando o tamanho da variável [!DNL Insight.log] atinge 100 MB, o arquivo é renomeado para [!DNL insight-1.log]. Se um arquivo com o nome [!DNL insight-1.log] já existe, então [!DNL insight-1.log] é renomeado para [!DNL insight-2.log]e assim por diante, com um máximo de [!DNL insight-9.log]. O arquivo [!DNL insight.log] sempre contém as informações de log mais recentes e [!DNL insight-max.log] contém o mais antigo.

* **[!DNL User]diretório:** No [!DNL User] diretório são pastas que correspondem a cada perfil usado até o momento e, em cada pasta de perfil, são pastas nomeadas [!DNL Work] e [!DNL Workspaces]. O diretório `User\*profile name*\Workspaces` é o local padrão no qual os arquivos do espaço de trabalho Insight são salvos. `User\*profile name*\Work` é o local padrão no qual as visualizações do Insight e outros trabalhos personalizados executados pelo usuário do Insight são salvos.

A tabela a seguir lista os locais padrão dos componentes acessados com frequência.

<table id="table_0254A8C25AF5400F89F87A242746D07E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Local do Diretório </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visualizações salvas </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Usuário\<i>nome do perfil</i>\Trabalho\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvo <span class="wintitle"> Áreas de trabalho</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Usuário\<i>nome do perfil</i>\Espaços de trabalho\<i>nome da guia</i>\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Salvo<span class="filepath"> .png</span> arquivos </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Usuário\<i>nome do perfil</i>\Trabalho\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cache de dados </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Insight.log</span> arquivo </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

Você pode pesquisar por nome de chave, tipo de chave ou valor para localizar rapidamente uma entrada, a fim de remover a necessidade de rolar pelos arquivos grandes e expandidos para obter informações aninhadas. Você pode localizar nomes de dimensões, nomes de servidores e assim por diante. O exemplo a seguir mostra correspondências para uma pesquisa no mapa de frases.

![](assets/cfg_search.PNG)

Digite uma frase de pesquisa nesse campo para localizar os dados. Dependendo do sucesso de uma correspondência, a cor do campo muda. As correspondências são mostradas em destaque e as não correspondências são esmaecidas. Se não houver correspondências, o plano de fundo do campo de pesquisa ficará vermelho. Quando você pressiona Enter, a árvore de configuração expande cada lugar em que há uma correspondência e é reduzida em um local em que não há correspondência.

Também é possível usar expressões regulares na variável [!DNL Search] campo. Por exemplo, você pode usar re: [!DNL *zip.*] para qualquer entrada que contenha a palavra &quot;zip&quot;.

Para limpar uma pesquisa, pressione **[!UICONTROL Escape]**.
