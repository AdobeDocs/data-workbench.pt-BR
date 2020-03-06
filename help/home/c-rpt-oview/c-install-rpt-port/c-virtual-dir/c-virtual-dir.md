---
description: Para configurar o Portal de relatórios, é necessário mapear seus arquivos de aplicativo para diretórios virtuais.
solution: Analytics
title: Mapear as páginas do portal de relatórios para diretórios virtuais
topic: Data workbench
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mapear as páginas do portal de relatórios para diretórios virtuais{#map-the-report-portal-pages-to-virtual-directories}

Para configurar o Portal de relatórios, é necessário mapear seus arquivos de aplicativo para diretórios virtuais.

Um diretório virtual define o endereço que os clientes do navegador usam para localizar um recurso físico no servidor de aplicativos IIS. Para acessar [!DNL Report Portal], os clientes apontam seus navegadores para o diretório virtual que você atribui ao portal.

O nome do diretório virtual ao qual você atribui [!DNL Report Portal] deve corresponder ao nome usado para a pasta VSVirtualPortalName na Etapa 3 da seção anterior. Por exemplo, se você deseja usar &quot;Portal&quot; como o nome do seu portal, [!DNL Report Portal]é necessário mapear os arquivos do portal para um diretório virtual chamado &quot;Portal&quot;. O exemplo a seguir mostra o URI que os clientes usariam para acessar um diretório virtual [!DNL Report Portal] atribuído [!DNL VisualReportPortal] em um servidor chamado myWebServer:

[!DNL http://myWebServer/VisualReportPortal]

Os procedimentos a seguir descrevem como mapear [!DNL Report Portal] para um diretório virtual no IIS 5.0, 6.0 e 7.0 ou superior.

Siga o conjunto de procedimentos para a versão do IIS que você está usando:

* [Mapeamento do portal de relatórios para um diretório virtual (IIS 7.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [Mapeamento do portal de relatórios para um diretório virtual (IIS 5.0)](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [Editar o arquivo de configuração da sessão](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)

