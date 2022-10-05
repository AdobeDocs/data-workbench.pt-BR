---
description: O Data Workbench baixa perfis em sua máquina.
title: Perfis
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Perfis{#profiles}

{{eol}}

O Data Workbench baixa perfis em sua máquina.

Se você estiver carregando um perfil pela primeira vez, é necessário ter uma conexão de rede com o [!DNL Data Workbench server] e trabalhar online para que o Data Workbench possa baixar os arquivos necessários da [!DNL Data Workbench server].

O download do perfil pode levar alguns minutos. Você não deve começar a trabalhar com o perfil até que o Cache de dados comece a preencher, mas não precisa aguardar até que ele esteja cheio. Você pode acompanhar o progresso do cache de dados, o progresso da sincronização de perfis e a data e hora dos dados processados mais recentemente, observando as barras de status à medida que o perfil é carregado.

>[!NOTE]
>
>Você não vê dados em visualizações que adiciona até que o cache de dados comece a preencher.

Na próxima vez que você carregar o perfil, as atualizações do perfil e seus dados serão baixados somente se você tiver uma conexão de rede com o [!DNL Data Workbench server] e estão trabalhando online. Se você estiver trabalhando offline, o perfil e seus dados serão carregados do cache do computador. Nesse caso, você está visualizando a versão do perfil e os dados que foram baixados na última vez que você trabalhou online com o perfil. Para obter mais informações sobre como trabalhar online ou offline, consulte [Trabalhar offline e online](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

Quando precisar alterar o perfil (usando a variável [!DNL Profile Manager] ou [!DNL Server Files Manager]), você deve trabalhar online para garantir que tenha a versão mais atualizada do perfil. Para obter mais informações sobre o [!DNL Profile Manager] e [!DNL Server Files Manager], consulte [Interfaces administrativas](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Se não conseguir acessar ou carregar um perfil, talvez seja necessário confirmar o seguinte:

* Você tem uma conexão de rede com o [!DNL Data Workbench server] máquina na qual o perfil reside.
* Você tem as permissões apropriadas para acessar o perfil.

Para obter ajuda, entre em contato com o administrador do sistema.

## Carregamento ou troca de perfis {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Inicie o Data Workbench.
1. Na barra lateral, clique no nome do perfil e clique em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, onde *nome do perfil* é o perfil com o qual você deseja trabalhar.

   ![](assets/sidebar_profile.png)

Se esta for a primeira vez que você carrega o perfil selecionado, pode levar vários minutos para baixar dados suficientes para preencher uma visualização.

## Acesso a um perfil em um cluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench usuários que acessam um perfil em execução em um

O cluster de servidores do Data Workbench identifica somente o Servidor do Data Workbench principal no arquivo de configuração do Data Workbench ( [!DNL Insight.cfg]). Da perspectiva do usuário do Data Workbench, o perfil pode ser acessado em apenas um Servidor do Data Workbench (o Servidor do Data Workbench principal). No entanto, as solicitações de consulta dos analistas podem ser direcionadas para qualquer um dos Servidores de Data Workbench no cluster.

Para obter mais informações sobre perfis em execução em um cluster do Data Workbench Server, consulte *Guia de Instalação e Administração de Produtos para Servidores*.
