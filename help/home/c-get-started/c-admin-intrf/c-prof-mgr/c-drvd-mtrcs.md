---
description: Você define novas métricas (conhecidas como métricas derivadas) e edita definições de métricas existentes usando o Editor de métricas.
solution: Analytics
title: Trabalhar com métricas derivadas
topic: Data workbench
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trabalhar com métricas derivadas{#work-with-derived-metrics}

Você define novas métricas (conhecidas como métricas derivadas) e edita definições de métricas existentes usando o Editor de métricas.

Para obter mais informações sobre métricas do que as fornecidas nesta seção e na Sintaxe [de linguagem de](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)consulta, consulte o Guia *de* métricas, dimensões e filtros.

## Criar uma métrica derivada {#section-d57b98bf0a9940daba4920ff7efc808d}

Use um formulário [!DNL Metric Editor] para definir uma nova métrica por nome, fórmula e formato, que é salvo na pasta Usuário\*nome_do_perfil*\Métricas para uso posterior.

1. Abra uma nova [!DNL Metric Editor] usando a opção de menu **[!UICONTROL Admin]** > **[!UICONTROL Profile]** ou clicando com o botão direito do mouse na coluna **[!UICONTROL User]** da pasta na qual deseja criar a métrica e clicando em **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   Um [!DNL Metric Editor] é exibido.

1. No parâmetro Name, digite um nome para a nova métrica.

   Observe que espaços ( ) são permitidos enquanto sublinhados (_) não são permitidos. Além disso, não é possível usar os seguintes símbolos:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. No parâmetro Fórmula, digite uma expressão para a nova métrica. Observe que os filtros devem ser definidos entre colchetes [ ] na expressão.

   Para obter mais regras de sintaxe de expressão de métrica, consulte [Sintaxe para Expressões](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66)de métrica.

   A tabela a seguir fornece exemplos de expressões para métricas estendidas.

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Nome da métrica estendida </th> 
      <th colname="col2" class="entry"> Expressão </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Porcentagem de primeiras sessões </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sessões [Session_Number="1"]/Sessões</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Primeira sessão de conversão </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Conversão [Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Valor médio por visitante </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Valor/Visitantes</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >Quando uma expressão apropriada é inserida, a linha de visualização exibe o valor da nova métrica. Se houver um erro na expressão, a linha de visualização exibirá uma mensagem de erro.

1. Clique com o botão direito do mouse **[!UICONTROL (New)]** e clique em **[!UICONTROL Save]**.

   Quando você salva a métrica, um arquivo que representa a nova métrica é criado no computador, no diretório de instalação do Análise de big data \User\*nome do perfil*\Métricas.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Agora você pode usar a nova métrica em todo o perfil atual selecionando-a como faria com qualquer métrica incorporada. Para alterar a ordem em que suas métricas aparecem no menu de métricas, consulte [Personalizar menus usando arquivos](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

Se você deseja que todos os usuários do perfil usem a métrica criada, é necessário publicá-la no perfil de trabalho usando o [!DNL Profile Manager]. Consulte [Publicação de arquivos no seu perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabalho.

## Editar métricas derivadas {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. Na [!DNL Profile Manager] ou [!DNL Metrics Manager], na coluna nome *do* perfil, clique com o botão direito do mouse na marca de seleção do arquivo de métrica que deseja editar e clique em **[!UICONTROL Make Local]**.
1. Clique com o botão direito do mouse na marca de seleção do arquivo de métrica na [!DNL User] coluna e clique em **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >Você também pode abrir uma página [!DNL Metric Editor] clicando com o botão direito do mouse em qualquer área relacionada à métrica em uma visualização para exibir o menu de métricas. Para obter mais informações, consulte [Trabalhar com menus](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac)de métrica e dimensão.

1. No [!DNL Metric Editor], edite e salve a definição da métrica conforme necessário usando as Etapas 2 a 4 em [Criar novas métricas](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d)derivadas.

   Se você deseja que todos os usuários do perfil usem a métrica editada, é necessário publicá-la no perfil de trabalho usando o [!DNL Profile Manager]. Consulte [Publicação de arquivos no seu perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabalho.

