---
description: Etapas para editar contas de usuário existentes.
title: Editar usuários existentes
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
exl-id: cfbc54d8-16b4-4629-b556-a2aa4ee0c606
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 3%

---

# Editar usuários existentes{#editing-existing-users}

Etapas para editar contas de usuário existentes.

1. No [!DNL Report Portal], clique na guia **[!UICONTROL Admin]**. A página [!DNL Admin] é exibida.

   ![](assets/report_admintag2.png)

1. Clique na carta que representa a primeira letra do nome da conta que deseja editar. Por exemplo, se você quiser editar a conta &quot;Marketing&quot;, clique na letra &quot;M&quot;.

   Uma lista dos nomes das contas que começam com essa carta é exibida.

1. Selecione o nome da conta que deseja editar e clique no botão **[!UICONTROL select]**. A página [!DNL Edit Account Info] é exibida.

   ![Informações da etapa](assets/rptPort_scrn_AdminTab_editUser.png)

1. Altere apenas os campos desta página que precisam ser atualizados. A tabela a seguir fornece descrições de cada um desses campos:

   | Neste campo . . . | Especificar . . . |
   |---|---|
   | email | O endereço de email do usuário. |
   | senha antiga | A senha atual, que é necessária para prosseguir ao editar uma conta de administrador ou ao redefinir a senha de uma conta de não administrador. |
   | nova senha | A nova senha que o usuário deve fornecer ao fazer logon em [!DNL Report Portal]. |
   | confirmar senha | A nova senha que o usuário deve fornecer ao fazer logon em [!DNL Report Portal]. |
   | acesso ao perfil | Os perfis que este usuário tem permissão para acessar (por exemplo, ProductSales). Para permitir o acesso a vários perfis, separe os nomes por vírgulas. Se o usuário tiver permissão para acessar todos os perfis associados a [!DNL Report Portal], digite &quot;ALL&quot;. |
   | acesso à guia | As guias que este usuário tem permissão para acessar (por exemplo, [!DNL Admin]). Para permitir o acesso a várias guias, separe os nomes por vírgulas. Se o usuário tiver permissão para acessar todas as guias no [!DNL Report Portal], digite &quot;ALL&quot;. Esse campo, juntamente com o campo de tipo de conta, é muito útil para definir direitos de acesso de grupo. |
   | tipo de conta | Se esta conta é para um indivíduo ou um grupo. As contas individuais permitem que os usuários redefinam suas senhas, enquanto os grupos não. Um administrador é a única pessoa capaz de redefinir a senha de uma conta de grupo. |
   | status | Se esta conta está ativa ou inativa. O valor padrão está ativo. Para desativar uma conta de usuário, selecione **[!UICONTROL inactive]**. |
   | admin | Permitir que este usuário crie, atualize e exclua contas de usuário, bem como editar notas associadas a cada relatório. A configuração padrão é false. Para tornar este um usuário administrador, selecione true. |
   | data de expiração | A data, no formato MM/DD/AAAA, até a qual este usuário tem permissão para usar [!DNL Report Portal]. |

1. Clique em **[!UICONTROL update]**.
