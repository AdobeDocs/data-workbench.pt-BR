---
description: Etapas para mapear o portal de relatórios para um diretório virtual (IIS 7.0 ou superior).
title: Mapear o portal de relatórios para um diretório virtual (IIS 7.0 ou superior)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 5%

---

# Mapear o portal de relatórios para um diretório virtual (IIS 7.0 ou superior){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

{{eol}}

Etapas para mapear o portal de relatórios para um diretório virtual (IIS 7.0 ou superior).

Atualmente, a maioria dos clientes de Serviço Gerenciado tem servidores com o sistema operacional Windows Server 2008 e o servidor Web IIS 7.0 ou superior.

## Pré-requisitos {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Certifique-se de que o ASP e o [!DNL ASP.Net] Os componentes são instalados para o IIS 7.0 ou superior.
* Certifique-se de que o usuário da Web do IIS tenha [!DNL Modify] acesso ao [!DNL E:\Portal\data\users.mdb] arquivo. Você pode alterar isso clicando com o botão direito do mouse no botão **[!UICONTROL users.mdb]** arquivo e em [!DNL Properties], acesse o [!DNL Security] guia . Se você não vir o Usuário da Web do IIS listado ou não tiver a capacidade de adicionar o Usuário da Web do IIS à lista, basta dar o [!DNL Users] agrupe [!DNL Modify] acesso.

* Verifique se qualquer conta de usuário está sendo usada para executar o [!DNL Application Pools] também tem [!DNL Modify] acesso ao [!DNL E:\Portal\data\users.mdb] e as pastas [!DNL C:\Windows\Temp\].

## Etapas de instalação {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Na máquina em que [!DNL Report Portal] estiver instalado, inicie o [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Selecionar **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Clique com o botão direito do mouse **[!UICONTROL Default Web Site]** e selecione **[!UICONTROL Add Virtual Directory]**.

1. Para um alias, insira o Portal.
1. Para o caminho físico, insira [!DNL E:\Portal\PortalASP].
1. Clique em **[!UICONTROL OK]**.

   O diretório virtual que você criou será exibido sob a variável [!DNL Default Web Site].

1. Adicione os seguintes diretórios virtuais no diretório virtual que você acabou de criar.

   | Criar este alias... | Para este recurso físico |
   |---|---|
   | Núcleo | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Imagens | [!DNL E:\Portal\PortalFiles\Images] |
   | Saída | Localização física do diretório em que [!DNL Report Server] salva a saída dos conjuntos de relatórios. A pasta de saída pode ser localizada em qualquer lugar e pode ser nomeada como qualquer coisa. Ele contém uma subpasta para cada conjunto de relatórios. É possível excluir o [!DNL E:\Portal\PortalFiles\Output], mas mova o [!DNL profiles.xml] para o local físico do arquivo de saída. |

1. Quando terminar, verifique se o IIS exibe quatro novos diretórios virtuais. Certifique-se de que a estrutura de diretório tenha uma pasta principal (com o mesmo nome do portal) e quatro subpastas.
1. Clique em **[!UICONTROL Application Pools]**, em seguida **[!UICONTROL DefaultAppPool]** (supondo que seja esse o portal que você configurou).

1. Clique em **[!UICONTROL Advanced Settings]** e selecione Verdadeiro para os Aplicativos de 32 bits ativados.
1. Para obter o [!DNL Portal] para funcionar, é necessário convertê-lo em um aplicativo. Depois de configurar os diretórios virtuais, clique com o botão direito do mouse no diretório virtual do Portal e selecione **[!UICONTROL Convert to Application]**.

## Dicas e truques adicionais {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Você pode baixar o [!DNL Portal] do Softdocs em **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Basta baixar o [!DNL ReportPortal-Release-1-0-0-7.zip].

* Você não precisa mais do [!DNL ReportPortalSetup.xml], para que possa ser excluído.
* Por uma questão de padronização, coloque o conteúdo desse arquivo zip em [!DNL E:\Portal].
* Para determinar o servidor SMTP para clientes de serviços gerenciados, você pode consultar aqui.
* Coloque uma solicitação com NetOps para alterar a entrada de nome de domínio no IIS para o servidor de relatório para algo mais amigável - por exemplo, [!DNL reports.clientname.insight.omniture.com], para que o URL geral do portal seja [!DNL https://reports.clientname.insight.omniture.com/Portal]. Configure seu [!DNL email.asa] após a implementação dessa alteração.
