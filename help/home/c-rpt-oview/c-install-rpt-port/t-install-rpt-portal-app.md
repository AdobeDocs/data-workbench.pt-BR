---
description: O portal de relatórios é composto de um conjunto de páginas do servidor de aplicativos (ASPs) e arquivos de suporte.
title: Instalar os arquivos do aplicativo do portal de relatórios
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Instalar os arquivos do aplicativo do portal de relatórios{#install-the-report-portal-application-files}

O portal de relatórios é composto de um conjunto de páginas do servidor de aplicativos (ASPs) e arquivos de suporte.

Para instalar o [!DNL Report Portal], você deve extrair esses arquivos do arquivo de distribuição recebido do Adobe e instalá-los na máquina em que o Microsoft IIS está sendo executado.

**Para instalar os arquivos  [!DNL Report Portal] de aplicativo**

1. Se ainda não tiver feito isso, baixe o pacote de instalação (arquivo .zip) para o [!DNL Report Portal] do site Adobe FTP.
1. Na máquina em que o IIS está sendo executado, extraia os arquivos no pacote de instalação para qualquer local. Esta etapa instala as seguintes subpastas e arquivos na pasta VSVirtualPortalName.

   | Pasta ou arquivo | Descrição |
   |---|---|
   | [!DNL \data\users.mdb] | Banco de dados contendo a lista de usuários autorizados [!DNL Report Portal]. |
   | [!DNL \PortalASP\] | Pasta contendo os arquivos ASP que compõem [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Pasta contendo cinco subpastas (Core, CSS, HTC, Imagens e Saída) que contêm arquivos de suporte usados por [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | Arquivo de configuração usado para definir os diretórios virtuais associados a [!DNL Report Portal] (usado somente com o IIS 6.0). |

   O diretório é semelhante ao seguinte exemplo:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >O nome do diretório pode ser diferente do nome mostrado no exemplo.

1. Renomeie a pasta VSVirtualPortalName (ou outro nome) para o que deseja usar como o diretório virtual raiz de seu [!DNL Report Portal] (a seguir chamado *PortalName*). Para obter mais informações sobre diretórios virtuais, consulte a próxima seção.
