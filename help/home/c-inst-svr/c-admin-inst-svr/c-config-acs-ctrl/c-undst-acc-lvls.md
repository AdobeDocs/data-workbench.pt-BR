---
description: Os níveis de acesso descrevem quais URIs na máquina um grupo de usuários tem permissão para ler ou modificar.
title: Compreender níveis de acesso
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# Compreender níveis de acesso{#understanding-access-levels}

Os níveis de acesso descrevem quais URIs na máquina um grupo de usuários tem permissão para ler ou modificar.

Siga estas orientações para definir os níveis de acesso conforme desejado para os usuários de sua organização:

* URIs específicos sem caractere de barra à direita restringem o acesso somente a esse URI. Por exemplo, [!DNL /Components/Communications.cfg] fornece acesso somente ao arquivo [!DNL Communications.cfg].

* Uma barra à direita (/), especificando um diretório, fornece aos membros do grupo acesso a qualquer URI que comece com essa string. Por exemplo, /Profiles/ fornece acesso a todo o diretório Perfis .
* Um símbolo de cifrão à direita ($) restringe o acesso somente ao URI exato, mesmo que seja um diretório. Por exemplo, /Profiles/$ fornece acesso para ler o diretório principal de Perfis, mas não para ler arquivos dentro desse diretório.

   Para acessar arquivos específicos, não é necessário usar um $ à direita.

   Por exemplo, [!DNL /Components/Communications.cfg] e [!DNL /Components/Communications.cfg$] fornecem o mesmo acesso.

* Um símbolo de porcentagem (%) pode ser usado com CN (Nome comum) para permitir acesso. Por exemplo, /Users/%CN%/ permite acesso ao diretório do usuário correspondente ao certificado SSL nome comum do usuário [!DNL Insight]. Observe que essa sintaxe pode ser usada somente uma vez em um URI.

Os URIs nos grupos de controle de acesso predefinidos foram configurados da seguinte maneira:

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome do grupo </th> 
   <th colname="col2" class="entry"> Acesso Somente Leitura </th> 
   <th colname="col3" class="entry"> Acesso de leitura e gravação </th> 
   <th colname="col4" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administradores </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>Acesso de leitura e gravação para todos os diretórios <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensores </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Acesso de leitura e gravação aos dois arquivos que o <span class="wintitle"> Sensores</span> usa para se comunicar com o <span class="keyword"> Servidor Insight</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuários </p> </td> 
   <td colname="col2"> <p>/Perfis/ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Endereços/ </p> <p>/Usuários/$ </p> </td> 
   <td colname="col3"> /Usuários/%CN%/ </td> 
   <td colname="col4"> <p>Acesso de leitura e gravação ao diretório Usuário correspondente ao certificado SSL nome comum do usuário <span class="keyword"> Insight</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usuários avançados </p> </td> 
   <td colname="col2"> <p>/Perfis/$ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Endereços/ </p> <p>/Usuários/$ </p> </td> 
   <td colname="col3"> <p>/Perfis/ </p> <p>/Usuários/%CN%/ </p> </td> 
   <td colname="col4"> <p>Os usuários avançados têm o mesmo acesso que os usuários, com a capacidade adicional de gravar no diretório Perfis . Esses usuários podem editar perfis e permitir que as alterações sejam atualizadas automaticamente para outros usuários do <span class="keyword"> Insight</span>, como ao distribuir espaços de trabalho recém-definidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de Cluster </p> </td> 
   <td colname="col2"> <p>/Componentes para servidores de processamento/ </p> <p>/Endereços/ </p> <p>/Perfis/ </p> <p>/Pesquisas/ </p> <p>/Controle de acesso/ </p> <p>/Bin/ </p> <p>/Logs/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Acesso de leitura e gravação no diretório Cluster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de relatórios </p> </td> 
   <td colname="col2"> <p>/Perfis/$ </p> <p>/Status/ </p> <p>/Software/ </p> <p>/Endereços/ </p> <p>/Usuários/$ </p> </td> 
   <td colname="col3"> <p>/Perfis/ </p> <p>/Usuários/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Os computadores de relatório têm o mesmo acesso que os Usuários avançados, com a capacidade adicional de gravar no arquivo <span class="filepath"> ReportStatus.vsp</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Para configurar o Controle de Acesso**

Ao definir grupos de controle de acesso, você precisa incluir todos os administradores de sistema, usuários, servidores de cluster e usuários do Servidor de relatórios que exigem acesso a este [!DNL Insight Server] computador. Você pode conceder acesso usando o endereço IP ou as informações do certificado SSL, como o nome ou a organização comum.

>[!NOTE]
>
>Quando o arquivo [!DNL Access Control.cfg] é alterado em [!DNL Insight Server], todas as conexões existentes são encerradas e forçadas a se reconectar. As conexões são verificadas em relação às permissões no arquivo [!DNL Access Control.cfg] atualizado. Na interface do Gerenciador de Servidores, o ícone [!DNL Insight Server] fica vermelho temporariamente e verde novamente, pois a conexão é encerrada e forçada a se reconectar junto com todas as outras.

1. Na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho Gerenciador de Servidores .

1. Clique com o botão direito do mouse no ícone do [!DNL Insight Server] que deseja configurar e clique em **[!UICONTROL Files]**.

1. No [!DNL Server Files Manager], clique em **[!UICONTROL Access Control]** para visualizar seu conteúdo. O arquivo [!DNL Access Control.cfg] está localizado dentro desse diretório.

1. Clique com o botão direito do mouse na marca de seleção na coluna *server name* para [!DNL Access Control.cfg] e clique em **[!UICONTROL Make Local]**. Uma marca de seleção aparece na coluna [!DNL Temp] para [!DNL Access Control.cfg].

1. Clique com o botão direito do mouse na marca de seleção recém-criada na coluna [!DNL Temp] e clique em **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Na janela [!DNL Access Control.cfg], clique em **[!UICONTROL Access Control Groups]** para visualizar seu conteúdo.

   ![](assets/access_ctrl_cfg.png)

1. Para adicionar um novo grupo de controle de acesso:

   1. Clique com o botão direito do mouse em **[!UICONTROL Access Control Groups]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Clique com o botão direito do mouse em **[!UICONTROL Members]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Os membros dos grupos padrão não são predefinidos. Por padrão, o acesso de Administrador é concedido para 127.0.0.1 (host local) e [!DNL Sensor] é concedido para IP:*. Todos os outros membros do grupo de controle de acesso devem ser definidos.

   1. Complete os parâmetros.

1. Para adicionar novos membros a um grupo de controle de acesso existente:

   1. Clique com o botão direito do mouse em **[!UICONTROL Members]** no grupo de controle de acesso apropriado e clique em **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Salve o arquivo clicando com o botão direito do mouse em **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para salvar as alterações feitas localmente na máquina [!DNL Insight Server], no [!DNL Server Files Manager], clique com o botão direito do mouse na marca de seleção [!DNL Access Control.cfg] na coluna [!DNL Temp] e depois clique em **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]***.
