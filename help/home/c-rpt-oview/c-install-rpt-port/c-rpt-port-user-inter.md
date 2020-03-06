---
description: Os conjuntos de relatórios devem ser configurados de uma maneira específica para produzir relatórios que são exibidos corretamente pelo Portal de relatórios.
solution: Analytics
title: Personalizar a interface do usuário do Portal de relatórios
topic: Data workbench
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personalizar a interface do usuário do Portal de relatórios{#customize-the-report-portal-user-interface}

Os conjuntos de relatórios devem ser configurados de uma maneira específica para produzir relatórios que são exibidos corretamente pelo Portal de relatórios.

A interface do usuário para [!DNL Report Portal] é projetada para exibir uma guia para cada pasta de conjunto de relatórios que aparece no diretório de saída e está listada no [!DNL profiles.xml] arquivo, bem como a guia incorporada [!DNL Admin] , que deve ser adicionada ao [!DNL TopNavigation.xml] arquivo a ser exibido. Para obter mais informações sobre como exibir a [!DNL Admin] guia incorporada, consulte [Vincular uma pasta de saída a uma guia no usuário...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Verificando se os conjuntos de relatórios são compatíveis com o Portal de relatórios...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Vinculando uma pasta de saída a uma guia no usuário...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Verificar se seus conjuntos de relatórios são compatíveis com o Portal de relatórios {#section-2b141e5d198a4bbea455699126c24706}

Um conjunto de relatórios define um trabalho programado para [!DNL Report]. É composto por dois elementos:

* Uma pasta que define a coleção de espaços de trabalho que você deseja gerar [!DNL Report] como relatórios.
* Um arquivo de configuração ( [!DNL Report.cfg]).

Entre outras coisas, o [!DNL Report.cfg] arquivo informa [!DNL Report] quando gerar os relatórios e onde salvar os arquivos de saída. Os conjuntos de relatórios residem na pasta Relatórios no servidor da análise de big data. Um perfil pode exibir qualquer número de conjuntos de relatórios.

Para garantir a compatibilidade com [!DNL Report Portal], seus conjuntos de relatórios devem atender aos seguintes requisitos:

* O diretório de saída dos conjuntos de relatórios deve conter um [!DNL profiles.xml] arquivo configurado.
* Cada conjunto de relatórios deve incluir um relatório de nível superior chamado &quot;Resumo de *ReportSetName* &quot;, onde *ReportSetName* corresponde ao nome do conjunto de relatórios. Por exemplo, a seguir [!DNL Profile Manager] são exibidos dois conjuntos de relatórios, &quot;Início&quot; e &quot;Tráfego&quot;. Observe que cada conjunto de relatórios define um relatório de resumo ( [!DNL Home Summary.vw] e [!DNL Traffic Summary.vw], respectivamente).

![](assets/rptPort_scrn_RptSets.png)

Em, [!DNL Report Portal]o relatório de resumo é exibido na guia do conjunto de relatórios. O relatório de resumo pode conter qualquer espaço de trabalho, janela ou visualização escolhida.

* O relatório de resumo deve ser o único relatório na pasta de nível superior de um conjunto de relatórios. Todos os outros relatórios devem ser colocados em subpastas. Se você colocar outros relatórios na pasta de nível superior, não poderá visualizá-los pelo portal.

## Vincular uma pasta de saída a uma guia na interface do usuário {#section-3f6bc47d37ed448e871f4f685f46acee}

Para especificar as guias que deseja exibir, é necessário configurar um [!DNL Report Portal] [!DNL TopNavigation.xml] arquivo para cada perfil. Esse arquivo determina quais conjuntos de relatórios aparecem como guias na interface do usuário para um perfil específico, bem como a ordem dessas guias. O [!DNL TopNavigation.xml] arquivo está localizado na pasta \*NomePortal*\PortalFiles\Core\TopNav\*profileName*.

**Para editar o arquivo TopNavigation.xml**

1. Na máquina em que o IIS está sendo executado, abra o [!DNL TopNavigation.xml] arquivo em um editor de texto, como o Bloco de notas.
1. Edite a lista de `<TopNav>` [!DNL Report Portal] elementos para que ela defina os nomes e a ordem dos conjuntos de relatórios cuja saída você deseja exibir, como no exemplo a seguir:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <TOPNAV_ELEMENTS>
   <TOPNAV>
       <NAME>Monthly Web</NAME>
     </TOPNAV>
     <TOPNAV>
       <NAME>Weekly Web</NAME>
     </TOPNAV>
   <TOPNAV> 
         <NAME>Admin</NAME> 
     </TOPNAV>
   </TOPNAV_ELEMENTS>
   ```

   >[!NOTE]
   >
   >A guia [!DNL Admin] é uma guia incorporada que fornece funcionalidade adicional. Se você não incluí-la no [!DNL TopNavigation.xml] arquivo, essa guia não será exibida e sua funcionalidade não estará disponível.

1. No \*PortalName*\PortalFiles\Core\TopNav\ folder, crie uma pasta para o seu próximo perfil.
1. Copie o [!DNL TopNavigation.xml] arquivo da primeira pasta de perfil e cole-o na nova pasta.
1. Edite o arquivo [!DNL TopNavigation.xml] conforme necessário e salve-o.
1. Repita as Etapas 3 a 5 para todos os outros perfis disponíveis no portal.

