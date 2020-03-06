---
description: Informações sobre como trabalhar com o servidor da Análise de big data offline ou online.
solution: Analytics
title: Trabalhar offline e online
topic: Data workbench
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trabalhar offline e online{#working-offline-and-online}

Informações sobre como trabalhar com o servidor da Análise de big data offline ou online.

O Análise de big data baixa automaticamente atualizações para o perfil e seus dados do servidor do Análise de big data se você tiver uma conexão de rede com o [!DNL server] e estiver trabalhando on-line. Se você não tiver especificado para trabalhar online, o Análise de big data carregará o perfil e seus dados do cache do computador. Nesse caso, você está visualizando a versão do perfil e seus dados que foram baixados na última vez que você trabalhou online com o perfil.

Trabalhar offline oferece uma vantagem na velocidade de processamento porque você está trabalhando a partir do cache local e consultando os dados em seu próprio computador. Ao trabalhar on-line, cada consulta deve voltar para o servidor do Análise de big data, que demora mais tempo e o força a competir com outros usuários on-line pelos recursos do servidor. Desde que você tenha uma conexão de rede com o servidor da Análise de big data, trabalhar offline impedirá que o servidor da Análise de big data atualize os perfis ou os dados da Análise de big data, mas isso não impede que você salve itens no servidor da Análise de big data.

Devido à capacidade de trabalhar offline, o servidor da Análise de big data é dimensionado para lidar com alguma quantidade de entrada de tráfego em tempo real e alguma quantidade de dados no conjunto de dados, juntamente com alguns usuários da Análise de big data, mas não precisa ser dimensionado para suportar o número máximo de usuários simultâneos (o que na prática não acontece com frequência). Como os usuários geralmente procuram tendências e taxas, explorando os dados à medida que você vai, na maioria dos casos você não precisa de contagens exatas. Se houver necessidade de consultar e resolver contagens exatas usando os dados atuais, você pode trabalhar online e obtê-las, mas as consultas demoram mais para serem resolvidas em 100%.

**Para trabalhar online ou offline**

Na barra lateral, clique na **[!UICONTROL Connection]** configuração e clique em **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Quando você trabalha on-line, o Análise de big data se conecta ao servidor do Análise de big data e sincroniza as informações do computador com o perfil e suas informações do conjunto de dados que residem no servidor do Análise de big data.

A configuração padrão para o Análise de big data é trabalhar offline, mas, conforme descrito na seção a seguir, cada usuário pode alterar seu [!DNL Insight.cfg] arquivo para que sua instância do Análise de big data funcione online por padrão.

**Para trabalhar online por padrão**

1. Navegue até o diretório de instalação do Insight.
1. Abra o [!DNL Insight.cfg] arquivo em um editor de texto.
1. Adicione a linha realçada ao arquivo, como mostrado no exemplo a seguir:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

Na próxima vez que você abrir o Análise de big data, ele se conectará ao servidor do Análise de big data e funcionará on-line por padrão.
