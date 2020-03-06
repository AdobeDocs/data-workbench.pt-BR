---
description: Para todos os idiomas, o Servidor de relatórios 6.0 e posterior requer o arquivo "insight.zbin" copiado para a pasta raiz do Servidor de relatórios.
solution: Analytics
title: Atualizar o Servidor de Relatório com um arquivo de idioma (arquivo .zbin)
topic: Data workbench
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Atualizar o Servidor de Relatório com um arquivo de idioma (arquivo .zbin){#update-report-server-with-a-language-file-zbin-file}

Para todos os idiomas, o Servidor de relatórios 6.0 e posterior requer o arquivo &quot;insight.zbin&quot; copiado para a pasta raiz do Servidor de relatórios.

Atualize os arquivos de idioma do Servidor de relatórios:

1. Adicione o arquivo renomeado como &quot;insight.zbin&quot; ao diretório raiz do ReportServer.
1. O arquivo de configuração do Servidor de relatórios (reportserver.cfg) requer configurações de fonte para idiomas de byte duplo. Por exemplo, o chinês exige a adição de fontes usando o SimSun:

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
   >Se uma localidade não for especificada, o Servidor de relatórios assumirá inglês como padrão.

   Siga as etapas para iniciar o ReportServer como um serviço com os parâmetros Locale:

   1. Inicie um prompt de comando como administrador.
   1. Navegue até a pasta de instalação do ReportServer.
   1. Digite o seguinte comando para iniciar o serviço:

      * Para inglês: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Para chinês: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Para verificar se o ReportServer está em execução com os parâmetros corretos:

   1. Abra o Windows Service Manager.
   1. Clique com o botão direito do mouse [!DNL Adobe Insight Report Server - Properties].
   O caminho para o executável conterá os parâmetros:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

