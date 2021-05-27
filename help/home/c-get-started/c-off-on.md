---
description: Informações sobre como trabalhar com o servidor do Data Workbench offline ou online.
title: Trabalhar offline e online
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# Trabalhar offline e online{#working-offline-and-online}

Informações sobre como trabalhar com o servidor do Data Workbench offline ou online.

O Data Workbench baixa automaticamente as atualizações no perfil e seus dados do servidor do Data Workbench se você tiver uma conexão de rede com o [!DNL server] e estiver trabalhando online. Se você não tiver especificado para trabalhar online, o Data Workbench carregará o perfil e seus dados do cache do seu computador. Nesse caso, você está visualizando a versão do perfil e seus dados baixados na última vez que trabalhou online com o perfil.

Trabalhar offline oferece uma vantagem de velocidade de processamento porque você está trabalhando a partir do cache local e consultando os dados em seu próprio computador. Ao trabalhar online, cada query deve retornar ao servidor do Data Workbench, que leva mais tempo e força você a competir com outros usuários online por recursos do servidor. Desde que tenha uma conexão de rede com o servidor do Data Workbench, trabalhar offline impede que o servidor do Data Workbench atualize os perfis ou dados na Data Workbench, mas não impede que você salve itens no servidor do Data Workbench.

Devido à capacidade de trabalhar offline, o servidor do Data Workbench é dimensionado para lidar com uma quantidade de entrada de tráfego em tempo real e com uma quantidade de dados no conjunto de dados, juntamente com um número maior de usuários do Data Workbench, mas não precisa ser dimensionado para suportar o número máximo de usuários simultâneos (o que na prática não acontece com frequência). Como os usuários geralmente procuram tendências e taxas, explorando os dados durante o processo, na maioria dos casos você não precisa de contagens exatas. Se houver a necessidade de consultar e resolver contagens exatas usando os dados atuais, você pode trabalhar online e obtê-las, mas as consultas demoram mais para serem resolvidas em 100%.

**Para trabalhar online ou offline**

Na barra lateral, clique na configuração **[!UICONTROL Connection]** e clique em **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Quando você trabalha online, o Data Workbench se conecta ao servidor do Data Workbench e sincroniza as informações em sua máquina com o perfil e as informações do conjunto de dados que residem no servidor do Data Workbench.

A configuração padrão do Data Workbench é trabalhar offline, mas, conforme descrito na seção a seguir, cada usuário pode alterar seu arquivo [!DNL Insight.cfg] para que sua instância do Data Workbench funcione online por padrão.

**Para trabalhar online por padrão**

1. Navegue até o diretório de instalação do Insight .
1. Abra o arquivo [!DNL Insight.cfg] em um editor de texto.
1. Adicione a linha realçada ao arquivo, conforme mostrado no exemplo a seguir:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

Na próxima vez que você abrir o Data Workbench, ele se conectará ao servidor do Data Workbench e funcionará online por padrão.
