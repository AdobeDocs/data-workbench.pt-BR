---
description: A seguir estão os requisitos e recomendações para a instalação da estação de trabalho (cliente) no Data Workbench.
title: Requisitos da estação de trabalho
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---

# Requisitos da estação de trabalho{#workstation-requirements}

A seguir estão os requisitos e recomendações para a instalação da estação de trabalho (cliente) no Data Workbench.

Consulte [Requisitos do sistema do servidor](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/c-msr-server.html?lang=en) para obter requisitos adicionais do sistema de Data Workbench.

>[!IMPORTANT]
>
>Os componentes servidor, servidor de relatórios e cliente são atualizados para serem executados em sistemas operacionais Windows de 64 bits.

**Antes de começar**

Certifique-se de concluir as tarefas antes de instalar a estação de trabalho do Data Workbench (cliente):

* **** ***AddExcluded*** Processes for  *MS System Center Endpoint Protection in Windows 2012* Server para os seguintes executáveis:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Isso habilitará lista de permissões direitos de  para esses executáveis de interface.

* **Instale o Microsoft Excel para exportar dados de análise.** Para exportar dados de espaços de trabalho como arquivos do Microsoft Excel (  [!DNL .xls] ou  [!DNL .xlsx]), o computador no qual você instala o Data Workbench deve ter o Excel instalado e registrado. Se o Excel não tiver sido registrado e o Data Workbench tentar acessá-lo pela primeira vez, o Excel exibirá uma caixa de diálogo de registro. Se não tiver certeza se a cópia está registrada, inicie o Excel manualmente e, se uma caixa de diálogo de registro for exibida, conclua o processo de registro.

   >[!NOTE]
   >
   >Com o lançamento do Data Workbench 6.4, o suporte para Excel 2007 foi descontinuado. Além disso, como o Data Workbench só é executado no Microsoft Windows para arquitetura de 64 bits, é recomendável também instalar uma versão de 64 bits do Microsoft Excel.

* **Instalação do Adobe  [!DNL Acrobat] para impressão de espaços de trabalho dimensionados em PDF.** Para imprimir espaços de trabalho dimensionados no formato Adobe PDF, o computador no qual você instalou o Data Workbench deve ter o Adobe  [!DNL Acrobat] instalado.

* **Fornecimento de acesso a uma impressora para espaços de trabalho de impressão.** Para imprimir espaços de trabalho do Data Workbench, o computador no qual você instala o Data Workbench deve ter acesso a uma impressora. O Data Workbench pode imprimir espaços de trabalho em impressoras coloridas ou monocromáticas e não requer postscript ou outros recursos avançados da impressora. Para obter melhores resultados, o Adobe recomenda a impressão de espaços de trabalho em cores.
* **Aplicar medidas de segurança.** Você deve seguir as políticas normais de segurança corporativa de sua empresa para computadores Data Workbench. Para atender às suas principais finalidades, o Data Workbench requer apenas a capacidade de se conectar a um servidor (por meio das portas 80 e 443) e a qualquer servidor que colete dados. Você pode usar o hardware da Data Workbench para qualquer outra finalidade, desde que mantenha o software da Data Workbench e aloque pelo menos 10 GB de espaço de armazenamento para a Data Workbench.
* Para renderizar as visualizações com precisão, o computador no qual você instala o workbench deve ter um **adaptador gráfico** apropriado instalado (consulte os requisitos do adaptador gráfico abaixo).

**Requisitos do cliente do Data Workbench**

**Sistema operacional**

* Microsoft Windows 7 de 64 bits
* Microsoft Windows 8.1 de 64 bits
* Microsoft Windows 10 de 64 bits

>[!NOTE]
>
>O Windows XP não é compatível com o Data Workbench 6.1 e versões posteriores.

**Resolução**

* Obrigatório: 1024 x 768 (XGA)
* Recomendado: 1920 x 1200 (WUXGA)

**Adaptador gráfico**

* Obrigatório: Aceleração de hardware OpenGL para oferecer suporte ao OpenGL 3.2
* Recomendado: Adaptador de vídeo dedicado (por exemplo, adaptador NVIDIA ou ATI)

**Processador**

* Obrigatório: 1,2 GHz ou superior Intel ou AMD
* Recomendado: Classe Duo ICore 2

**RAM**

* Obrigatório: 2 GB
* Recomendado: 4 GB

**Conectividade**

* Obrigatório: Link de 512 Kbps para a DPU
* Recomendado: Link de 2 Mbps ou mais rápido para a DPU

**Sistema de arquivos**

NTFS

**Armazenamento em disco**

Pelo menos dez (10) GB ou mais de espaço livre em disco rígido

**Impressão**

Acesso da impressora (impressoras coloridas ou em escala cinza) para espaços de trabalho e relatórios de impressão

**Outro**

* Mouse dedicado
* Ambiente de trabalho de pouco brilho
* Monitor de superfície
