---
description: O portal de relatórios é composto de um conjunto de páginas do servidor de aplicativos (ASPs) e arquivos de suporte.
title: Instalar os arquivos do aplicativo do portal de relatórios
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Instalar os arquivos do aplicativo do portal de relatórios{#install-the-report-portal-application-files}

{{eol}}

O portal de relatórios é composto de um conjunto de páginas do servidor de aplicativos (ASPs) e arquivos de suporte.

Para instalar o [!DNL Report Portal], você deve extrair esses arquivos do arquivo de distribuição recebido do Adobe e instalá-los na máquina em que o Microsoft IIS está sendo executado.

**Para instalar o [!DNL Report Portal] arquivos de aplicativo**

1. Se ainda não tiver feito isso, baixe o pacote de instalação (arquivo .zip) da variável [!DNL Report Portal] do site Adobe FTP.
1. Na máquina em que o IIS está sendo executado, extraia os arquivos no pacote de instalação para qualquer local. Esta etapa instala as seguintes subpastas e arquivos na pasta VSVirtualPortalName.

   | Pasta ou arquivo | Descrição |
   |---|---|
   | [!DNL \data\users.mdb] | Base de dados que contém a lista de [!DNL Report Portal] usuários. |
   | [!DNL \PortalASP\] | Pasta contendo os arquivos ASP que compõem [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Pasta contendo cinco subpastas (Core, CSS, HTC, Imagens e Saída) que contêm arquivos de suporte usados por [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | Arquivo de configuração usado para definir os diretórios virtuais associados ao [!DNL Report Portal] (usado somente com o IIS 6.0). |

   O diretório é semelhante ao seguinte exemplo:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >O nome do diretório pode ser diferente do nome mostrado no exemplo.

1. Renomeie a pasta VSVirtualPortalName (ou outro nome) para o que deseja usar como o diretório virtual raiz de seu [!DNL Report Portal] (adiante designada por *PortalName*). Para obter mais informações sobre diretórios virtuais, consulte a próxima seção.
