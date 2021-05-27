---
description: Etapas para disponibilizar uma nova camada de terreno para exibição na visualização de globo.
title: Disponibilizar uma nova camada de imagem do terreno
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 7%

---

# Disponibilizar uma nova camada de imagem do terreno{#making-a-new-terrain-image-layer-available}

Etapas para disponibilizar uma nova camada de terreno para exibição na visualização de globo.

1. Na pasta Profiles\*profile name*\Maps no diretório de instalação **[!UICONTROL Insight Server]**, coloque o arquivo de camada e os arquivos de imagem de suporte.
1. Edite o arquivo [!DNL order.txt] na pasta Perfis\*nome do perfil*\Mapas para refletir a ordem em que deseja que as camadas sejam exibidas. Por padrão, as camadas são exibidas em ordem lexicográfica pelos nomes.

   >[!NOTE]
   >
   >Ao editar o arquivo [!DNL order.txt], não cubra as camadas de mapa que deseja mostrar.

   Para obter mais informações sobre o uso de arquivos [!DNL order.txt], consulte o capítulo Configuração de recursos de interface e análise do *Guia do usuário do Data Workbench*.

1. No Data Workbench, selecione o perfil desejado clicando com o botão direito do mouse na barra de título do espaço de trabalho e clicando em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Work Online]**. Um X é exibido ao lado de [!DNL Work Online].
1. Abra um espaço de trabalho e, em uma visualização de globo, clique com o botão direito do mouse e selecione a nova camada. Um X é exibido ao lado do nome da camada.
