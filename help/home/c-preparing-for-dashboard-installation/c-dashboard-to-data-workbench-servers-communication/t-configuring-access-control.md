---
description: O painel requer determinadas permissões somente leitura para acessar e exibir seus dados do Data Workbench. Privilégios de gravação não são necessários.
title: Configurar o controle de acesso
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 6%

---

# Configurar o controle de acesso{#configuring-access-control}

O painel requer determinadas permissões somente leitura para acessar e exibir seus dados do Data Workbench. Privilégios de gravação não são necessários.

A configuração do controle de acesso envolve a edição do arquivo [!DNL Access Control.cfg] no(s) FSU(s) e a adição de um novo grupo para conceder permissão ao painel do Data Workbench:

1. Edite o arquivo [!DNL AccessControl.cfg] (preferencialmente usando a estação de trabalho de análise de big data).
1. Crie um novo grupo chamado *Acesso ao Painel Insight*.
1. Nos membros deste grupo, adicione o CN correto fornecido a você para essa finalidade (Exemplo: CN:INSIGHT-USER01). Entre em contato com o Atendimento ao cliente do Adobe para obter esse CN.
1. No acesso somente leitura deste grupo, modifique a lista para refletir o seguinte:

* /Perfis/$
* /Perfis/
* /Endereços
* /Status/
* /Usuários/$

1. Remova quaisquer itens da seção de acesso de leitura e gravação, pois nenhuma permissão de gravação é necessária para o painel.
1. Salve as alterações no arquivo [!DNL AccessControl.cfg] no servidor para que as permissões tenham efeito.
