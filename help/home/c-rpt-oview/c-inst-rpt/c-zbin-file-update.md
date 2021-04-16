---
description: Para todos os idiomas, o Servidor de relatórios 6.0 e posterior requer o arquivo "insight.zbin" copiado para a pasta raiz do Servidor de relatórios.
title: Atualizar o servidor de relatórios com um arquivo de idioma (arquivo .zbin)
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
exl-id: a76b7c01-83f0-4cf2-97a9-07d51cc75b3c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 10%

---

# Atualizar o servidor de relatórios com um arquivo de idioma (arquivo .zbin){#update-report-server-with-a-language-file-zbin-file}

Para todos os idiomas, o Servidor de relatórios 6.0 e posterior requer o arquivo &quot;insight.zbin&quot; copiado para a pasta raiz do Servidor de relatórios.

Atualize os arquivos de idioma do Report Server:

1. Adicione o arquivo &quot;insight.zbin&quot; renomeado para o diretório raiz do ReportServer.
1. O arquivo de configuração do Servidor de Relatórios (reportserver.cfg) requer configurações de fonte para idiomas de byte duplo. Por exemplo, chinês requer a adição de fontes usando SimSun:

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Um parâmetro para o Report Server 6.0 precisa ser transmitido na linha de comando para localização, por exemplo:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Se uma localidade não for especificada, o Servidor de relatório assumirá inglês como padrão.

   Siga as etapas para iniciar o ReportServer como um serviço com os parâmetros Locais:

   1. Inicie um prompt de comando como administrador.
   1. Navegue até a pasta de instalação do ReportServer.
   1. Digite o seguinte comando para iniciar o serviço:

      * Em inglês: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Para chinês: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Para verificar se o ReportServer está em execução com os parâmetros corretos:

   1. Abra o Gerenciador de Serviços do Windows.
   1. Clique com o botão direito do mouse em [!DNL Adobe Insight Report Server - Properties].

   O caminho para executável conterá os parâmetros:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```
