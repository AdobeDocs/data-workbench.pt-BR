---
description: Como exportar, copiar e marcar a partir da área de trabalho.
solution: Analytics
title: Uso do menu Miniatura da área de trabalho
topic: Data workbench
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Uso do menu Miniatura da área de trabalho{#using-the-worktop-thumbnail-menu}

Como exportar, copiar e marcar a partir da área de trabalho.

Clique com o botão direito do mouse em um Espaço de trabalho para exportar, copiar e marcar funções da área de trabalho.

![](assets/thumbnail_menu.png)

## Descrições da interface {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

Os seguintes elementos estão disponíveis no menu em [!DNL Worktop] miniatura:

**Área de trabalho do servidor:** *nome*

Aparece somente para espaços de trabalho não editados do servidor. Identifica o espaço de trabalho nomeado como o mesmo espaço de trabalho armazenado no servidor.

**Data:** *dia e hora*

A data e a hora em que o espaço de trabalho foi aberto pela última vez.

**Versão local de:** *nome*

Aparece somente para versões locais de espaços de trabalho do servidor. Identifica o espaço de trabalho nomeado como uma versão editada local de um espaço de trabalho armazenado no servidor.

**Área de trabalho do usuário:** *nome*

Aparece somente para espaços de trabalho do usuário. Identifica o espaço de trabalho nomeado como um espaço de trabalho que existe apenas na máquina local.

**Computação em segundo plano**

Aparece somente ao trabalhar online. Mantém as consultas no espaço de trabalho selecionado em execução em segundo plano enquanto você continua trabalhando. Quando selecionada, a miniatura exibe as seguintes informações, que indicam o progresso das consultas:

* Trabalhando: *n%* - indica que a consulta está sendo processada e a porcentagem do processamento concluído.
* *n* MB Query Load - tamanho total do resultado da consulta. A Carga de consulta é proporcional à carga total de memória do servidor da Análise de big data, mas não se correlaciona diretamente. Como diretriz, uma carga de consulta de 10 MB ou mais pode sobrecarregar o sistema. A carga de consulta listada não leva em conta o agrupamento.

   >[!NOTE]
   >
   >Se a opção Calcular em segundo plano permanecer selecionada, as consultas no espaço de trabalho selecionado se tornarão consultas permanentes, continuando a ser atualizadas e usando a carga de memória. Desmarque a opção Computar em segundo plano quando terminar de trabalhar no espaço de trabalho.

**Exportar para Excel**

Exporte dados de espaço de trabalho para tabela no Microsoft Excel (arquivos .xls e .xslx). Ao exportar um espaço de trabalho para o Excel, o Análise de big data exporta dados de determinadas visualizações, legendas de dimensão e valor e anotações em texto para uma nova pasta de trabalho do Excel com uma visualização por planilha.

**Exportar para Modelo do Excel**

Exportar para um modelo do Excel (.xltx).

**Copiar**

Copia o espaço de trabalho. Para obter mais informações sobre como colar um espaço de trabalho copiado, consulte [Copiando e Colando Espaços de Trabalho](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65)Existentes.

**Reverter para versão do servidor**

Aparece somente para versões locais de espaços de trabalho do servidor. Exclui a cópia local deste espaço de trabalho. O original permanece no servidor.

**Excluir**

Aparece somente para espaços de trabalho do usuário. Exclui o espaço de trabalho do usuário, que existe somente no computador local. Para obter informações sobre como excluir espaços de trabalho do servidor do Análise de big data conectado, consulte [Excluir arquivos do seu perfil](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b)de trabalho.

**Salvar no servidor**

Aparece somente para versões locais de espaços de trabalho do servidor e de usuários e funciona somente para usuários com as permissões apropriadas. Salva a cópia local do espaço de trabalho no servidor. Por padrão, os espaços de trabalho são salvos na `<profile name>\Workspaces\<tab name>` pasta de trabalho apropriada.

**Marcador**

Marque um espaço de trabalho como favorito para recuperar rapidamente mais tarde.

Um ícone de marcador ![](assets/bookmark_icon.png) aparecerá acima da área de trabalho na área de trabalho e o nome da área de trabalho aparecerá no painel Marcador. ![](assets/bookmark_worktop.png)

