---
description: Configure o arquivo insight.zbin para definir o idioma do aplicativo cliente.
solution: Analytics
title: Configuração de idiomas localizados
topic: Data workbench
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuração de idiomas localizados{#setting-up-localized-languages}

Configure o arquivo insight.zbin para definir o idioma do aplicativo cliente.

## Atualizar os componentes do servidor da análise de big data {#section-5d07a081befc4eaa8fdf7fea904e0d48}

O administrador deve primeiro concluir essas tarefas para atualizar esses componentes do servidor:

1. **Atualizar para o servidor 6.x da análise de big data.** É necessário atualizar o servidor da análise de big data para localização atualizando o [!DNL base\localization\*.zbin] arquivo. Esse [!DNL insight.zbin] arquivo será copiado para o cliente.

   Um [!DNL insight.zbin] arquivo é incluído na pasta de instalação ao lado do [!DNL insight.exe] arquivo. Se você se conectar a um servidor que não fornece a você [!DNL .zbin] arquivos específicos de idioma, o análise de big data continuará usando esse arquivo.

   O [!DNL insight.zbin] arquivo de backup pode ser fornecido em qualquer idioma. Como resultado, se você usar a análise de big data em chinês e se conectar a um servidor que não suporta esse idioma, o cliente da análise de big data ainda estará em chinês, mesmo se o servidor alterar seu perfil básico e remover seus [!DNL .zbin] arquivos da [!DNL Base/Localization] pasta.

1. **Atualize o servidor de relatório da análise de big data.** Por padrão, a pasta raiz do servidor de relatório da análise de big data [!DNL insight.zbin] estará em inglês. Como administrador, você deverá selecionar e copiar o [!DNL .zbin] arquivo do pacote atualizado do servidor de relatório e colocá-lo no diretório raiz do servidor de relatório da análise de big data. Como o cliente, o servidor de relatório também requer os argumentos apropriados para o idioma selecionado, como [!DNL Insight.exe -zh-cn]

   1. Pare os serviços do servidor de relatórios.
   1. Copie a [!DNL Localization] pasta do novo pacote do servidor de relatórios.
   1. Na [!DNL Localization] pasta, copie o [!DNL Insight.zbin] arquivo e coloque-o no diretório raiz do servidor de relatório em que [!DNL Insight.exe] ele está localizado.

   1. Adicione quaisquer argumentos necessários, como [!DNL insight.exe -zh-cn]
   1. Reinicie o servidor de relatórios.

## Atualizar o cliente da análise de big data {#section-9653d3fcaf2a4337a97b685857e7aeac}

Após atualizar o servidor, siga estas etapas para atualizar cada cliente.

1. Para garantir que o cliente não seja atualizado do servidor durante esta atualização, defina seu [!DNL Insight.cfg] argumento como False.

   ```
   Update Software = bool: false
   ```

1. Reinicie o cliente.
1. Navegue até o perfil Software and Docs (perfil SoftDocs) e baixe o arquivo necessário do **[!UICONTROL insight.zbin]** pacote do cliente: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Mova o [!DNL insight.zbin] arquivo para a pasta onde [!DNL insight.exe] está localizado.

1. Para garantir que os arquivos cliente sejam atualizados a partir do servidor, altere o argumento do [!DNL Insight.cfg] arquivo para Verdadeiro:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Seu cliente será sincronizado com o servidor e você verá uma mensagem informando que ele está sendo atualizado. Ao concluir o download, você receberá uma mensagem perguntando se deseja reiniciar seu cliente.

1. Clique em **OK** para reiniciar o cliente.

Se você receber a seguinte mensagem, isso significa que o [!DNL zbin] arquivo não foi colocado no mesmo local do [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Telas iniciais localizadas**

A análise de big data procura os seguintes arquivos de tela de apresentação:

* Inglês (padrão): [!DNL Base/Images/<version_product> Splash.png]
* Chinês (quando iniciado com -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

Se uma tela inicial for solicitada, mas estiver ausente, o análise de big data acessará a tela inicial em inglês por padrão.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

