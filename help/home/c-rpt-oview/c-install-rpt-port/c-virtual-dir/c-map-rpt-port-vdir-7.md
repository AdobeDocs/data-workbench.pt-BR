---
description: Etapas para mapear o portal de relatórios para um diretório virtual (IIS 7.0 ou superior).
title: Mapear o portal de relatórios para um diretório virtual (IIS 7.0 ou superior)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---

# Mapear o portal de relatórios para um diretório virtual (IIS 7.0 ou superior){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Etapas para mapear o portal de relatórios para um diretório virtual (IIS 7.0 ou superior).

Atualmente, a maioria dos clientes de Serviço Gerenciado tem servidores com o sistema operacional Windows Server 2008 e o servidor Web IIS 7.0 ou superior.

## Pré-requisitos {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Verifique se os componentes ASP e [!DNL ASP.Net] estão instalados para o IIS 7.0 ou superior.
* Verifique se o usuário da Web do IIS tem [!DNL Modify] acesso ao arquivo [!DNL E:\Portal\data\users.mdb]. Você pode alterar isso clicando com o botão direito do mouse no arquivo **[!UICONTROL users.mdb]** e em [!DNL Properties], vá para a guia [!DNL Security]. Se você não vir o Usuário da Web do IIS listado ou não tiver a capacidade de adicionar o Usuário da Web do IIS à lista, basta dar ao grupo [!DNL Users] o acesso [!DNL Modify].

* Certifique-se de que qualquer conta de usuário que esteja sendo usada para executar o [!DNL Application Pools] também tenha [!DNL Modify] acesso às pastas [!DNL E:\Portal\data\users.mdb] e  [!DNL C:\Windows\Temp\] .

## Etapas de instalação {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Na máquina em que [!DNL Report Portal] está instalado, inicie o [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Selecionar **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Clique com o botão direito do mouse em **[!UICONTROL Default Web Site]** e selecione **[!UICONTROL Add Virtual Directory]**.

1. Para um alias, insira o Portal.
1. Para o caminho físico, insira [!DNL E:\Portal\PortalASP].
1. Clique em **[!UICONTROL OK]**.

   O diretório virtual que você criou aparece em [!DNL Default Web Site].

1. Adicione os seguintes diretórios virtuais no diretório virtual que você acabou de criar.

   | Criar este alias... | Para este recurso físico |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Imagens | [!DNL E:\Portal\PortalFiles\Images] |
   | Saída | Localização física do diretório em que [!DNL Report Server] salva a saída dos conjuntos de relatórios. A pasta de saída pode ser localizada em qualquer lugar e pode ser nomeada como qualquer coisa. Ele contém uma subpasta para cada conjunto de relatórios. Você pode excluir o [!DNL E:\Portal\PortalFiles\Output], mas mover o [!DNL profiles.xml] para o local físico do arquivo de saída. |

1. Quando terminar, verifique se o IIS exibe quatro novos diretórios virtuais. Certifique-se de que a estrutura de diretório tenha uma pasta principal (com o mesmo nome do portal) e quatro subpastas.
1. Clique em **[!UICONTROL Application Pools]**, em seguida em **[!UICONTROL DefaultAppPool]** (supondo que seja esse o portal que você configurou com seu portal).

1. Clique em **[!UICONTROL Advanced Settings]** e selecione Verdadeiro para os Aplicativos de 32 bits ativados.
1. Para que o [!DNL Portal] funcione, é necessário convertê-lo em um aplicativo. Depois de configurar os diretórios virtuais, clique com o botão direito do mouse no diretório virtual do Portal e selecione **[!UICONTROL Convert to Application]**.

## Dicas e truques adicionais {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Você pode baixar o [!DNL Portal] do Softdocs em **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Basta baixar o [!DNL ReportPortal-Release-1-0-0-7.zip].

* Você não precisa mais do [!DNL ReportPortalSetup.xml], então ele pode ser excluído.
* Por uma questão de padronização, coloque o conteúdo desse arquivo zip em [!DNL E:\Portal].
* Para determinar o servidor SMTP para clientes de serviços gerenciados, você pode consultar aqui.
* Coloque uma solicitação com NetOps para alterar a entrada de nome de domínio no IIS para o servidor de relatório para algo mais amigável - por exemplo, [!DNL reports.clientname.insight.omniture.com], para que o URL geral do portal seja [!DNL https://reports.clientname.insight.omniture.com/Portal]. Configure seu arquivo [!DNL email.asa] assim que essa alteração for implementada.
