---
description: Os nomes de pasta e arquivo incluídos na implementação são exibidos no lado esquerdo do Gerenciador de perfis.
title: Gerenciador de perfis
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# Gerenciador de perfis{#profile-manager}

{{eol}}

Os nomes de pasta e arquivo incluídos na implementação são exibidos no lado esquerdo do Gerenciador de perfis.

Os perfis que compõem seu aplicativo são exibidos como colunas individuais no [!DNL Profile Manager]. Esses perfis incluem vários perfis herdados e um único perfil de trabalho.

>[!NOTE]
>
>Seu perfil de trabalho (um perfil de conjunto de dados ou um perfil específico de função) é o perfil que você carrega ao abrir o Data Workbench.

As marcas de verificação (e suas cores) indicam as pastas de perfil no servidor do Data Workbench e os computadores do Data Workbench em que cada arquivo reside, se existem várias cópias de um arquivo e se essas cópias têm a mesma data e hora Modificadas. Esses arquivos são sincronizados entre o servidor do Data Workbench e os computadores do Data Workbench durante o download do perfil.

Veja a seguir uma amostra [!DNL Profile Manager] para uma implementação HBX:

![](assets/client-prof.png)

No [!DNL Profile Manager] , você pode abrir qualquer um dos outros gerentes (por exemplo, a variável [!DNL Dimensions Manager] ou [!DNL Reports Manager]), que exibem apenas partes específicas de [!DNL Profile Manager]. Você também pode criar novos gerentes de perfil. Consulte [Criação de novos gerenciadores de perfil](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

Uma marca de seleção ao lado de um nome de arquivo em uma coluna específica indica que um arquivo com esse nome reside na pasta nomeada nessa coluna (perfil). À medida que você se move para a direita no [!DNL Profile Manager], os arquivos têm precedência sobre aqueles à esquerda, ou seja, cada perfil herdado é construído nos perfis à esquerda na variável [!DNL Profile Manager]. Por exemplo, se você tiver um arquivo com o mesmo nome e no mesmo local no [!DNL Base] perfil (coluna) e no [!DNL User] perfil (coluna), o arquivo no [!DNL User] O perfil é usado em vez do arquivo no [!DNL Base] perfil.

## Pesquisar perfis {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

Com a Data Workbench 5.5, um campo de pesquisa foi adicionado para encontrar perfis necessários na [!DNL Profile Manager].

![](assets/client-prof2.png)

Os seguintes tipos de colunas aparecem no [!DNL Profile Manager]:

* O *nome de perfil herdado* As colunas contêm marcas de verificação para arquivos que residem em cada pasta de perfil. Os perfis herdados incluem perfis internos fornecidos pelo Adobe, bem como qualquer perfil específico da empresa ou de função que você criar e manter. No exemplo acima, os perfis internos incluem Base, Tráfego, Valor, Marketing e assim por diante. O [!DNL Base] O perfil, que contém os blocos de construção básicos e as informações de configuração necessárias para executar o aplicativo Adobe, é fornecido com cada implementação. Os outros perfis internos contêm elementos (espaços de trabalho, métricas, dimensões derivadas etc.) relacionados a tipos específicos de informações, como tráfego da Web ou marketing. O Adobe fornece apenas os perfis adequados para o tipo de dados que você está analisando e para o seu setor.

   >[!NOTE]
   >
   >Por padrão, os perfis internos (aqueles fornecidos pelo Adobe) não podem ser alterados. Toda personalização deve ocorrer em seu conjunto de dados, em perfis específicos de função ou em outros perfis que você criar. Se estiver criando um novo aplicativo e precisar alterar um perfil interno, altere o parâmetro Modificar perfis internos na seção [!DNL Insight.cfg] arquivo. Consulte [Parâmetros de configuração do Insight](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) para obter mais informações. Antes de fazer isso, entre em contato com os Serviços de consultoria da Adobe.

* O *nome do perfil de trabalho* , que é sempre a próxima à última coluna, contém marcas de verificação para arquivos que residem na pasta do perfil de trabalho atual. No exemplo acima, o perfil de trabalho é Conjunto de dados. Seu perfil de trabalho é um perfil de conjunto de dados ou um perfil específico de função. Os arquivos nessa pasta têm prioridade sobre qualquer arquivo com os mesmos nomes em qualquer pasta de perfil herdada.
* O [!DNL User] , que é sempre a última coluna, contém marcas de verificação para arquivos e pastas que residem como arquivos locais na pasta User\*profile name*. A estrutura de diretório da pasta Usuário imita a do perfil de trabalho, e cada pasta User\*nome do perfil* contém cópias locais dos espaços de trabalho, métricas, dimensões e arquivos de configuração para esse perfil específico. Essas cópias locais têm prioridade sobre qualquer arquivo com os mesmos nomes em qualquer pasta de perfil herdada ou de trabalho. Os arquivos na [!DNL User] foram criadas e salvas somente na pasta User\*profile name* ou residem em um perfil interno ou de trabalho, bem como na pasta User\*profile name*. Os arquivos em cada pasta podem ou não ser idênticos e podem ou não ter a mesma data e hora modificadas.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Para evitar alterar seu conjunto de dados somente localmente, o servidor do Data Workbench ignora as cópias locais do [!DNL profile.cfg] e quaisquer arquivos no conjunto de dados ou nas pastas Exportar na pasta Usuário\*nome do perfil*. Os arquivos ignorados são identificados por um plano de fundo vermelho no [!DNL User] e um aviso &quot;Ignorado no diretório do usuário&quot; no menu de contexto. Para implementar as alterações feitas nas cópias locais desses arquivos, você deve salvá-las no perfil de trabalho para que possam ser sincronizadas com o servidor do Data Workbench. Para obter etapas para salvar arquivos em seu perfil de trabalho, consulte [Publicar arquivos no seu perfil de trabalho](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
   >    
   >    * Um hífen (-) em vez de uma marca de seleção em uma coluna identifica um arquivo vazio (byte zero). O Data Workbench trata arquivos de byte zero como inexistentes, o que permite usá-los para ocultar arquivos incluídos em um perfil à esquerda. Consulte [Ocultar arquivos usando arquivos vazios (zero bytes)](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## Determinar versões de arquivo {#section-225d732246b94cbe87acdfa9c881d6af}

Como mencionado na seção anterior, as marcas de verificação no [!DNL Profile Manager] são codificadas por cores, de modo que você possa identificar facilmente onde um arquivo reside e se as várias cópias de um arquivo foram modificadas em momentos diferentes.

Se um arquivo ou um diretório recolhido for exatamente o mesmo que o arquivo ou diretório à esquerda, ele terá a mesma marca de verificação de cor que o arquivo ou diretório nessa coluna (perfil). Se for diferente de qualquer arquivo ou diretório à sua esquerda, ou se o arquivo ou diretório existir somente na variável [!DNL User] coluna, a marca de seleção é branca.

![](assets/vis_ProfMgr_LocalFiles.png)

O [!DNL Profile Manager] mostrado no exemplo acima indica o seguinte:

* Uma marca de verificação branca para a variável [!DNL A New Metric.metric] O arquivo aparece somente no [!DNL User] indica que você tem apenas uma cópia local desse arquivo; ele não foi publicado (ou carregado) no servidor do Data Workbench para que outros usuários do Data Workbench acessem.

* Marque as marcas para a [!DNL Average Score.metric] o nome do arquivo aparece em Filmes e [!DNL User] colunas. A marca de verificação no [!DNL User] é a mesma cor da marca de seleção na coluna Filmes , que indica que a cópia local do arquivo tem a mesma data e hora Modificadas que o arquivo na pasta Filmes .

* Marque as marcas para a [!DNL Average Score Error.metric] o nome do arquivo aparece em Filmes e [!DNL User] colunas. A marca de verificação no [!DNL User] é branca, o que indica que a cópia local do arquivo tem uma data ou hora Modificada diferente do arquivo na pasta Filmes.

