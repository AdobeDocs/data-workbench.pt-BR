---
description: Instruções para atualizar o Repetidor usando o Insight ou para atualizar copiando arquivos.
solution: Analytics
title: Atualizar o repetidor
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# Atualizar o repetidor{#upgrading-repeater}

Instruções para atualizar o Repetidor usando o Insight ou para atualizar copiando arquivos.

Você pode usar um dos seguintes métodos para atualizar [!DNL Repeater] da Plataforma 4.x ou posterior:

* Se você tiver criado uma conexão entre [!DNL Insight] e [!DNL Repeater] , conforme descrito em [Criando uma conexão entre o Insight e o Repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), poderá usar [!DNL Insight] para atualizar [!DNL Repeater]. Consulte [Atualizando o repetidor usando o Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -ou-

* Se você não pôde ou não criou uma conexão entre [!DNL Insight] e [!DNL Repeater], é necessário copiar os arquivos de atualização diretamente para a [!DNL Repeater] máquina. Consulte [Atualizando o repetidor copiando arquivos](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Atualizando o repetidor usando o Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. No [!DNL Insight] computador, copie a [!DNL bin] pasta do pacote de [!DNL Insight Server] atualização para a [!DNL Temp] pasta no diretório onde [!DNL Insight] está instalada.
1. Início [!DNL Insight].
1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile] , clique na **[!UICONTROL Servers Manager]** miniatura para abrir a área de trabalho do Gerenciador de servidores.
1. Clique com o botão direito do mouse no ícone do aplicativo [!DNL Repeater] que deseja atualizar e clique em **[!UICONTROL Server Files]**.
1. Na página [!DNL Server Files Manager], faça o seguinte para fazer upload dos arquivos de atualização para o servidor:

   1. Localize a [!DNL bin] pasta.
   1. Clique com o botão direito do mouse na marca de seleção da [!DNL bin] pasta no diretório Temp e selecione **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Você verá uma mensagem indicando que essa etapa substitui arquivos com o mesmo nome existentes no servidor. Click **[!UICONTROL Yes]** to continue.

>[!NOTE]
>
>Se você precisar carregar arquivos adicionais para concluir a [!DNL Repeater] atualização, o Adobe fornecerá instruções para isso.

Depois de fazer upload dos arquivos de atualização para o [!DNL Repeater] computador, [!DNL Repeater] reinicia automaticamente e carrega a nova versão.

## Atualizando o repetidor copiando arquivos {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Abra o arquivo de atualização fornecido pelo Adobe. Provavelmente, este arquivo é um [!DNL .zip] arquivo para atualização [!DNL Insight Server].
1. Vá para o diretório onde você instalou [!DNL Repeater] (por exemplo, [!DNL D:\Adobe\Repeater]).
1. Copie a [!DNL bin] pasta dentro do [!DNL .zip] arquivo e cole-a no diretório [!DNL Repeater] de instalação para substituir a [!DNL bin] pasta existente.

>[!NOTE]
>
>Se você precisar carregar arquivos adicionais para concluir a [!DNL Insight Server] atualização, o Adobe fornecerá instruções para isso.

Depois de copiar os arquivos de atualização para a [!DNL Repeater] máquina, [!DNL Repeater] reinicia automaticamente e carrega a nova versão.
