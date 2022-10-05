---
description: O Data Workbench agora é compatível com o Editor de método de entrada (IME) como um processo de entrada de texto secundário para idiomas internacionais.
title: Instalação do editor de método de entrada
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# Instalação do editor de método de entrada{#installing-the-input-method-editor}

{{eol}}

O Data Workbench agora é compatível com o Editor de método de entrada (IME) como um processo de entrada de texto secundário para idiomas internacionais.

Os IMEs permitem inserir caracteres internacionais usando uma variedade de métodos adequados para o seu idioma local. O Data Workbench fornece uma caixa de diálogo de entrada que permite abrir e usar o IME desejado para campos de texto.

>[!NOTE]
>
>Para a versão do Data Workbench 6.1, somente o teclado chinês simplificado virtual será suportado. Inserir outros idiomas pelo IME pode resultar em um comportamento inesperado.

## Uso de um IME {#section-5f008d75a7b24119ab6aebc55454f927}

Para usar o recurso de entrada de texto IME flutuante:

1. Clique em **[!UICONTROL Alt + Space]** para qualquer área de entrada de texto.
1. Insira valores usando o IME do sistema.
1. Feche a caixa de diálogo de entrada selecionando o **[!UICONTROL Enter]** ou clicar no botão **[!UICONTROL OK]** botão.

   A caixa de diálogo desaparecerá e os caracteres aparecerão no campo selecionado.

**Atualização do arquivo Insight.cfg**

Para usar o IME, você deve atualizar o [!DNL Insight.cfg] com esta configuração:

```
Localized IME = bool: true
```

Se essa configuração não existir no arquivo de configuração, pressione **[!UICONTROL Alt + Space]** O não interage com o recurso IME.

**Iniciar o Insight em outro idioma:** Para oferecer suporte melhor a ativos localizados, como uma tela inicial, e para oferecer suporte a vários idiomas no futuro, o Data Workbench requer argumentos de linha de comando que identifiquem o idioma a ser carregado. O idioma padrão é inglês.

Iniciar o Data Workbench em chinês requer que você chame [!DNL Insight.exe] com o argumento &quot;-zh-cn&quot;:

```
Insight.exe -zh-cn
```

(Esses argumentos de linha de comando não diferenciam maiúsculas de minúsculas.)
