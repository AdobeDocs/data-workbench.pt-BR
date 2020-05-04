---
description: O Portal de relatórios é composto de um conjunto de páginas do servidor de aplicativos (ASPs) e arquivos de suporte.
solution: Analytics
title: Instalar os arquivos de aplicativo do portal de relatórios
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
translation-type: tm+mt
source-git-commit: 7521fe7f5fabe8e1be26e140ffff577a42fce88b

---


# Instalar os arquivos de aplicativo do portal de relatórios{#install-the-report-portal-application-files}

O Portal de relatórios é composto de um conjunto de páginas do servidor de aplicativos (ASPs) e arquivos de suporte.

Para instalar o [!DNL Report Portal], você deve extrair esses arquivos do arquivo de distribuição recebido da Adobe e instalá-los no computador em que o Microsoft IIS está sendo executado.

**Para instalar os arquivos do[!DNL Report Portal]aplicativo**

1. Caso ainda não o tenha feito, baixe o pacote de instalação (arquivo .zip) do site FTP da Adobe [!DNL Report Portal] para o site.
1. Na máquina em que o IIS está sendo executado, extraia os arquivos no pacote de instalação para qualquer local. Esta etapa instala as seguintes subpastas e arquivos na pasta VSVirtualPortalName.

   | Pasta ou arquivo | Descrição |
   |---|---|
   | [!DNL \data\users.mdb] | Banco de dados que contém a lista de [!DNL Report Portal] usuários autorizados. |
   | [!DNL \PortalASP\] | Pasta que contém os arquivos ASP que compõem [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Pasta que contém cinco subpastas (Core, CSS, HTC, Imagens e Saída) que contêm arquivos de suporte usados por [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | Arquivo de configuração usado para definir os diretórios virtuais associados [!DNL Report Portal] (usado somente com o IIS 6.0). |

   O diretório é semelhante ao seguinte exemplo:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >O nome do diretório pode ser diferente do nome mostrado no exemplo.

1. Renomeie a pasta VSVirtualPortalName (ou outro nome) para o que você deseja usar como o diretório virtual raiz do seu [!DNL Report Portal] (a seguir denominado *PortalName*). Para obter mais informações sobre diretórios virtuais, consulte a próxima seção.
