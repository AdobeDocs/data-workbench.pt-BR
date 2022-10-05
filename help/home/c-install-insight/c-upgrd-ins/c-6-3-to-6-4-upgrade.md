---
description: Siga estas etapas para atualizar para o Data Workbench v6.4.
title: Atualização da versão 6.3 para 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
exl-id: 540deb86-2463-4820-b67a-a32d68b4346e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Atualização da versão 6.3 para 6.4{#upgrading-to}

{{eol}}

Siga estas etapas para atualizar para o Data Workbench v6.4.

## Requisitos de atualização e Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Siga estes requisitos e recomendações ao atualizar para a Data Workbench 6.4.

>[!IMPORTANT]
>
>Recomenda-se usar os arquivos de configuração padrão recém-instalados e personalizá-los, em vez de mover os arquivos de uma instalação anterior — com estas exceções:

* **Adicionar** ***Processos excluídos*** para *Proteção do Endpoint do MS System Center em servidores Windows 2012* para os seguintes executáveis:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Isso habilitará lista de permissões direitos de  para esses executáveis de interface.

* **Atualize o *Trust_ca_cert.pem* certificado nos servidores**.
* **Reorganização de perfis de atribuição**.

   * O *Atribuição* a pasta foi renomeada para ***Atribuição - Premium*** (encontrado na instalação padrão em *Perfis*\*Atribuição - Premium*).

   * O *Premium* O perfil foi removido e o espaço de trabalho foi movido para o novo ***Atribuição - Premium*** pasta.

* **Atualizar *Attribution-Premium* configurações**. Se você tiver personalizado perfis com configurações de parâmetro que substituem o padrão *Adobe SC* , é necessário atualizar os campos personalizados nesses arquivos de configuração:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* Devido a essa reorganização, você desejará remover o *Atribuição* e *Premium* da instalação do servidor.

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

* **Atualizar arquivos Meta.cfg personalizados** (se necessário).

   O **[!DNL Meta.cfg]** arquivos em **[!DNL Base\Context and AdobeSC\Context]** As pastas foram atualizadas nesta versão.

   Se você substituir o **meta.cfg** durante a instalação, a cópia do perfil precisa ser atualizada com esses parâmetros e o **vetor de metadados** devidamente inscrito:

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

* **Definir permissões do Servidor de relatórios** para gerar relatórios do Microsoft Excel nos servidores do Windows 2012.

   1. Defina a permissão da pasta raiz (**[!DNL E:\ReportServer\]**) a *Todos = controle total*.

   1. Crie as seguintes pastas com as permissões apropriadas:

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Se você estiver executando o Report Server no Windows Server 2012, precisará ter o Windows Server 2012 R2 instalado.

   1. Atribua &quot;SYSTEM&quot; como proprietário para essas pastas.

* **Adicionar fontes ao servidor de relatórios.** No **[!DNL ReportServer.cfg]**arquivo, adicione essas fontes (para todos os idiomas):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Atualize sua versão do Microsoft Excel ** (se necessário).

   Com o lançamento do Data Workbench 6.4, o suporte para Excel 2007 foi descontinuado. Além disso, como o Data Workbench só é executado no Microsoft Windows para arquitetura de 64 bits, é recomendável também instalar uma versão de 64 bits do Microsoft Excel.

* **Arquitetura de 64 bits** necessário para a instalação da estação de trabalho (cliente).
* **Execute o Assistente de configuração da estação de trabalho**.

   Instale a nova versão da estação de trabalho (cliente) baixando e iniciando ***InsightSetup.exe*** e seguindo as instruções de configuração. Por padrão, o assistente de configuração instalará seus arquivos em um novo local:

   Os arquivos de programa agora são salvos por padrão em:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   Os arquivos de dados (perfis, certificados, logs de rastreamento e arquivos de usuário) agora são salvos por padrão em:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Adicionar fontes à estação de trabalho**.

   No **[!DNL Insight.cfg]** , adicione essas fontes (para todos os idiomas):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```
