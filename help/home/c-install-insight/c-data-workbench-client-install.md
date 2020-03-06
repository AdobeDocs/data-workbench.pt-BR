---
description: A seguir estão os requisitos e recomendações para a instalação da estação de trabalho (Cliente) na análise de big data.
solution: Analytics
title: Requisitos da workstation
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Requisitos da workstation{#workstation-requirements}

A seguir estão os requisitos e recomendações para a instalação da estação de trabalho (Cliente) na análise de big data.

Consulte Requisitos [do sistema do](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) servidor para obter os requisitos adicionais do sistema da análise de big data.

>[!IMPORTANT]
>
>Os componentes servidor, servidor de relatório e cliente são atualizados para serem executados em sistemas operacionais Windows de 64 bits.

**Antes de começar**

Verifique se essas tarefas foram concluídas antes de instalar a estação de trabalho de análise de big data (cliente):

* **Adicione** processos ****** excluídos para o *MS System Center Endpoint Protection nos servidores* Windows 2012 para os seguintes executáveis:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Isso permitirá direitos de &quot;lista branca&quot; para esses executáveis de interface.

* **Instale o Microsoft Excel para exportar dados de análise.** Para exportar dados de espaços de trabalho como arquivos do Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), o computador no qual você instala o Análise de big data deve ter o Excel instalado e registrado. Se o Excel não tiver sido registrado e o Análise de big data tentar acessá-lo pela primeira vez, o Excel exibirá uma caixa de diálogo de registro. Se não tiver certeza se a cópia está registrada, inicie o Excel manualmente e, se uma caixa de diálogo de registro for exibida, conclua o processo de registro.

   >[!NOTE]
   >
   >Com o lançamento do Análise de big data 6.4, o suporte ao Excel 2007 foi descontinuado. Além disso, como o Análise de big data só é executado no Microsoft Windows para a arquitetura de 64 bits, recomenda-se instalar uma versão de 64 bits do Microsoft Excel.

* **Instalação da Adobe[!DNL Acrobat]para impressão de espaços de trabalho dimensionados em PDF.** Para imprimir espaços de trabalho dimensionados no formato Adobe PDF, o computador no qual você instalou o Análise de big data deve ter a Adobe [!DNL Acrobat] instalada.

* **Fornecimento de acesso a uma impressora para espaços de trabalho de impressão.** Para imprimir espaços de trabalho do Análise de big data, o computador no qual você instala o Análise de big data deve ter acesso a uma impressora. O Análise de big data pode imprimir espaços de trabalho em impressoras coloridas ou monocromáticas e não requer o postscript ou outros recursos avançados da impressora. Para obter resultados ideais, a Adobe recomenda a impressão de espaços de trabalho coloridos.
* **Aplicar medidas de segurança.** Você deve seguir as políticas de segurança corporativas normais de sua empresa para computadores com a Análise de big data. Para atender aos fins principais, o Análise de big data exige apenas a capacidade de se conectar a um servidor (pelas portas 80 e 443) e a qualquer servidor que coleta dados. Você pode usar o hardware da Análise de big data para qualquer outra finalidade, desde que mantenha o software da Análise de big data e aloque pelo menos 10 GB de espaço de armazenamento para a Análise de big data.
* Para renderizar as visualizações com precisão, o computador no qual você instala o workbench deve ter um adaptador **** gráfico apropriado instalado (consulte os requisitos do adaptador gráfico abaixo).

**Requisitos do cliente da análise de big data**

**Sistema operacional**

* Microsoft Windows 7 de 64 bits
* Microsoft Windows 8.1 de 64 bits
* Microsoft Windows 10 de 64 bits

>[!NOTE]
>
>O Windows XP não é compatível com o Análise de big data 6.1 e versões posteriores.

**Resolução**

* Obrigatório: 1024 x 768 (XGA)
* Recomendado: 1920 x 1200 (WUXGA)

**Adaptador gráfico**

* Obrigatório: Aceleração de hardware OpenGL para suportar OpenGL 3.2
* Recomendado: Adaptador de vídeo dedicado (por exemplo, adaptador NVIDIA ou ATI)

**Processador**

* Obrigatório: 1,2 GHz ou superior Intel ou AMD
* Recomendado: ICore 2 Duo-Class

**RAM**

* Obrigatório: 2 GB
* Recomendado: 4 GB

**Conectividade**

* Obrigatório: Link de 512 Kbps para a DPU
* Recomendado: Link de 2 Mbps ou mais rápido para a DPU

**Sistema de arquivos**

NTFS

**Armazenamento em disco**

Pelo menos dez (10) GB ou mais de espaço livre na unidade de disco rígido

**Impressão**

Acesso da impressora (impressoras coloridas ou em escala cinza) para imprimir espaços de trabalho e relatórios

**Outro**

* Mouse dedicado
* Ambiente de trabalho de pouco brilho
* Monitor de superfície fosca

