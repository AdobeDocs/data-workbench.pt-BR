---
description: O parâmetro ExpFile aponta para o local do arquivo de configuração do experimento, que define seu experimento.
solution: Analytics,Analytics
title: Modificar o parâmetro ExpFile
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# Modificar o parâmetro ExpFile{#modifying-the-expfile-parameter}

O parâmetro ExpFile aponta para o local do arquivo de configuração do experimento, que define seu experimento.

Configurar esse parâmetro permite executar experimentos. Para obter etapas para criar o arquivo de configuração do experimento, consulte [Configuração e Implantação do Experimento](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

A seguir, um exemplo do parâmetro ExpFile :

```
ExpFile /home/experiment.txt
```

Esse arquivo de texto delimitado por tabulação ( [!DNL .txt]) pode ser localizado em qualquer lugar na pasta [!DNL Sensor] e pode ter qualquer nome conveniente.

Certifique-se de registrar o local do diretório experimentos e o nome do arquivo de configuração especificado, pois é necessário salvar o arquivo de configuração do experimento (a ser descrito posteriormente neste guia) usando esse nome e nesse diretório.

>[!NOTE]
>
>Se você não definir esse parâmetro de forma idêntica em cada máquina do cluster da Web em que [!DNL Sensor] está instalado, a experimentação controlada não funcionará.

Essa entrada pode ser pré-configurada e permanecer no arquivo de configuração [!DNL Sensor] de forma contínua, sem efeito adverso. Se o nome do arquivo de configuração de experimento especificado não for encontrado por [!DNL Sensor] ou estiver em branco (ou seja, ele existe, mas não tem conteúdo), [!DNL Sensor] não conduzirá o experimento, registrará um evento de erro no servidor HTTP e continuará a operar normalmente em todos os outros aspectos.
