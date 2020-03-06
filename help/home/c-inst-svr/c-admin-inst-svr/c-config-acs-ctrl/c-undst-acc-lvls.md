---
description: Os níveis de acesso descrevem quais URIs no computador um grupo de usuários tem permissão para ler ou modificar.
solution: Insight
title: Noções básicas sobre os níveis de acesso
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Noções básicas sobre os níveis de acesso{#understanding-access-levels}

Os níveis de acesso descrevem quais URIs no computador um grupo de usuários tem permissão para ler ou modificar.

Siga estas diretrizes para definir os níveis de acesso desejados para os usuários de sua organização:

* URIs específicos sem caractere de barra à direita restringem o acesso somente a esse URI. Por exemplo, [!DNL /Components/Communications.cfg] fornece acesso somente ao [!DNL Communications.cfg]arquivo.

* Uma barra (/), especificando um diretório, fornece aos membros do grupo acesso a qualquer URI que comece com essa string. Por exemplo, /Profiles/ fornece acesso ao diretório inteiro de Perfis.
* Um símbolo de cifrão ($) à direita restringe o acesso somente ao URI exato, mesmo que ele seja um diretório. Por exemplo, /Profiles/$ fornece acesso para ler o diretório principal de Perfis, mas não para ler arquivos dentro desse diretório.

   Para acessar arquivos específicos, não é necessário usar um $ à direita.

   Por exemplo, [!DNL /Components/Communications.cfg] e [!DNL /Components/Communications.cfg$] forneça o mesmo acesso.

* Um símbolo de porcentagem (%) pode ser usado com CN (Nome comum) para permitir o acesso. Por exemplo, /Users/%CN%/ permite o acesso ao diretório Usuário que corresponde ao nome comum do certificado SSL do [!DNL Insight] usuário. Observe que essa sintaxe pode ser usada apenas uma vez em um URI.

Os URIs nos grupos de controle de acesso predefinidos foram configurados da seguinte forma:

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome do grupo </th> 
   <th colname="col2" class="entry"> Acesso somente leitura </th> 
   <th colname="col3" class="entry"> Acesso de leitura e gravação </th> 
   <th colname="col4" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administradores </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>Acesso de leitura e gravação a todos os diretórios do <span class="keyword"> Insight Server</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensores </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Acesso de leitura e gravação aos dois arquivos que os <span class="wintitle"> Sensores</span> usam para se comunicar com o <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuários </p> </td> 
   <td colname="col2"> <p>/Profiles/ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Usuários/$ </p> </td> 
   <td colname="col3"> /Usuários/%CN%/ </td> 
   <td colname="col4"> <p>Acesso de leitura e gravação ao diretório Usuário que corresponde ao certificado SSL nome comum do usuário do <span class="keyword"> Insight</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuários avançados </p> </td> 
   <td colname="col2"> <p>/Profiles/$ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Usuários/$ </p> </td> 
   <td colname="col3"> <p>/Profiles/ </p> <p>/Usuários/%CN%/ </p> </td> 
   <td colname="col4"> <p>Os usuários avançados podem ter o mesmo acesso que os usuários, com a capacidade adicional de gravar no diretório Perfis. Esses usuários podem editar perfis e permitir que as alterações sejam atualizadas automaticamente para outros usuários do <span class="keyword"> Insight</span> , como ao distribuir espaços de trabalho recém-definidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de cluster </p> </td> 
   <td colname="col2"> <p>/Components for Processing Servers/ </p> <p>/Addresses/ </p> <p>/Profiles/ </p> <p>/Pesquisas/ </p> <p>/Access Control/ </p> <p>/Bin/ </p> <p>/Logs/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Acesso de leitura e gravação ao diretório Cluster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de relatório </p> </td> 
   <td colname="col2"> <p>/Profiles/$ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Usuários/$ </p> </td> 
   <td colname="col3"> <p>/Profiles/ </p> <p>/Usuários/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Os computadores de relatórios têm o mesmo acesso que os Usuários avançados, com a capacidade adicional de gravar no arquivo <span class="filepath"> ReportStatus.vsp</span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

**Para configurar o controle de acesso**

Ao definir grupos de controle de acesso, é necessário incluir todos os administradores de sistema, usuários, servidores de cluster e usuários do Servidor de relatórios que exigem acesso a este [!DNL Insight Server] computador. Você pode conceder acesso usando o endereço IP ou as informações do certificado SSL, como o nome comum ou a organização.

>[!NOTE]
>
>Quando o [!DNL Access Control.cfg] arquivo é alterado em [!DNL Insight Server], todas as conexões existentes são encerradas e forçadas a se reconectar. As conexões são verificadas em relação às permissões no arquivo atualizado. [!DNL Access Control.cfg] Na interface do Gerenciador de servidores, o [!DNL Insight Server] ícone fica vermelho temporariamente e verde novamente, pois a conexão é encerrada e forçada a se reconectar com todas as outras.

1. Na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.

1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Files]**.

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Access Control]** para exibir o conteúdo. O [!DNL Access Control.cfg] arquivo está localizado dentro deste diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna de nome *do* servidor para [!DNL Access Control.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção é exibida na [!DNL Temp] coluna para [!DNL Access Control.cfg].

1. Clique com o botão direito do mouse na marca de seleção recém-criada na [!DNL Temp] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Na [!DNL Access Control.cfg] janela, clique **[!UICONTROL Access Control Groups]** para exibir seu conteúdo.

   ![](assets/access_ctrl_cfg.png)

1. Para adicionar um novo grupo de controle de acesso:

   1. Clique com o botão direito do mouse **[!UICONTROL Access Control Groups]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Clique com o botão direito do mouse **[!UICONTROL Members]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Os membros dos grupos padrão não são predefinidos. Por padrão, o acesso do Administrador é concedido ao 127.0.0.1 (host local) e o acesso [!DNL Sensor] é concedido ao IP:*. Todos os outros membros do grupo de controle de acesso devem ser definidos.

   1. Complete os parâmetros.

1. Para adicionar novos membros a um grupo de controle de acesso existente:

   1. Clique com o botão direito do mouse **[!UICONTROL Members]** no grupo de controle de acesso apropriado e clique em **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e, em seguida, clicando em **[!UICONTROL Save]**.

1. Para salvar as alterações feitas localmente no [!DNL Insight Server] computador, no [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção para [!DNL Access Control.cfg] na [!DNL Temp] coluna e clique em **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

