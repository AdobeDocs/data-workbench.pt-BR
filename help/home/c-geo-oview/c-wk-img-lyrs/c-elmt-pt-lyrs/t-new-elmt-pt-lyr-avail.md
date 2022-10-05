---
description: Etapas para disponibilizar uma camada de ponto de elemento para exibição na visualização de globo.
title: Disponibilizar uma nova camada de ponto de elemento
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%

---

# Disponibilizar uma nova camada de ponto de elemento{#making-a-new-element-point-layer-available}

{{eol}}

Etapas para disponibilizar uma camada de ponto de elemento para exibição na visualização de globo.

1. Na pasta Profiles\*profile name*\Maps no diretório de instalação do servidor do Data Workbench, coloque o arquivo de camada e o arquivo de pesquisa relacionado.
1. Se você definiu uma nova dimensão para a camada do ponto de elemento e ainda não retransformou seu conjunto de dados, retransforme seu conjunto de dados agora.
1. Edite o [!DNL order.txt] na pasta Profiles\*profile name*\Maps para refletir a ordem em que deseja que as camadas sejam exibidas. Por padrão, as camadas são exibidas em ordem lexicográfica pelos nomes.

   >[!NOTE]
   >
   >Ao editar o [!DNL order.txt] , certifique-se de não ocultar as camadas do mapa que deseja mostrar.

   Para obter mais informações sobre como usar [!DNL order.txt] arquivos, consulte o capítulo Configuração da interface e recursos de análise *Guia do usuário do Data Workbench*.

1. No Data Workbench, selecione o perfil desejado clicando com o botão direito do mouse na barra de título do espaço de trabalho e clicando em **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Clique com o botão direito do mouse na barra de título do espaço de trabalho e clique em **[!UICONTROL Work Online]**. Um X é exibido ao lado de [!DNL Work Online].
1. Abra um espaço de trabalho e, em uma visualização de globo, clique com o botão direito do mouse e selecione a nova camada. Um X é exibido ao lado do nome da camada.
