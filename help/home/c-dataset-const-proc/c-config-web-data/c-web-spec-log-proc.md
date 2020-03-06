---
description: Informações sobre configurações específicas da Web definidas no Conjunto de dados de processamento de log Incluir arquivos fornecidos com perfis da Adobe para o Site.
solution: Analytics
title: Configurações específicas da Web para processamento de log
topic: Data workbench
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Configurações específicas da Web para processamento de log{#web-specific-settings-for-log-processing}

Informações sobre configurações específicas da Web definidas no Conjunto de dados de processamento de log Incluir arquivos fornecidos com perfis da Adobe para o Site.

A filtragem definida por essas configurações ocorre depois que as entradas do registro deixam os decodificadores e as transformações são aplicadas, mas antes da avaliação pelo [!DNL Log Entry Condition].

* [Filtragem de status HTTP](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [Filtragem de robô](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## Filtragem de status HTTP {#section-ac66acdcb6aa467d81c3721199e540fd}

Você pode configurar sua implementação de [!DNL Site] para remover entradas de log com códigos de status sc de 400 ou superior do conjunto de dados. Solicitações bem-sucedidas têm códigos de status que são menores que 400. Sua implementação padrão inclui um [!DNL Log Processing Dataset Include] arquivo no qual a filtragem de status HTTP está configurada.

**Para editar as configurações de filtragem de status HTTP**

1. Abra o arquivo [!DNL Profile Manager] em seu perfil de conjunto de dados e abra o [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg] arquivo.

   >[!NOTE]
   >
   >Se você personalizou sua implementação do, [!DNL Site]o arquivo no qual essas configurações existem pode ser diferente do local descrito.

1. Revise ou edite os valores dos parâmetros do arquivo, conforme desejado. Use o exemplo a seguir como guia.

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   Para obter informações sobre a [!DNL Range] condição, consulte [Condições](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).

1. Salve o [!DNL HTTP Status Filter.cfg] arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo.

   >[!NOTE]
   >
   >Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

## Filtragem de robô {#section-7f43681dfbc64b969619cb88f97d5ad5}

Você pode configurar sua implementação de [!DNL Site] para usar arquivos de pesquisa para remover entradas de log geradas por robôs conhecidos, scripts de teste e endereços IP para usuários internos do seu conjunto de dados. Sua implementação padrão inclui um [!DNL Log Processing Dataset Include] arquivo no qual a filtragem de robôs está configurada.

**Para editar as configurações de filtragem de robôs**

1. Abra o arquivo [!DNL Profile Manager] em seu perfil de conjunto de dados e abra o [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg] arquivo.

   >[!NOTE]
   >
   >Se você personalizou sua implementação do, [!DNL Site]o arquivo no qual essas configurações existem pode ser diferente do local descrito.

1. Revise ou edite os parâmetros do arquivo usando o exemplo e as informações a seguir como guias:

   ![](assets/cfg_WebParameters_RobotFilter.png)

   O arquivo inclui um [!DNL NotRobotCondition] que é definido pelos três parâmetros a seguir:

   * **Filtragem de robô sem distinção entre maiúsculas e minúsculas:** Verdadeiro ou falso. Se verdadeiro, letras maiúsculas e minúsculas não são consideradas na filtragem de robôs.
   * **Arquivo de pesquisa de robô, Linha de base:** O caminho e o nome do arquivo de texto que contém uma lista de agentes de usuário do navegador conhecidos como robôs e que devem ser filtrados para fora do conjunto de dados. A Adobe fornece o arquivo de pesquisa de robô básico. Se você não especificar um caminho, o servidor da análise de big data procurará esse arquivo no diretório Pesquisas no diretório de instalação do servidor da análise de big data.
   * **Arquivo de pesquisa de robô, estendido:** O caminho e o nome de um arquivo de texto opcional que contém uma lista de agentes de usuário do navegador ou endereços IP que definem robôs específicos para sua implementação. Essa lista pode incluir robôs de monitoramento interno, scripts de teste e endereços IP para usuários internos que devem ser filtrados fora do conjunto de dados. Se você não especificar um caminho, o servidor da análise de big data procurará esse arquivo no diretório Pesquisas no diretório de instalação do servidor da análise de big data.
   Se o agente de usuário do navegador de uma entrada de log não estiver listado em nenhum dos arquivos de pesquisa, a entrada de log será considerada gerada por um visitante real e não será filtrada do conjunto de dados.

   >[!NOTE]
   >
   >A correspondência nos arquivos de pesquisa de robô usa subsequências de caracteres para comparar com os campos de log c-ip e cs(user-agent). Se a string de pesquisa começar com &quot;$&quot;, ela deverá corresponder à frente da string que está sendo testada e, se ela terminar com &quot;$&quot;, a string de pesquisa deverá corresponder ao final da string que está sendo testada. Se a string de pesquisa começa com e termina com &quot;$&quot;, as strings devem corresponder exatamente à entrada do log a ser filtrada. Por exemplo, para testar todos os endereços IP em um bloco da classe C, você usaria uma string como $231.78.123. para forçar uma correspondência na frente da string. Corresponderia aos endereços 231.78.123.0 a 231.78.123.255.

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**.

1. Para que as alterações feitas localmente entrem em vigor, no [!DNL Profile Manager], clique com o botão direito do mouse na marca de seleção do arquivo na [!DNL User] coluna, em seguida, clique em **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, onde nome do perfil é o nome do perfil do conjunto de dados ou o perfil herdado ao qual o conjunto de dados inclui o arquivo.

   Não salve o arquivo de configuração modificado em nenhum dos perfis internos fornecidos pela Adobe, pois suas alterações são substituídas quando você instala atualizações nesses perfis.

   >[!NOTE]
   >
   >Se for crítico que as entradas de log subjacentes usadas para construir um conjunto de dados não sejam alteradas (mesmo se as transformações usadas para construir e atualizar o conjunto de dados e suas dimensões forem alteradas), o Arquivo de pesquisa robô, a Linha de base e o Arquivo de pesquisa robô, Extended, devem ser controlados por versão. A inserção de um número de versão nesses arquivos garante que as atualizações nos arquivos de pesquisa de robô padrão não alterem intencionalmente os conjuntos de dados de relatório construídos anteriormente adicionando ou excluindo entradas nesses arquivos.

