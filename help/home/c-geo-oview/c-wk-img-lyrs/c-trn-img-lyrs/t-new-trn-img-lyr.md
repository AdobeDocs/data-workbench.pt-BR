---
description: Etapas para tornar uma nova camada de terreno disponível para exibição na visualização do globo.
solution: Analytics
title: Disponibilização de uma nova camada de imagem de terreno
topic: Data workbench
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Disponibilização de uma nova camada de imagem de terreno{#making-a-new-terrain-image-layer-available}

Etapas para tornar uma nova camada de terreno disponível para exibição na visualização do globo.

1. Na pasta Perfis\*nome do perfil*\Maps no diretório de **[!UICONTROL Insight Server]** instalação, coloque o arquivo de camada e os arquivos de imagem de suporte.
1. Edite o [!DNL order.txt] arquivo na pasta Perfis\*nome do perfil*\Mapas para refletir a ordem em que deseja que as camadas sejam exibidas. Por padrão, as camadas são exibidas em ordem lexicográfica pelos nomes.

   >[!NOTE]
   >
   >Ao editar o [!DNL order.txt] arquivo, tenha cuidado para não ocultar as camadas do mapa que você deseja mostrar.

   Para obter mais informações sobre o uso de [!DNL order.txt] arquivos, consulte o capítulo Configuração de recursos de interface e análise do Guia *do Usuário do* Análise de big data.

1. Na análise de big data, selecione o perfil desejado clicando com o botão direito do mouse na barra de título da área de trabalho e clicando em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Work Online]**. Um X é exibido ao lado de [!DNL Work Online].
1. Abra um espaço de trabalho e, em uma visualização de globo, clique com o botão direito do mouse e selecione a nova camada. Um X é exibido ao lado do nome da camada.
