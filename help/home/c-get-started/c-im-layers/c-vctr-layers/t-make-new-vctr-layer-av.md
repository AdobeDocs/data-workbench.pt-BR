---
description: Etapas para disponibilizar qualquer camada de vetor para exibir na visualização de globo.
title: Disponibilizar uma nova camada de vetor
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 7%

---

# Disponibilizar uma nova camada de vetor{#make-a-new-vector-layer-available}

Etapas para disponibilizar qualquer camada de vetor para exibir na visualização de globo.

1. Na pasta Profiles\*profile name*\Maps no diretório de instalação do servidor do Data Workbench, coloque o arquivo de camada e os arquivos [!DNL .vec] ou [!DNL .tsv].
1. Edite o arquivo [!DNL order.txt] na pasta Perfis\*nome do perfil*\Mapas para refletir a ordem em que deseja que as camadas sejam exibidas. Por padrão, as camadas são exibidas em ordem lexicográfica pelos nomes.

   >[!NOTE]
   >
   >Ao editar o arquivo [!DNL order.txt], não cubra as camadas de mapa que deseja mostrar.

   Para obter mais informações sobre o uso de arquivos [!DNL order.txt], consulte [Personalização de menus usando arquivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. No Insight, selecione o perfil desejado clicando com o botão direito do mouse na barra de título do espaço de trabalho e clicando em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Work Online]**. Um X é exibido ao lado de Trabalhar online.
1. Abra um espaço de trabalho e, em uma visualização de globo, clique com o botão direito do mouse e selecione a nova camada. Um X é exibido ao lado do nome da camada.
