---
description: Etapas para disponibilizar qualquer camada vetorial para exibição na visualização global.
solution: Analytics
title: Disponibilizar uma nova camada de vetor
topic: Data workbench
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Disponibilizar uma nova camada de vetor{#make-a-new-vector-layer-available}

Etapas para disponibilizar qualquer camada vetorial para exibição na visualização global.

1. Na pasta Perfis\*nome do perfil*\Maps no diretório de instalação do servidor Análise de big data, coloque o arquivo de camada e os [!DNL .vec] arquivos ou [!DNL .tsv] arquivos.
1. Edite o [!DNL order.txt] arquivo na pasta Perfis\*nome do perfil*\Mapas para refletir a ordem em que deseja que as camadas sejam exibidas. Por padrão, as camadas são exibidas em ordem lexicográfica pelos nomes.

   >[!NOTE]
   >
   >Ao editar o [!DNL order.txt] arquivo, tenha cuidado para não ocultar as camadas do mapa que você deseja mostrar.

   Para obter mais informações sobre como usar [!DNL order.txt] arquivos, consulte [Personalizar menus usando arquivos](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

1. No Insight, selecione o perfil desejado clicando com o botão direito do mouse na barra de título do espaço de trabalho e clicando em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Work Online]**. Um X é exibido ao lado de Work Online.
1. Abra um espaço de trabalho e, em uma visualização de globo, clique com o botão direito do mouse e selecione a nova camada. Um X é exibido ao lado do nome da camada.
