---
description: Os conjuntos de relatórios devem ser configurados de uma maneira específica para produzir relatórios que são exibidos corretamente por meio do Portal de relatórios.
title: Personalizar a interface do usuário do portal de relatórios
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Personalizar a interface do usuário do portal de relatórios{#customize-the-report-portal-user-interface}

{{eol}}

Os conjuntos de relatórios devem ser configurados de uma maneira específica para produzir relatórios que são exibidos corretamente por meio do Portal de relatórios.

A interface do usuário do para [!DNL Report Portal] foi criada para exibir uma guia para cada pasta de conjunto de relatórios que aparece no diretório de saída e é listada no [!DNL profiles.xml] , bem como o arquivo incorporado [!DNL Admin] , que deve ser adicionada à variável [!DNL TopNavigation.xml] arquivo a ser exibido. Para obter mais informações sobre como exibir o [!DNL Admin] guia , consulte [Vincular uma pasta de saída a uma guia no usuário..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Certificando-se de que seus conjuntos de relatórios são compatíveis com o portal de relatórios...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Vincular uma pasta de saída a uma guia no usuário..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Garantir que seus conjuntos de relatórios sejam compatíveis com o portal de relatórios {#section-2b141e5d198a4bbea455699126c24706}

Um conjunto de relatórios define um trabalho agendado para [!DNL Report]. Consiste em dois itens:

* Uma pasta que define a coleção de espaços de trabalho que você deseja [!DNL Report] para gerar como relatórios.
* Um arquivo de configuração ( [!DNL Report.cfg]).

Entre outras coisas, a variável [!DNL Report.cfg] o arquivo informa [!DNL Report] quando gerar os relatórios e onde salvar os arquivos de saída. Os conjuntos de relatórios ficam na pasta Relatórios no servidor do Data Workbench. Um perfil pode exibir qualquer número de conjuntos de relatórios.

Para garantir a compatibilidade com o [!DNL Report Portal], seus conjuntos de relatórios devem atender aos seguintes requisitos:

* O diretório de saída dos conjuntos de relatórios deve conter um [!DNL profiles.xml] arquivo.
* Cada conjunto de relatórios deve incluir um relatório de nível superior chamado &quot;*ReportSetName* Resumo, onde *ReportSetName* corresponde ao nome do conjunto de relatórios. Por exemplo, o seguinte [!DNL Profile Manager] mostra dois conjuntos de relatórios, &quot;Início&quot; e &quot;Tráfego&quot;. Observe que cada conjunto de relatórios define um relatório de resumo ( [!DNL Home Summary.vw] e [!DNL Traffic Summary.vw], respectivamente).

![](assets/rptPort_scrn_RptSets.png)

Em [!DNL Report Portal], o relatório de resumo é exibido na guia do conjunto de relatórios. O relatório de resumo pode conter qualquer espaço de trabalho, janela ou visualização escolhida.

* O relatório de resumo deve ser o único relatório na pasta de nível superior de um conjunto de relatórios. Todos os outros relatórios devem ser colocados em subpastas. Se você colocar outros relatórios na pasta de nível superior, não poderá visualizá-los no portal.

## Vincular uma pasta de saída a uma guia na interface do usuário {#section-3f6bc47d37ed448e871f4f685f46acee}

Especificação das guias que deseja [!DNL Report Portal] para exibir, você deve configurar um [!DNL TopNavigation.xml] para cada perfil. Esse arquivo determina quais conjuntos de relatórios aparecem como guias na interface do usuário para um perfil específico, bem como a ordem dessas guias. O [!DNL TopNavigation.xml] O arquivo reside na pasta \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**Para editar o arquivo TopNavigation.xml**

1. Na máquina em que o IIS está em execução, abra o [!DNL TopNavigation.xml] em um editor de texto, como o Bloco de notas.
1. Edite a lista de `<TopNav>` elementos para que ele defina os nomes e a ordem dos conjuntos de relatórios cuja saída você deseja [!DNL Report Portal] para exibir, como no exemplo a seguir:

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
   >O [!DNL Admin] é uma guia incorporada que fornece funcionalidade adicional. Se você não incluí-lo na variável [!DNL TopNavigation.xml] , essa guia não é exibida e sua funcionalidade não está disponível.

1. No \*PortalName*\PortalFiles\Core\TopNav\ folder, crie uma pasta para o próximo perfil.
1. Copie o [!DNL TopNavigation.xml] da primeira pasta de perfil e cole-a na nova pasta.
1. Edite o [!DNL TopNavigation.xml] conforme necessário, salve o arquivo.
1. Repita as Etapas 3 a 5 para todos os outros perfis disponíveis no portal.
