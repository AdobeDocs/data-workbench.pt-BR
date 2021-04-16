---
description: O Portal de relatórios usa as informações em um arquivo de configuração chamado global.asa para inicializar sessões de usuário.
title: Editar o arquivo de configuração da sessão
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Editar o arquivo de configuração da sessão{#edit-the-session-configuration-file}

O Portal de relatórios usa as informações em um arquivo de configuração chamado global.asa para inicializar sessões de usuário.

Ao instalar [!DNL Report Portal], é necessário editar esse arquivo, conforme indicado. O arquivo [!DNL global.asa] reside no \*PortalName*\PortalASP\ folder.

>[!NOTE]
>
>Não altere nenhum outro parâmetro neste arquivo de configuração.

1. Na máquina em que o IIS está sendo executado, abra o arquivo [!DNL global.asa] em um editor de texto, como o Bloco de notas.
1. Opcional. Para permitir que os usuários acessem [!DNL Report Portal] sem autenticação, altere o valor do parâmetro Session(&quot;In&quot;) para true. O padrão é false, que autentica todos os usuários que tentam acessar [!DNL Report Portal].
1. Se o [!DNL Report Portal] estiver instalado em uma unidade diferente da unidade C, altere o valor do parâmetro Session(&quot;Drive&quot;) para o local correto da unidade.
1. Para o parâmetro Session(&quot;DBPath&quot;) , altere o valor para refletir o caminho para o banco de dados que contém as informações necessárias para autenticar usuários [!DNL Report Portal]. Não inclua a letra da unidade, mas certifique-se de incluir uma barra à direita.

   Exemplo: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Salve o arquivo.
1. Para verificar se os arquivos [!DNL Report Portal] foram instalados corretamente e podem ser acessados por meio de seu diretório virtual designado, abra a seguinte página no navegador:

   http://*YourServerAddress*/*YourPortalName*

   Exemplo: [!DNL http://localhost/VisualReportPortal]

   Se as [!DNL Report Portal] ASPs tiverem sido instaladas corretamente, você deverá ver a página de logon do portal. Se você não vir esta página, verifique se os ASPs estão ativados no IIS e verifique novamente os mapeamentos de diretório virtual.
