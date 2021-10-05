---
description: Para que alguns dos recursos do Servidor de relatórios funcionem, você deve fornecer e configurar o hardware ou software antes de instalar o.
title: Antes de começar
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# Antes de começar{#before-you-begin}

Para que alguns dos recursos do Servidor de relatórios funcionem, você deve fornecer e configurar o hardware ou software antes de instalar o.

## Requisitos básicos do servidor de relatórios {#section-e891eaee79fe4fa98e658426dc3b2777}

Os relatórios enviados podem estar na forma de imagens .PNG ou planilhas .XLS colocadas em um sistema de arquivos ou como emails. Os requisitos de hardware são idênticos ao [cliente do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements).

Existem os seguintes requisitos para o Servidor de relatórios:

* Acesso ao sistema de arquivos para saída de dados (compartilhamento de rede ou unidade local).
* Acesso ao servidor SMTP configurado.
* Microsoft Excel 2010 de 64 bits ou superior instalado no Servidor [!DNL Report]. Consulte [Considerações para automação do lado do servidor do Office](https://support.microsoft.com/kb/257757) para obter mais informações.

## Requisitos adicionais {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Instale um adaptador gráfico apropriado.** Para renderizar os relatórios adequadamente, a máquina na qual você instala o  [!DNL Report] Servidor deve ter um adaptador gráfico apropriado instalado.

* **Instale o Microsoft Excel para gerar relatórios como arquivos do Excel.** Para gerar e distribuir relatórios como arquivos do Microsoft Excel (  [!DNL .xls] ou  [!DNL .xlsx]), a máquina na qual você instala o Report Server deve ter a versão apropriada do Microsoft Excel de 64 bits instalada e registrada. Se o Excel não tiver sido registrado e o Servidor de Relatórios tentar acessá-lo pela primeira vez, o Excel exibirá uma caixa de diálogo de registro. Se não tiver certeza se a cópia está registrada, inicie o Excel manualmente e, se uma caixa de diálogo de registro for exibida, conclua o processo de registro.

   >[!NOTE]
   >
   >Ao gerar relatórios como arquivos do Excel, você está abrindo uma nova instância do Excel. Para obter mais informações sobre esse processo, consulte [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).

* **Forneça acesso a um servidor SMTP para distribuir relatórios por e-mail.** Se você quiser distribuir relatórios por email, o Report Server deve ser capaz de se conectar a um servidor SMTP e as portas apropriadas para o serviço de encaminhamento de email devem ser abertas.
