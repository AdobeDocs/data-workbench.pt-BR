---
description: Os nomes de pasta e arquivo incluídos na sua implementação são exibidos no lado esquerdo do Gerenciador de perfis.
solution: Analytics
title: Gerenciador de perfil
topic: Data workbench
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gerenciador de perfil{#profile-manager}

Os nomes de pasta e arquivo incluídos na sua implementação são exibidos no lado esquerdo do Gerenciador de perfis.

Os perfis que compõem seu aplicativo são exibidos como colunas individuais no [!DNL Profile Manager]. Esses perfis incluem vários perfis herdados e um único perfil de trabalho.

>[!NOTE]
>
>Seu perfil de trabalho (um perfil de conjunto de dados ou um perfil específico da função) é o perfil que você carrega ao abrir o Análise de big data.

As marcas de seleção (e suas cores) indicam a(s) pasta(s) de perfil no servidor da Análise de big data e nos computadores da Análise de big data em que cada arquivo reside, se existem várias cópias de um arquivo e se essas cópias têm a mesma data e hora modificadas. Esses arquivos são sincronizados entre o servidor do Análise de big data e os computadores do Análise de big data durante o download do perfil.

Veja a seguir uma amostra [!DNL Profile Manager] para uma implementação HBX:

![](assets/client-prof.png)

No [!DNL Profile Manager] menu, você pode abrir qualquer um dos outros gerentes (por exemplo, o [!DNL Dimensions Manager] ou [!DNL Reports Manager]), que exibem apenas partes específicas do [!DNL Profile Manager]. Você também pode criar novos gerentes de perfil. Consulte [Criação de novos gerenciadores](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3)de perfis.

Uma marca de seleção ao lado de um nome de arquivo em uma coluna específica indica que um arquivo por esse nome reside na pasta nomeada nessa coluna (perfil). À medida que você se move para a direita no [!DNL Profile Manager]campo, os arquivos têm precedência sobre aqueles para a esquerda, ou seja, cada perfil herdado se baseia nos perfis à esquerda no [!DNL Profile Manager]. Por exemplo, se você tiver um arquivo com o mesmo nome e no mesmo local no [!DNL Base] perfil (coluna) e no [!DNL User] perfil (coluna), o arquivo no [!DNL User] perfil será usado em vez do arquivo no [!DNL Base] perfil.

## Procurar perfis {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

Com o Análise de big data 5.5, um campo de pesquisa foi adicionado para localizar perfis necessários no [!DNL Profile Manager].

![](assets/client-prof2.png)

Os seguintes tipos de colunas são exibidos na [!DNL Profile Manager]:

* As colunas de nome *de perfil* herdadas contêm marcas de verificação para arquivos que residem em cada pasta de perfil. Os perfis herdados incluem perfis internos fornecidos pela Adobe, bem como qualquer perfil específico da empresa ou perfil específico da função que você criar e manter. No exemplo acima, os perfis internos incluem Base, Tráfego, Valor, Marketing e assim por diante. O [!DNL Base] perfil interno, que contém os elementos básicos e as informações de configuração necessários para executar seu aplicativo Adobe, é fornecido com cada implementação. Os outros perfis internos contêm elementos (espaços de trabalho, métricas, dimensões derivadas etc.) relacionados a tipos específicos de informações, como tráfego da Web ou marketing. A Adobe fornece apenas os perfis apropriados para o tipo de dados que você está analisando e para o seu setor.

   >[!NOTE]
   >
   >Por padrão, os perfis internos (fornecidos pela Adobe) não podem ser alterados. Toda personalização deve ocorrer em seu conjunto de dados ou em perfis específicos de função ou em outros perfis que você criar. Se você estiver criando um novo aplicativo e precisar alterar um perfil interno, é necessário alterar o parâmetro Modificar perfis internos no [!DNL Insight.cfg] arquivo. Consulte Parâmetros [de configuração do](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) Insight para obter mais informações. Antes de fazer isso, entre em contato com os Serviços de consultoria da Adobe.

* A coluna de nome *do perfil de* trabalho, que é sempre a coluna próxima à última, contém marcas de verificação para arquivos que residem na pasta do perfil de trabalho atual. No exemplo acima, o perfil de trabalho é Conjunto de dados. Seu perfil de trabalho é um perfil de conjunto de dados ou um perfil específico da função. Os arquivos desta pasta têm prioridade sobre qualquer arquivo com os mesmos nomes em qualquer pasta de perfil herdada.
* A [!DNL User] coluna, que é sempre a última coluna, contém marcas de verificação para arquivos e pastas que residem como arquivos locais na pasta User\*profile name*. A estrutura de diretório da pasta Usuário mimetiza a do perfil de trabalho, e cada pasta User\*profile name* contém cópias locais dos espaços de trabalho, métricas, dimensões e arquivos de configuração desse perfil específico. Essas cópias locais têm prioridade sobre qualquer arquivo com os mesmos nomes em qualquer pasta de perfil herdada ou de trabalho. Os arquivos na [!DNL User] coluna foram criados e salvos apenas na pasta User\*profile name* ou residem em um perfil interno ou de trabalho, bem como na pasta User\*profile name*. Os arquivos de cada pasta podem ou não ser idênticos e podem ou não ter a mesma data e hora modificadas.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Para evitar alterar seu conjunto de dados apenas localmente, o servidor do Análise de big data ignora as cópias locais do [!DNL profile.cfg] arquivo e quaisquer arquivos nas pastas Conjunto de dados ou Exportar na pasta User\*profile name*. Os arquivos ignorados são identificados por um plano de fundo vermelho na [!DNL User] coluna e um aviso &quot;Ignorado no diretório do usuário&quot; no menu de contexto. Para implementar as alterações feitas nas cópias locais desses arquivos, é necessário salvá-las no perfil de trabalho para que possam ser sincronizadas com o servidor do Análise de big data. Para obter etapas para salvar arquivos no seu perfil de trabalho, consulte [Publicação de arquivos no seu perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabalho.
      >    
      >    
   * Um hífen (-) em vez de uma marca de seleção em uma coluna identifica um arquivo vazio (byte zero). A Análise de big data trata os arquivos de byte zero como inexistentes, permitindo que você os use para ocultar os arquivos incluídos em um perfil à esquerda. Consulte [Ocultar arquivos usando arquivos](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491)vazios (zero byte).


## Determinar versões de arquivo {#section-225d732246b94cbe87acdfa9c881d6af}

Conforme mencionado na seção anterior, as marcas de seleção no arquivo [!DNL Profile Manager] são codificadas por cores para que você possa identificar facilmente onde um arquivo reside e se as várias cópias de um arquivo foram modificadas em momentos diferentes.

Se um arquivo ou diretório recolhido for exatamente o mesmo que o arquivo ou diretório à sua esquerda, ele terá a mesma marca de seleção de cor que o arquivo ou diretório naquela coluna (perfil). Se for diferente de qualquer arquivo ou diretório à esquerda, ou se o arquivo ou diretório existir apenas na [!DNL User] coluna, a marca de seleção será branca.

![](assets/vis_ProfMgr_LocalFiles.png)

O exemplo [!DNL Profile Manager] mostrado acima indica o seguinte:

* Uma marca de seleção branca para o [!DNL A New Metric.metric] [!DNL User] arquivo aparece somente na coluna, o que indica que você tem apenas uma cópia local desse arquivo — ele não foi publicado (ou carregado) no servidor da Análise de big data para que outros usuários da Análise de big data acessem.

* As marcas de verificação para o nome do [!DNL Average Score.metric] arquivo são exibidas nos Filmes e [!DNL User] colunas. A marca de seleção na [!DNL User] coluna tem a mesma cor que a marca de seleção na coluna Filmes, o que indica que a cópia local do arquivo tem a mesma data e hora Modificadas que o arquivo na pasta Filmes.

* As marcas de verificação para o nome do [!DNL Average Score Error.metric] arquivo são exibidas nos Filmes e [!DNL User] colunas. A marca de seleção na [!DNL User] coluna é branca, o que indica que a cópia local do arquivo tem uma data ou hora Modificada diferente do arquivo na pasta Filmes.

