---
description: O Portal de relatórios usa as informações em um arquivo de configuração chamado global.asa para inicializar sessões de usuário.
title: Editar o arquivo de configuração da sessão
uuid: c1bcd4d2-9bf5-425a-bda2-7f805983cdc6
exl-id: 98cf2e11-afb8-4530-aaa4-ea3c913effc1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---

# Editar o arquivo de configuração da sessão{#edit-the-session-configuration-file}

{{eol}}

O Portal de relatórios usa as informações em um arquivo de configuração chamado global.asa para inicializar sessões de usuário.

Ao instalar [!DNL Report Portal], edite esse arquivo conforme indicado. O [!DNL global.asa] O arquivo reside na pasta \*PortalName*\PortalASP\.

>[!NOTE]
>
>Não altere nenhum outro parâmetro neste arquivo de configuração.

1. Na máquina em que o IIS está em execução, abra o [!DNL global.asa] em um editor de texto, como o Bloco de notas.
1. Opcional. Para permitir que os usuários acessem [!DNL Report Portal] sem autenticação, altere o valor do parâmetro Session(&quot;In&quot;) para true. O padrão é false, que autentica todos os usuários que tentam acessar [!DNL Report Portal].
1. Se o seu [!DNL Report Portal] for instalado em uma unidade diferente da unidade C, altere o valor do parâmetro Session(&quot;Drive&quot;) para o local correto da unidade.
1. Para o parâmetro Session(&quot;DBPath&quot;) , altere o valor para refletir o caminho para o banco de dados que contém as informações necessárias para autenticar [!DNL Report Portal] usuários. Não inclua a letra da unidade, mas certifique-se de incluir uma barra à direita.

   Exemplo: [!DNL /Inetpub/wwwroot/Portal/data/]

1. Salve o arquivo.
1. Para verificar se a variável [!DNL Report Portal] Os arquivos foram instalados corretamente e podem ser acessados por meio de seu diretório virtual designado, abra a seguinte página no navegador:

   https://*YourServerAddress*/*YourPortalName*

   Exemplo: [!DNL https://localhost/VisualReportPortal]

   Se a variável [!DNL Report Portal] Os ASPs foram instalados corretamente, você deve ver a página de logon do portal. Se você não vir esta página, verifique se os ASPs estão ativados no IIS e verifique novamente os mapeamentos de diretório virtual.
