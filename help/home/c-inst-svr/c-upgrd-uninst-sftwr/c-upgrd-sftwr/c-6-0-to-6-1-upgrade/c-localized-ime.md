---
description: O Data Workbench agora é compatível com o Editor de método de entrada (IME) como um processo de entrada de texto secundário para idiomas internacionais.
title: Instalação do editor de método de entrada
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56,0bdc7d95-b49a-4ca5-9fde-9c1ce2cd14ec,e4e1c016-0544-434a-b82e-fdd2a4af316c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# Instalação do editor de método de entrada{#installing-the-input-method-editor}

O Data Workbench agora é compatível com o Editor de método de entrada (IME) como um processo de entrada de texto secundário para idiomas internacionais.

Os IMEs permitem inserir caracteres internacionais usando uma variedade de métodos adequados para o seu idioma local. O Data Workbench fornece uma caixa de diálogo de entrada que permite abrir e usar o IME desejado para campos de texto.

>[!NOTE]
>
>Para a versão do Data Workbench 6.1, somente o teclado chinês simplificado virtual será suportado. Inserir outros idiomas pelo IME pode resultar em um comportamento inesperado.

## Uso de um IME {#section-5f008d75a7b24119ab6aebc55454f927}

Para usar o recurso de entrada de texto IME flutuante:

1. Clique em **[!UICONTROL Alt + Space]** para qualquer área de entrada de texto.
1. Insira valores usando o IME do sistema.
1. Feche a caixa de diálogo de entrada selecionando a tecla **[!UICONTROL Enter]** ou clicando no botão **[!UICONTROL OK]**.

   A caixa de diálogo desaparecerá e os caracteres aparecerão no campo selecionado.

**Atualização do arquivo Insight.cfg**

Para usar o IME, você deve atualizar o arquivo [!DNL Insight.cfg] com esta configuração:

```
Localized IME = bool: true
```

Se essa configuração não existir no arquivo de configuração, pressionar **[!UICONTROL Alt + Space]** não engajará o recurso IME.

**Iniciar o Insight em outro idioma:** para oferecer melhor suporte a ativos localizados, como uma tela inicial e para oferecer suporte a vários idiomas no futuro, o Data Workbench requer argumentos de linha de comando que identifiquem o idioma a ser carregado. O idioma padrão é inglês.

Iniciar o Data Workbench em chinês requer que você chame [!DNL Insight.exe] com o argumento &quot;-zh-cn&quot;:

```
Insight.exe -zh-cn
```

(Esses argumentos de linha de comando não diferenciam maiúsculas de minúsculas.)
