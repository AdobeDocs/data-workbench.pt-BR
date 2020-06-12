---
description: Siga estas etapas para atualizar para o Análise de big data v6.4.
title: Atualização de 6.3 para 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 2930bd3ae06e700e75144221fc993efdd6bd1e85
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---


# Upgrading 6.3 to 6.4{#upgrading-to}

Siga estas etapas para atualizar para o Análise de big data v6.4.

## Requisitos e recomendações de atualização {#section-8704a9ac358246cd81233dd0982d534f}

Siga estes requisitos e recomendações ao atualizar para o Análise de big data 6.4.

>[!IMPORTANT]
>
>É recomendável usar os arquivos de configuração padrão recém-instalados e personalizá-los, em vez de mover arquivos de uma instalação anterior — com as seguintes exceções:

* **Adicione** processos ****** excluídos para o *MS System Center Endpoint Protection nos servidores* Windows 2012 para os seguintes executáveis:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Isso ativará os direitos permitidos para esses executáveis de interface.

* **Atualize o certificado *Trust_ca_cert.pem*nos servidores**.
* **Reorganização de Perfis** de Atribuição.

   * A pasta *Atribuição* foi renomeada para ***Atribuição - Premium*** (encontrada na instalação padrão em *Perfis*\*Atribuição - Premium*).

   * O perfil *Premium* foi removido e o espaço de trabalho foi movido para a nova pasta ***Atribuição - Premium*** .

* **Atualize as configurações *de Atribuição-Premium***. Se você personalizou perfis com configurações de parâmetro que substituem o perfil padrão *Adobe SC* , é necessário atualizar os campos personalizados nesses arquivos de configuração:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* Devido a essa reorganização, você desejará remover as antigas pastas *Atribuição* e *Premium* da instalação do servidor.

   **Alterar estas definições**

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 6 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
   
       4 = string: Attribution\\ 
       5 = string: Premium\\
   ```

   para estas configurações:

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\
       4 = string: Attribution - Premium\\
   ```

* **Atualize os arquivos** personalizados Meta.cfg (se necessário).

   Os **[!DNL Meta.cfg]** arquivos em **[!DNL Base\Context and AdobeSC\Context]** pastas foram atualizados nesta versão.

   Se você substituir o arquivo **meta.cfg** durante a instalação, a cópia do perfil precisará ser atualizada com esses parâmetros e o vetor **de** metadados inserido adequadamente:

   ```
   94 = meta: 
     path = string: SegmentExport:CRS Configuration/CRS Attributes 
     acceptable children = vector: 1 items 
       0 = Template: 
         name = string: CRS Attributes 
         value = CRSAttributeConfiguration: 
           Attribute Name = string: 
           Attribute Type(int,string) = string: 
           Field Name = string: 
   
   95 = meta: 
     path = string: SegmentExportQuery:CRS Configuration/Report Suite 
     acceptable children = vector: 1 items 
       0 = Template 
         name = string: Add Report Suite 
         value = string:
   ```

* **Defina permissões** do Servidor de Relatório para gerar relatórios do Microsoft Excel em servidores Windows 2012.

   1. Defina a permissão da pasta raiz (**[!DNL E:\ReportServer\]**) como *Todos = controle* total.

   1. Crie as seguintes pastas com as permissões apropriadas:

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Se você estiver executando o Servidor de relatórios no Windows Server 2012, precisará ter o Windows Server 2012 R2 instalado.

   1. Atribua &quot;SYSTEM&quot; como proprietário para estas pastas.

* **Adicionar fontes ao Servidor de relatórios.** No arquivo **[!DNL ReportServer.cfg]**s, adicione estas fontes (para todos os idiomas):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Atualize sua versão do Microsoft Excel ** (se necessário).

   Com o lançamento do Análise de big data 6.4, o suporte ao Excel 2007 foi descontinuado. Além disso, como o Análise de big data só é executado no Microsoft Windows para a arquitetura de 64 bits, recomenda-se instalar uma versão de 64 bits do Microsoft Excel.

* **Arquitetura** de 64 bits necessária para a instalação da Workstation (Cliente).
* **Execute o Assistente** de configuração da estação de trabalho.

   Instale a nova versão da estação de trabalho (cliente) baixando e iniciando o ***InsightSetup.exe*** e seguindo as instruções de configuração. Por padrão, o assistente de instalação instalará seus arquivos em um novo local:

   Os arquivos de Programa agora são salvos por padrão em:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Os arquivos de dados (perfis, certificados, registros de rastreamento e arquivos de usuário) agora são salvos por padrão para:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Adicione fontes à estação de trabalho**.

   No **[!DNL Insight.cfg]** arquivo, adicione essas fontes (para todos os idiomas):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

