---
description: Para que alguns dos recursos do Servidor de relatórios funcionem, é necessário fornecer e configurar hardware ou software antes de instalar.
solution: Analytics
title: Antes de começar
topic: Data workbench
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Antes de começar{#before-you-begin}

Para que alguns dos recursos do Servidor de relatórios funcionem, é necessário fornecer e configurar hardware ou software antes de instalar.

## Requisitos básicos do servidor de relatórios {#section-e891eaee79fe4fa98e658426dc3b2777}

Os relatórios que são enviados podem estar na forma de imagens .PNG ou planilhas .XLS colocadas em um sistema de arquivos, ou como emails. Os requisitos de hardware são idênticos ao cliente [](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)da análise de big data.

Os seguintes requisitos existem para o Servidor de relatórios:

* Acesso ao sistema de arquivos para saída de dados (compartilhamento de rede ou unidade local).
* Acesso ao servidor SMTP configurado.
* Microsoft Excel 2010 de 64 bits ou superior instalado no [!DNL Report] Server. Consulte [Considerações para automação do Office](http://support.microsoft.com/kb/257757) no servidor para obter mais informações.

## Requisitos adicionais {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Instale um adaptador gráfico apropriado.** Para renderizar corretamente os relatórios, o computador no qual você instala o [!DNL Report] Servidor precisa ter um adaptador gráfico apropriado instalado.

* **Instale o Microsoft Excel para gerar relatórios como arquivos do Excel.** Para gerar e distribuir relatórios como arquivos do Microsoft Excel ( [!DNL .xls] ou [!DNL .xlsx]), a máquina na qual você instala o Report Server deve ter a versão apropriada do Microsoft Excel de 64 bits instalada e registrada. Se o Excel não tiver sido registrado e o Servidor de Relatórios tentar acessá-lo pela primeira vez, o Excel exibirá uma caixa de diálogo de registro. Se não tiver certeza se a cópia está registrada, inicie o Excel manualmente e, se uma caixa de diálogo de registro for exibida, conclua o processo de registro.

   >[!NOTE]
   >
   >Ao gerar relatórios como arquivos do Excel, você está abrindo uma nova instância do Excel. Para obter mais informações sobre esse processo, consulte [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).

* **Forneça acesso a um servidor SMTP para distribuir relatórios por email.** Se você deseja distribuir relatórios por email, o Servidor de relatórios deve poder se conectar a um servidor SMTP e as portas apropriadas ao serviço de encaminhamento de email devem ser abertas.

