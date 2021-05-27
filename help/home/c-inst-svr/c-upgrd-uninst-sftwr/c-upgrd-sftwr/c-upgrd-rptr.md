---
description: Instruções para atualizar o Repetidor usando o Insight ou para atualizar copiando arquivos.
title: Atualizar o repetidor
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Atualizar o repetidor{#upgrading-repeater}

Instruções para atualizar o Repetidor usando o Insight ou para atualizar copiando arquivos.

Você pode usar um dos seguintes métodos para atualizar [!DNL Repeater] da Plataforma 4.x ou posterior:

* Se você criou uma conexão entre [!DNL Insight] e [!DNL Repeater] conforme descrito em [Criando uma conexão entre o Insight e o Repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), você pode usar [!DNL Insight] para atualizar [!DNL Repeater]. Consulte [Atualizando Repetidor Usando Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -ou-

* Se você não conseguiu ou não criou uma conexão entre [!DNL Insight] e [!DNL Repeater], deve copiar os arquivos de atualização diretamente para a máquina [!DNL Repeater]. Consulte [Atualizando repetidor copiando arquivos](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Atualizar o repetidor usando o Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. No computador [!DNL Insight], copie a pasta [!DNL bin] do pacote de atualização [!DNL Insight Server] para a pasta [!DNL Temp] no diretório onde [!DNL Insight] está instalado.
1. Início [!DNL Insight].
1. Em [!DNL Insight], na guia [!DNL Admin] > [!DNL Dataset and Profile], clique na miniatura **[!UICONTROL Servers Manager]** para abrir o espaço de trabalho do Gerenciador de Servidores.
1. Clique com o botão direito do mouse no ícone do [!DNL Repeater] que deseja atualizar e clique em **[!UICONTROL Server Files]**.
1. No [!DNL Server Files Manager], faça o seguinte para carregar os arquivos de atualização no servidor:

   1. Localize a pasta [!DNL bin].
   1. Clique com o botão direito do mouse na marca de seleção da pasta [!DNL bin] no diretório Temp e selecione **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]***.

>[!NOTE]
>
>Você verá uma mensagem indicando que essa etapa substitui arquivos com o mesmo nome existentes no servidor. Clique em **[!UICONTROL Yes]** para continuar.

>[!NOTE]
>
>Se você precisar carregar arquivos adicionais para concluir a atualização [!DNL Repeater], o Adobe fornecerá instruções para isso.

Depois de fazer upload dos arquivos de atualização para a máquina [!DNL Repeater], [!DNL Repeater] reinicia automaticamente e carrega a nova versão.

## Atualizar o repetidor copiando arquivos {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Abra o arquivo de atualização fornecido pelo Adobe. Provavelmente, esse arquivo é um arquivo [!DNL .zip] para atualização [!DNL Insight Server].
1. Vá para o diretório onde você instalou [!DNL Repeater] (por exemplo, [!DNL D:\Adobe\Repeater]).
1. Copie a pasta [!DNL bin] no arquivo [!DNL .zip] e cole-a no diretório de instalação [!DNL Repeater] para substituir a pasta [!DNL bin] existente.

>[!NOTE]
>
>Se você precisar carregar arquivos adicionais para concluir a atualização [!DNL Insight Server], o Adobe fornecerá instruções para isso.

Depois de copiar os arquivos de atualização para a máquina [!DNL Repeater], [!DNL Repeater] reinicia automaticamente e carrega a nova versão.
