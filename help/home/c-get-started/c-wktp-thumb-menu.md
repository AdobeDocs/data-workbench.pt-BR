---
description: Como exportar, copiar e marcar a partir da área de trabalho.
title: Uso do menu Miniatura da bancada
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
exl-id: 2220051d-5c53-48ed-8e13-62883819f22a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Uso do menu Miniatura da bancada{#using-the-worktop-thumbnail-menu}

Como exportar, copiar e marcar a partir da área de trabalho.

Clique com o botão direito do mouse em um espaço de trabalho para exportar, copiar e marcar funções do desktop.

![](assets/thumbnail_menu.png)

## Descrições da interface {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

Os seguintes elementos estão disponíveis no menu de miniatura [!DNL Worktop]:

**Espaço de trabalho do servidor:** *nome*

Aparece somente para espaços de trabalho do servidor não editados. Identifica o espaço de trabalho nomeado como o mesmo espaço de trabalho armazenado no servidor.

**Data:** *dia e hora*

A data e a hora em que o espaço de trabalho foi aberto pela última vez.

**Versão local de:** *name*

Aparece somente para versões locais de espaços de trabalho do servidor. Identifica o espaço de trabalho nomeado como uma versão editada local de um espaço de trabalho armazenado no servidor.

**Espaço de trabalho do usuário:** *nome*

Aparece somente para espaços de trabalho do usuário. Identifica o espaço de trabalho nomeado como um espaço de trabalho que existe somente na máquina local.

**Computar em segundo plano**

Aparece somente ao trabalhar online. Mantém as consultas no espaço de trabalho selecionado em execução em segundo plano enquanto você continua trabalhando. Quando selecionada, a miniatura exibe as seguintes informações, que indicam o progresso das consultas:

* Trabalhando: *n%* - indica que a consulta está processando e a porcentagem do processamento que está concluída.
* ** nMB Query Load - tamanho total do resultado da consulta. O carregamento da consulta é proporcional à carga total de memória do servidor do Data Workbench, mas não se correlaciona diretamente. Como diretriz, uma carga de consulta de 10 MB ou mais pode sobrecarregar o sistema. O carregamento de consulta listado não leva o clustering em consideração.

   >[!NOTE]
   >
   >Se Computar em Segundo Plano permanecer selecionado, as consultas no espaço de trabalho selecionado se tornarão consultas permanentes, continuando a ser atualizadas e a usar a carga de memória. Certifique-se de desmarcar Computar em segundo plano quando terminar de trabalhar no espaço de trabalho.

**Exportar para Excel**

Exportar dados do espaço de trabalho para tabela no Microsoft Excel (arquivos .xls e .xslx). Ao exportar um espaço de trabalho para o Excel, o Data Workbench exporta dados de determinadas visualizações, legendas de dimensão e valor e anotações de texto para uma nova pasta de trabalho do Excel com uma visualização por planilha.

**Exportar para modelo do Excel**

Exportar para um modelo do Excel (.xltx).

**Copiar**

Copia o espaço de trabalho. Para obter mais informações sobre como colar um espaço de trabalho copiado, consulte [Copiando e colando espaços de trabalho existentes](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65).

**Reverter para versão do servidor**

Aparece somente para versões locais de espaços de trabalho do servidor. Exclui a cópia local deste espaço de trabalho. O original permanece no servidor.

**Excluir**

Aparece somente para espaços de trabalho do usuário. Exclui o espaço de trabalho do usuário, que existe somente no computador local. Para obter informações sobre como excluir espaços de trabalho do servidor do Data Workbench conectado, consulte [Excluir arquivos do seu perfil de trabalho](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b).

**Salvar no servidor**

Aparece somente para versões locais de espaços de trabalho do servidor e espaços de trabalho do usuário e funciona somente para os usuários com as permissões apropriadas. Salva a cópia local do espaço de trabalho no servidor. Por padrão, os espaços de trabalho são salvos na pasta de trabalho `<profile name>\Workspaces\<tab name>` apropriada.

**Marcador**

Marque um espaço de trabalho como favorito para recuperar rapidamente depois.

Um ícone de marcador ![](assets/bookmark_icon.png) será exibido acima do espaço de trabalho na bancada e o nome do espaço de trabalho será exibido no painel Marcador . ![](assets/bookmark_worktop.png)
