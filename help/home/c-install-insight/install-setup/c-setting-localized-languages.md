---
description: Configure o arquivo insight.zbin para definir o idioma do aplicativo cliente.
title: Configuração de idiomas localizados
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Configuração de idiomas localizados{#setting-up-localized-languages}

Configure o arquivo insight.zbin para definir o idioma do aplicativo cliente.

## Atualizar os componentes do servidor do Data Workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

Primeiro, o administrador deve concluir essas tarefas para atualizar esses componentes do servidor:

1. **Atualizar para o servidor do Data Workbench 6.x.** Você precisa atualizar o servidor do Data Workbench para localização atualizando o  [!DNL base\localization\*.zbin] arquivo. Esse arquivo [!DNL insight.zbin] será copiado para o cliente.

   Um arquivo [!DNL insight.zbin] é incluído na pasta de instalação ao lado do arquivo [!DNL insight.exe]. Se você se conectar a um servidor que não fornece arquivos [!DNL .zbin] específicos ao idioma, o Data Workbench continuará a usar esse arquivo.

   O arquivo de backup [!DNL insight.zbin] pode ser fornecido em qualquer idioma. Como resultado, se você usar o Data Workbench em chinês e se conectar a um servidor que não oferece suporte a esse idioma, o cliente do Data Workbench ainda estará em chinês, mesmo que o servidor altere seu perfil básico e remova seus arquivos [!DNL .zbin] da pasta [!DNL Base/Localization].

1. **Atualize o servidor de relatório do Data Workbench.** O  [!DNL insight.zbin] na pasta raiz do servidor de relatório do Data Workbench estará em inglês por padrão. Como administrador, você deverá selecionar e copiar o arquivo [!DNL .zbin] do pacote do servidor de relatório atualizado e colocá-lo no diretório raiz do servidor de relatório do Data Workbench. Como o cliente, o servidor de relatórios também requer os argumentos adequados para o idioma selecionado, como [!DNL Insight.exe -zh-cn]

   1. Pare os serviços do servidor de relatórios.
   1. Copie a pasta [!DNL Localization] do novo pacote do servidor de relatório.
   1. Na pasta [!DNL Localization] , copie o arquivo [!DNL Insight.zbin] e o coloque no diretório raiz do servidor de relatórios, onde [!DNL Insight.exe] está localizado.

   1. Adicione quaisquer argumentos necessários, como [!DNL insight.exe -zh-cn]
   1. Reinicie o servidor de relatórios.

## Atualizar o cliente do Data Workbench {#section-9653d3fcaf2a4337a97b685857e7aeac}

Após atualizar o servidor, siga estas etapas para atualizar cada cliente.

1. Para garantir que o cliente não seja atualizado do servidor durante essa atualização, defina o argumento [!DNL Insight.cfg] como Falso.

   ```
   Update Software = bool: false
   ```

1. Reinicie o cliente.
1. Navegue até o perfil Software and Docs (perfil SoftDocs) e baixe o arquivo **[!UICONTROL insight.zbin]** necessário do pacote do cliente: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Mova o arquivo [!DNL insight.zbin] para a pasta onde [!DNL insight.exe] está localizado.

1. Para garantir que os arquivos cliente agora sejam atualizados a partir do servidor, altere o argumento de arquivo [!DNL Insight.cfg] para True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Seu cliente sincronizará com o servidor e você verá uma mensagem informando que está atualizando. No final do download, você receberá uma mensagem perguntando se deseja reiniciar o cliente.

1. Clique em **OK** para reiniciar o cliente.

Se você receber a mensagem a seguir, significa que o arquivo [!DNL zbin] não foi colocado no mesmo local que o [!DNL Insight.exe].

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
