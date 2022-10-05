---
description: Etapas para disponibilizar uma camada de vetor para exibição na visualização de globo.
title: Disponibilizar uma nova camada de vetor
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 6%

---

# Disponibilizar uma nova camada de vetor{#making-a-new-vector-layer-available}

{{eol}}

Etapas para disponibilizar uma camada de vetor para exibição na visualização de globo.

1. Na pasta Profiles\*profile name*\Maps no diretório de instalação do servidor do Data Workbench, coloque o arquivo de camada e o [!DNL .vec] ou [!DNL .tsv] arquivos.
1. Edite o [!DNL order.txt] na pasta Profiles\*profile name*\Maps para refletir a ordem em que deseja que as camadas sejam exibidas. Por padrão, as camadas são exibidas em ordem lexicográfica pelos nomes.

   >[!NOTE]
   >
   >Ao editar o [!DNL order.txt] , certifique-se de não ocultar as camadas do mapa que deseja mostrar.

   Para obter mais informações sobre como usar [!DNL order.txt] arquivos, consulte o capítulo Configuração da interface e recursos de análise *Guia do usuário do Data Workbench*.

1. No Data Workbench, selecione o perfil desejado clicando com o botão direito do mouse na barra de título do espaço de trabalho e clicando em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Work Online]**. Um X é exibido ao lado de [!DNL Work Online].
1. Abra um espaço de trabalho e, em uma visualização de globo, clique com o botão direito do mouse e selecione a nova camada. Um X é exibido ao lado do nome da camada.
