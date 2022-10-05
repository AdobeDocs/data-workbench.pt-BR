---
description: O parâmetro ExpFile aponta para o local do arquivo de configuração do experimento, que define seu experimento.
solution: Analytics
title: Modificar o parâmetro ExpFile
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# Modificar o parâmetro ExpFile{#modifying-the-expfile-parameter}

{{eol}}

O parâmetro ExpFile aponta para o local do arquivo de configuração do experimento, que define seu experimento.

Configurar esse parâmetro permite executar experimentos. Para obter as etapas para criar o arquivo de configuração de experimento, consulte [Configurar e implantar o experimento](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

A seguir, um exemplo do parâmetro ExpFile :

```
ExpFile /home/experiment.txt
```

Arquivo de texto delimitado por tabulação ( [!DNL .txt]) pode ser localizada em qualquer lugar da variável [!DNL Sensor] e pode ter qualquer nome conveniente.

Certifique-se de registrar o local do diretório experimentos e o nome do arquivo de configuração especificado, pois é necessário salvar o arquivo de configuração do experimento (a ser descrito posteriormente neste guia) usando esse nome e nesse diretório.

>[!NOTE]
>
>Se você não definir esse parâmetro de forma idêntica em cada máquina do cluster da Web em que um [!DNL Sensor] estiver instalado, a experimentação controlada não funcionará.

Essa entrada pode ser pré-configurada e permanecer no [!DNL Sensor] arquivo de configuração de forma contínua, sem efeito adverso. Se o nome do arquivo de configuração de experimento especificado não for encontrado por [!DNL Sensor] ou está em branco (ou seja, existe, mas não tem conteúdo), [!DNL Sensor] não realiza o experimento, registra um evento de erro no servidor HTTP e continua a operar normalmente em todos os outros aspectos.
