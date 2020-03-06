---
description: Etapas para mapear o Portal de relatórios para um diretório virtual (IIS 7.0 ou superior).
solution: Analytics
title: Mapeamento do portal de relatórios para um diretório virtual (IIS 7.0 ou superior)
topic: Data workbench
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mapeamento do portal de relatórios para um diretório virtual (IIS 7.0 ou superior){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Etapas para mapear o Portal de relatórios para um diretório virtual (IIS 7.0 ou superior).

Atualmente, a maioria dos clientes de Serviço Gerenciado tem servidores com o sistema operacional Windows Server 2008 e o servidor Web IIS 7.0 ou superior.

## Pré-requisitos {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Certifique-se de que o ASP e [!DNL ASP.Net] os componentes estejam instalados para o IIS 7.0 ou superior.
* Verifique se o usuário da Web do IIS tem [!DNL Modify] acesso ao [!DNL E:\Portal\data\users.mdb] arquivo. Você pode alterar isso clicando com o botão direito do mouse no **[!UICONTROL users.mdb]** arquivo e, em [!DNL Properties], vá para a [!DNL Security] guia. Se você não vir o Usuário da Web do IIS listado ou se não tiver a capacidade de adicionar o Usuário da Web do IIS à lista, basta dar o [!DNL Users] [!DNL Modify] acesso ao grupo.

* Certifique-se de que qualquer conta de usuário que esteja sendo usada para executar a conta também [!DNL Application Pools] tenha [!DNL Modify] acesso às pastas [!DNL E:\Portal\data\users.mdb] e [!DNL C:\Windows\Temp\].

## Etapas de instalação {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Na máquina em que [!DNL Report Portal] está instalado, inicie o [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Selecionar **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Clique com o botão direito do mouse **[!UICONTROL Default Web Site]** e selecione **[!UICONTROL Add Virtual Directory]**.

1. Para um alias, insira o Portal.
1. Para o caminho físico, digite [!DNL E:\Portal\PortalASP].
1. Clique em **[!UICONTROL OK]**.

   O diretório virtual que você criou será exibido abaixo de [!DNL Default Web Site].

1. Adicione os seguintes diretórios virtuais no diretório virtual que você acabou de criar.

   | Criar este alias... | Para este recurso físico |
   |---|---|
   | Núcleo | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Imagens | [!DNL E:\Portal\PortalFiles\Images] |
   | Saída | Localização física do diretório no qual [!DNL Report Server] salva a saída dos conjuntos de relatórios. A pasta de saída pode ser localizada em qualquer lugar e ser nomeada como qualquer coisa. Ele contém uma subpasta para cada conjunto de relatórios. Você pode excluir o arquivo [!DNL E:\Portal\PortalFiles\Output], mas mover o arquivo [!DNL profiles.xml] para o local físico do arquivo de Saída. |

1. Quando terminar, verifique se o IIS exibe quatro novos diretórios virtuais. Certifique-se de que a estrutura de diretório tenha uma pasta pai (com o mesmo nome do portal) e quatro subpastas.
1. Clique em **[!UICONTROL Application Pools]**, em seguida **[!UICONTROL DefaultAppPool]** (supondo que seja aquele que você configurou com seu portal).

1. Clique em **[!UICONTROL Advanced Settings]** e selecione Verdadeiro para ativar aplicativos de 32 bits.
1. Para fazer com que [!DNL Portal] o trabalho funcione, é necessário convertê-lo em um aplicativo. Depois de configurar os diretórios virtuais, clique com o botão direito do mouse no diretório virtual do Portal e selecione **[!UICONTROL Convert to Application]**.

## Dicas e truques adicionais {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Você pode baixar o [!DNL Portal] do Softdocs em **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Você pode simplesmente baixar o [!DNL ReportPortal-Release-1-0-0-7.zip].

* Você não precisa mais do [!DNL ReportPortalSetup.xml], portanto, ele pode ser excluído.
* Para fins de padronização, coloque o conteúdo desse arquivo zip em [!DNL E:\Portal].
* Para determinar o servidor SMTP Para clientes de serviços gerenciados, você pode consultar aqui.
* Insira uma solicitação com NetOps para alterar a entrada do nome do domínio no IIS para o servidor de relatório para algo mais amigável - por exemplo, [!DNL reports.clientname.insight.omniture.com], para que o URL geral do portal seja [!DNL http://reports.clientname.insight.omniture.com/Portal]. Configure seu [!DNL email.asa] arquivo assim que esta alteração for implementada.

