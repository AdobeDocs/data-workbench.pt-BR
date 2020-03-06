---
description: Etapas para tornar qualquer camada de ponto de elemento disponível para exibição na visualização global.
solution: Analytics
title: Disponibilizar uma nova camada de ponto de elemento
topic: Data workbench
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Disponibilizar uma nova camada de ponto de elemento{#make-a-new-element-point-layer-available}

Etapas para tornar qualquer camada de ponto de elemento disponível para exibição na visualização global.

1. Na pasta Perfis\*nome do perfil*\Maps no diretório de instalação do servidor Análise de big data, coloque o arquivo de camada e o arquivo de pesquisa relacionado.
1. Se você tiver definido uma nova dimensão para a camada do ponto do elemento e ainda não tiver retransformado seu conjunto de dados, retransforme seu conjunto de dados agora.
1. Edite o [!DNL order.txt] arquivo na pasta Perfis\*nome do perfil*\Mapas para refletir a ordem em que deseja que as camadas sejam exibidas. Por padrão, as camadas são exibidas em ordem lexicográfica pelos nomes.

   >[!NOTE]
   >
   >Ao editar o [!DNL order.txt] arquivo, tenha cuidado para não ocultar as camadas do mapa que você deseja mostrar.

   Para obter mais informações sobre o uso de [!DNL order.txt] arquivos, consulte o capítulo Configuração de recursos de interface e análise do Guia *do Usuário do* Análise de big data.

1. Na Análise de big data, selecione o perfil desejado clicando com o botão direito do mouse na barra de título da área de trabalho e clicando em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Work Online]**. Um X é exibido ao lado de Work Online.
1. Abra um espaço de trabalho e, em uma visualização de globo, clique com o botão direito do mouse e selecione a nova camada. Um X é exibido ao lado do nome da camada.
