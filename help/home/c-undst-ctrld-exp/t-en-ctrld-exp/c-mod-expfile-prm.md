---
description: O parâmetro ExpFile aponta para o local do arquivo de configuração do experimento, que define seu experimento.
solution: Analytics,Analytics
title: Modificar o parâmetro ExpFile
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---


# Modificar o parâmetro ExpFile{#modifying-the-expfile-parameter}

O parâmetro ExpFile aponta para o local do arquivo de configuração do experimento, que define seu experimento.

A definição desse parâmetro permite que você execute experiências. Para obter etapas para criar o arquivo de configuração do experimento, consulte [Configuração e implantação do Experimento](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Veja a seguir um exemplo do parâmetro ExpFile:

```
ExpFile /home/experiment.txt
```

Esse arquivo de texto delimitado por tabulação ( [!DNL .txt]) pode ser localizado em qualquer lugar na [!DNL Sensor] pasta e pode ter qualquer nome conveniente.

Certifique-se de gravar o local do diretório de experiências e o nome do arquivo de configuração especificado, pois é necessário salvar o arquivo de configuração do experimento (a ser descrito posteriormente neste guia) usando esse nome e esse diretório.

>[!NOTE]
>
>Se você não definir esse parâmetro de forma idêntica em cada máquina do cluster da Web em que um computador [!DNL Sensor] está instalado, a experimentação controlada não funcionará.

Essa entrada pode ser pré-configurada e permanecer no arquivo de [!DNL Sensor] configuração continuamente, sem nenhum efeito adverso. Se o nome do arquivo de configuração do experimento especificado não for encontrado por [!DNL Sensor] ou estiver em branco (isto é, ele existe mas não tem conteúdo), [!DNL Sensor] não realizar o experimento, registrará um evento de erro no servidor HTTP e continuará a operar normalmente em todos os outros aspectos.
