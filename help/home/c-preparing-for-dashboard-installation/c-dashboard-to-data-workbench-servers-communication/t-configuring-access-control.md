---
description: O painel requer determinadas permissões somente leitura para poder acessar e exibir seus dados da análise de big data. Privilégios de gravação não são obrigatórios.
solution: Analytics
title: Configurando o controle de acesso
topic: Data workbench
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurando o controle de acesso{#configuring-access-control}

O painel requer determinadas permissões somente leitura para poder acessar e exibir seus dados da análise de big data. Privilégios de gravação não são obrigatórios.

A configuração do controle de acesso envolve a edição de seu [!DNL Access Control.cfg] arquivo nos FSUs e a adição de um novo grupo para conceder permissão ao painel da análise de big data:

1. Edite o [!DNL AccessControl.cfg] arquivo (preferencialmente usando a estação de trabalho de análise de big data).
1. Crie um novo grupo chamado Acesso *ao painel do* Insight.
1. Sob os membros deste grupo, adicione o CN correto fornecido a você para essa finalidade (Exemplo: CN:INSIGHT-USER01). Entre em contato com o Atendimento ao cliente da Adobe para obter este CN.
1. No acesso somente leitura deste grupo, modifique a lista para refletir o seguinte:

* /Profiles/$
* /Profiles/
* /Endereços
* /Status/
* /Usuários/$

1. Remova todos os itens da seção de acesso de leitura e gravação, pois nenhuma permissão de gravação é necessária para o painel.
1. Salve as alterações no [!DNL AccessControl.cfg] arquivo no servidor para que as permissões entrem em vigor.
