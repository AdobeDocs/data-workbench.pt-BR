---
description: A análise de big data agora oferece suporte ao Editor de método de entrada (IME) como um processo de entrada de texto secundário para idiomas internacionais.
solution: Analytics
title: Instalação do editor de método de entrada
topic: Data workbench
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalação do editor de método de entrada{#installing-the-input-method-editor}

A análise de big data agora oferece suporte ao Editor de método de entrada (IME) como um processo de entrada de texto secundário para idiomas internacionais.

Os IMEs permitem que você insira caracteres internacionais usando uma variedade de métodos adequados ao seu idioma local. A análise de big data fornece uma caixa de diálogo de entrada que permite abrir e usar o IME desejado para campos de texto.

>[!NOTE]
>
>Na versão 6.1 da análise de big data, somente o teclado virtual chinês simplificado será suportado. A inserção de outros idiomas no IME pode resultar em comportamento inesperado.

## Uso de um IME {#section-5f008d75a7b24119ab6aebc55454f927}

Para usar o recurso de entrada de texto IME flutuante:

1. Clique em **[!UICONTROL Alt + Space]** qualquer área de entrada de texto.
1. Insira valores usando o IME do seu sistema.
1. Feche a caixa de diálogo de entrada selecionando a **[!UICONTROL Enter]** tecla ou clicando no **[!UICONTROL OK]** botão.

   A caixa de diálogo desaparecerá e os caracteres aparecerão no campo selecionado.

**Atualização do arquivo Insight.cfg**

Para usar o IME, atualize o [!DNL Insight.cfg] arquivo com esta configuração:

```
Localized IME = bool: true
```

Se essa configuração não existir no arquivo de configuração, então pressionar não **[!UICONTROL Alt + Space]** interagirá com o recurso IME.

**Iniciando o Insight em outro idioma:** Para suportar melhor ativos localizados, como uma tela de apresentação, e para suportar vários idiomas no futuro, a análise de big data requer argumentos de linha de comando que identifiquem o idioma a ser carregado. O idioma padrão é o inglês.

Iniciar análise de big data em chinês requer que você chame [!DNL Insight.exe] com o argumento &quot;-zh-cn&quot;:

```
Insight.exe -zh-cn
```

(Esses argumentos de linha de comando não distinguem maiúsculas de minúsculas.)
