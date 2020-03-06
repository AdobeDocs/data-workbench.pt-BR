---
description: O Portal de relatórios usa as informações em um arquivo de configuração chamado global.asa para inicializar as sessões do usuário.
solution: Analytics
title: Editar o arquivo de configuração da sessão
topic: Data workbench
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Editar o arquivo de configuração da sessão{#edit-the-session-configuration-file}

O Portal de relatórios usa as informações em um arquivo de configuração chamado global.asa para inicializar as sessões do usuário.

Ao instalar [!DNL Report Portal], edite esse arquivo conforme indicado. O [!DNL global.asa] arquivo reside no diretório \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Não altere nenhum outro parâmetro neste arquivo de configuração.

1. Na máquina em que o IIS está sendo executado, abra o [!DNL global.asa] arquivo em um editor de texto, como o Bloco de notas.
1. Opcional. Para permitir que os usuários acessem [!DNL Report Portal] sem autenticação, altere o valor do parâmetro Session(&quot;In&quot;) para true. O padrão é false, que autentica todos os usuários que tentam acessar [!DNL Report Portal].
1. Se [!DNL Report Portal] estiver instalado em uma unidade diferente da unidade C, altere o valor do parâmetro Session(&quot;Drive&quot;) para o local correto da unidade.
1. Para o parâmetro Session(&quot;DBPath&quot;), altere o valor para refletir o caminho para o banco de dados que contém as informações necessárias para autenticar [!DNL Report Portal] os usuários. Não inclua a letra da unidade, mas certifique-se de incluir uma barra.

   Exemplo: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Salve o arquivo.
1. Para verificar se os [!DNL Report Portal] arquivos foram instalados corretamente e podem ser acessados por meio de seu diretório virtual designado, abra a seguinte página no navegador:

   http://*YourServerAddress*/*YourPortalName*

   Exemplo: [!DNL http://localhost/VisualReportPortal]

   Se os [!DNL Report Portal] ASPs tiverem sido instalados corretamente, você deverá ver a página de logon do portal. Se você não vir esta página, verifique se os ASPs estão ativados no IIS e verifique novamente os mapeamentos do diretório virtual.

