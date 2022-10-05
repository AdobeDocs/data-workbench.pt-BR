---
description: Etapas para disponibilizar qualquer camada de terreno para exibição na visualização de globo.
title: Disponibilizar uma nova camada de imagem do terreno
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 7%

---

# Disponibilizar uma nova camada de imagem do terreno{#make-a-new-terrain-image-layer-available}

{{eol}}

Etapas para disponibilizar qualquer camada de terreno para exibição na visualização de globo.

1. Na pasta Profiles\*profile name*\Maps no diretório de instalação do servidor do Data Workbench, coloque o arquivo de camada e os arquivos de imagem de suporte.
1. Edite o [!DNL order.txt] na pasta Profiles\*profile name*\Maps para refletir a ordem em que deseja que as camadas sejam exibidas. Por padrão, as camadas são exibidas em ordem lexicográfica pelos nomes.

   >[!NOTE]
   >
   >Ao editar o [!DNL order.txt] , certifique-se de não ocultar as camadas do mapa que deseja mostrar.

   Para obter mais informações sobre como usar [!DNL order.txt] arquivos, consulte o capítulo Configuração da interface e recursos de análise *Guia do usuário do Data Workbench*.

1. Em Data Workbench, selecione o perfil desejado clicando com o botão direito do mouse na barra de título do espaço de trabalho e clicando em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Work Online]**. Um X é exibido ao lado de Trabalhar online.
1. Abra um espaço de trabalho e, em uma visualização de globo, clique com o botão direito do mouse e selecione a nova camada. Um X é exibido ao lado do nome da camada.
