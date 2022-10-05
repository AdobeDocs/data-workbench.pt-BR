---
description: Instruções para atualizar o Repetidor usando o Insight ou para atualizar copiando arquivos.
title: Atualizar o repetidor
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Atualizar o repetidor{#upgrading-repeater}

{{eol}}

Instruções para atualizar o Repetidor usando o Insight ou para atualizar copiando arquivos.

Você pode usar um dos seguintes métodos para atualizar [!DNL Repeater] da plataforma 4.x ou posterior:

* Se você criou uma conexão entre [!DNL Insight] e [!DNL Repeater] conforme descrito em [Criar uma conexão entre o Insight e o Repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), você pode usar [!DNL Insight] para atualizar [!DNL Repeater]. Consulte [Atualizar o repetidor usando o Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -ou-

* Se você não conseguiu ou não criou uma conexão entre [!DNL Insight] e [!DNL Repeater], você deve copiar os arquivos de atualização diretamente para o [!DNL Repeater] máquina. Consulte [Atualizar o repetidor copiando arquivos](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Atualizar o repetidor usando o Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. No [!DNL Insight] computador, copie o [!DNL bin] da pasta de [!DNL Insight Server] atualizar pacote para o [!DNL Temp] no diretório em que [!DNL Insight] está instalado.
1. Iniciar [!DNL Insight].
1. Em [!DNL Insight], no [!DNL Admin] > [!DNL Dataset and Profile] clique no botão **[!UICONTROL Servers Manager]** miniatura para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Repeater] você deseja atualizar e clicar em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], faça o seguinte para carregar os arquivos de atualização no servidor:

   1. Localize a variável [!DNL bin] pasta.
   1. Clique com o botão direito do mouse na marca de seleção para a [!DNL bin] no diretório Temp e selecione **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Você verá uma mensagem indicando que essa etapa substitui arquivos com o mesmo nome existentes no servidor. Clique em **[!UICONTROL Yes]** para continuar.

>[!NOTE]
>
>Se precisar fazer upload de arquivos adicionais para concluir a [!DNL Repeater] atualizar, o Adobe fornecerá instruções para isso.

Após fazer upload dos arquivos de atualização para a [!DNL Repeater] máquina, [!DNL Repeater] automaticamente se reinicia e carrega a nova versão.

## Atualizar o repetidor copiando arquivos {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Abra o arquivo de atualização fornecido pelo Adobe. Provavelmente, esse arquivo é um [!DNL .zip] arquivo para atualização [!DNL Insight Server].
1. Vá para o diretório onde você instalou o [!DNL Repeater] (por exemplo, [!DNL D:\Adobe\Repeater]).
1. Copie o [!DNL bin] na pasta [!DNL .zip] e cole-o em seu [!DNL Repeater] diretório de instalação para substituir o existente [!DNL bin] pasta.

>[!NOTE]
>
>Se precisar fazer upload de arquivos adicionais para concluir a [!DNL Insight Server] atualizar, o Adobe fornecerá instruções para isso.

Depois de copiar os arquivos de atualização para a [!DNL Repeater] máquina, [!DNL Repeater] automaticamente se reinicia e carrega a nova versão.
