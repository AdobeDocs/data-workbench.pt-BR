---
description: Arquivos incluídos no pacote de instalação do Data Workbench.
title: Arquivos incluídos no pacote de instalação
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
exl-id: 086fb49c-d492-4670-938b-7ede70a7cd16
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 5%

---

# Arquivos incluídos no pacote de instalação{#files-included-in-the-installation-package}

{{eol}}

Arquivos incluídos no pacote de instalação do Data Workbench.

Os seguintes diretórios estão incluídos no pacote Insight .

## Arquivos de programa {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

O executável Workstation (**[!DNL Insight.exe]**) e os arquivos de suporte são instalados por padrão nessa pasta.

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Diretório </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span> </b> </td> 
   <td colname="col2"> O executável do cliente Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span> </b> </td> 
   <td colname="col2"> Defina o idioma e o caminho para o <span class="filepath"> Appdata </span> pasta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span> </b> </td> 
   <td colname="col2"> <p>O Data Workbench agora é compatível com o Editor de método de entrada (IME) como um processo de entrada de texto secundário que permite inserir caracteres internacionais do teclado usando uma caixa de texto flutuante. Por padrão, o Data Workbench oferecerá suporte ao inglês, mas também permitirá que você carregue outros arquivos para suportar idiomas internacionais, como um teclado chinês virtual (Pinyin IME). </p> <p>Um novo arquivo de dicionário <span class="filepath"> (Insight.zbin </span>) é exigido pelo aplicativo cliente para suportar o IME. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Executável para desinstalar a Workstation e excluir arquivos. </td> 
  </tr> 
 </tbody> 
</table>

## Arquivos AppData {#section-afddeedf8d29451f996fa46b2dfe932c}

Arquivos de dados (**[!DNL Insight.cfg]**, Perfis, Certificados, logs de rastreamento e arquivos de usuário) são salvos por padrão em:

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Diretório </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span> </b> </td> 
   <td colname="col2"> O arquivo de configuração do Data Workbench. Define parâmetros dentro dos quais o Data Workbench opera. Consulte <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Configuração da conexão com o servidor Insight </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span> </b> </td> 
   <td colname="col2"> <p>Contém os arquivos de programa do Data Workbench. </p> <p> <p>Observação: Você não deve remover ou alterar nenhum desses arquivos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificados </span> </b> </td> 
   <td colname="col2"> Contém o arquivo de certificado, <span class="filepath"> trust_ca_cert.pem </span>e o certificado digital do usuário nomeado para o Data Workbench. Consulte <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Download e instalação do certificado digital </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Configuração </span> </b> </td> 
   <td colname="col2"> Contém os arquivos usados para a configuração da estação de trabalho. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Geografia </span></b> </td> 
   <td colname="col2"> Arquivos para renderização gráfica de visualizações geográficas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Rastreio </span></b> </td> 
   <td colname="col2"> Arquivos de log gerados a partir da estação de trabalho. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Perfis </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>, <i>Análise preditiva</i> e outros arquivos de configuração de perfil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> Assistente de Instalação para instalar computadores cliente adicionais na <b> <span class="filepath"> Software/Insight </span></b> pasta. </td> 
  </tr> 
 </tbody> 
</table>
