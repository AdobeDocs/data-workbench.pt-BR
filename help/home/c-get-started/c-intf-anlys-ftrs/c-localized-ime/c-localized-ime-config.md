---
description: Configure o arquivo insight.zbin para definir o idioma do aplicativo cliente.
title: Configuração de idiomas localizados
uuid: 97baf281-32fd-4df0-81a6-c2c7126b053c
exl-id: 29624b3a-e26a-48a9-9dcc-21ba829c34d4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Configuração de idiomas localizados{#setting-up-localized-languages}

{{eol}}

Configure o arquivo insight.zbin para definir o idioma do aplicativo cliente.

## Atualizar os componentes do servidor do Data Workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

Primeiro, o administrador deve concluir essas tarefas para atualizar esses componentes do servidor:

1. **Atualização para o servidor do Data Workbench 6.x.** Você precisa atualizar o servidor do Data Workbench para localização atualizando o [!DNL base\localization\*.zbin] arquivo. Essa [!DNL insight.zbin] O arquivo será copiado para o cliente.

   Um [!DNL insight.zbin] está incluído na pasta de instalação ao lado do [!DNL insight.exe] arquivo. Se você se conectar a um servidor que não fornece um idioma específico [!DNL .zbin] arquivos, então o Data Workbench continuará a usar esse arquivo.

   O backup [!DNL insight.zbin] pode ser fornecido em qualquer idioma. Como resultado, se você usar o Data Workbench em chinês e se conectar a um servidor que não suporta esse idioma, seu cliente do Data Workbench ainda estará em chinês, mesmo que o servidor altere seu perfil básico e remova seu [!DNL .zbin] arquivos da [!DNL Base/Localization] pasta.

1. **Atualize o servidor de relatório do Data Workbench.** O [!DNL insight.zbin] por padrão, na pasta raiz do servidor de relatórios do Data Workbench estará em inglês. Como administrador, você deverá selecionar e copiar a variável [!DNL .zbin] do pacote atualizado do servidor de relatórios e coloque-o no diretório raiz do servidor de relatórios do Data Workbench. Como o cliente, o servidor de relatórios também requer os argumentos adequados para o idioma selecionado, como [!DNL Insight.exe -zh-cn]

   1. Pare os serviços do servidor de relatórios.
   1. Copie o [!DNL Localization] pasta do novo pacote do servidor de relatórios.
   1. No [!DNL Localization] , copie a [!DNL Insight.zbin] e coloque-o no diretório raiz do servidor de relatórios, onde a função [!DNL Insight.exe] está localizado.

   1. Adicione quaisquer argumentos necessários, como [!DNL insight.exe -zh-cn]
   1. Reinicie o servidor de relatórios.

## Atualizar o cliente do Data Workbench {#section-9653d3fcaf2a4337a97b685857e7aeac}

Após atualizar o servidor, siga estas etapas para atualizar cada cliente.

1. Para garantir que o cliente não seja atualizado do servidor durante essa atualização, defina [!DNL Insight.cfg] para Falso.

   ```
   Update Software = bool: false
   ```

1. Reinicie o cliente.
1. Navegue até o perfil Software and Docs (perfil SoftDocs) e baixe o **[!UICONTROL insight.zbin]** do pacote do cliente: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Mova o [!DNL insight.zbin] para a pasta onde [!DNL insight.exe] está localizado.

1. Para garantir que os arquivos do cliente agora sejam atualizados do servidor, altere o [!DNL Insight.cfg] argumento de arquivo para Verdadeiro:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Seu cliente sincronizará com o servidor e você verá uma mensagem informando que está atualizando. No final do download, você receberá uma mensagem perguntando se deseja reiniciar o cliente.

1. Clique em **OK** para reiniciar o cliente.

Se você receber a seguinte mensagem, significa que a variável [!DNL zbin] O arquivo não foi colocado no mesmo local que o [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Telas iniciais localizadas**

O Data Workbench busca os seguintes arquivos de tela inicial:

* Inglês (padrão): [!DNL Base/Images/<version_product> Splash.png]
* Chinês (quando iniciado com -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

Se uma tela inicial for solicitada, mas estiver ausente, o Data Workbench acessará a tela inicial em inglês por padrão.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
