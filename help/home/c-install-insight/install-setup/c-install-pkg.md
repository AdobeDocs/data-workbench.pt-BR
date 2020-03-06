---
description: Arquivos incluídos no pacote de instalação do Análise de big data.
title: Arquivos incluídos no pacote de instalação
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arquivos incluídos no pacote de instalação{#files-included-in-the-installation-package}

Arquivos incluídos no pacote de instalação do Análise de big data.

Os seguintes diretórios estão incluídos no pacote Insight.

## Arquivos de programa {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

Por padrão, os arquivos executáveis (**[!DNL Insight.exe]**) e de suporte da estação de trabalho são instalados nessa pasta.

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
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span></b> </td> 
   <td colname="col2"> O executável de cliente do Análise de big data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span></b> </td> 
   <td colname="col2"> Defina o idioma e o caminho para a <span class="filepath"> pasta Appdata </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span></b> </td> 
   <td colname="col2"> <p>A análise de big data agora oferece suporte a um Editor de método de entrada (IME) como um processo de entrada de texto secundário que permite inserir caracteres internacionais do teclado usando uma caixa de texto flutuante. A análise de big data suporta inglês por padrão, mas também permite carregar outros arquivos para suportar idiomas internacionais, como um teclado chinês virtual (Pinyin IME). </p> <p>Um novo arquivo de dicionário <span class="filepath"> (Insight.zbin </span>) é necessário para o aplicativo cliente suportar o IME. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Executável para desinstalar a estação de trabalho e excluir arquivos. </td> 
  </tr> 
 </tbody> 
</table>

## Arquivos AppData {#section-afddeedf8d29451f996fa46b2dfe932c}

Por padrão, os arquivos de dados (**[!DNL Insight.cfg]**, perfis, certificados, registros de rastreamento e arquivos de usuário) são salvos para:

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
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span></b> </td> 
   <td colname="col2"> O arquivo de configuração do Análise de big data. Define parâmetros dentro dos quais a Análise de big data opera. Consulte <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Configurando a conexão com o Insight Server </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span></b> </td> 
   <td colname="col2"> <p>Contém os arquivos de programa para o Análise de big data. </p> <p> <p>Observação:  Você não deve remover ou alterar nenhum desses arquivos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificados </span></b> </td> 
   <td colname="col2"> Contém o arquivo de certificado, <span class="filepath"> trust_ca_cert.pem </span>e o certificado digital de usuário nomeado para o Análise de big data. Consulte <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Download e instalação do certificado digital </a>. </td> 
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
   <td colname="col1"> <b> <span class="filepath"> Rastreamento </span></b> </td> 
   <td colname="col2"> Registre os arquivos gerados a partir da estação de trabalho. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Perfis </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>, <i>Predictive Analytics</i> e outros arquivos de configuração de perfil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> Assistente de configuração para instalar computadores cliente adicionais na pasta <b> Software/Insight <span class="filepath"> </span></b> . </td> 
  </tr> 
 </tbody> 
</table>

