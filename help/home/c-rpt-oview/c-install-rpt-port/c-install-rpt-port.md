---
description: Para usar o portal de relatórios, você deve instalar e configurar um conjunto de páginas do servidor de aplicativos (ASPs) no IIS.
title: Instalar o portal de relatórios
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Instalar o portal de relatórios{#installing-the-report-portal}

Para usar o portal de relatórios, você deve instalar e configurar um conjunto de páginas do servidor de aplicativos (ASPs) no IIS.

**Antes de começar**

Os procedimentos neste capítulo descrevem como instalar e configurar [!DNL Report Portal]. Para concluir esses procedimentos, você deve:

* Ter o Microsoft IIS instalado e saber sua versão.
* Saiba os nomes dos conjuntos de relatórios cujos relatórios são exibidos por [!DNL Report Portal].
* Saiba o local do diretório em que [!DNL Report Server] salva a saída desses conjuntos de relatórios. Certifique-se de que o servidor de aplicativos do IIS tenha acesso a esse diretório.

>[!NOTE]
>
>* Para serem exibidos usando [!DNL Report Portal], os relatórios devem seguir convenções de nomenclatura específicas. Além disso, o diretório em que os relatórios são salvos deve seguir uma estrutura prescrita. Para obter uma descrição desses requisitos, consulte [Garantir que seus conjuntos de relatórios sejam compatíveis com o portal de relatórios...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* As senhas no portal de relatórios agora são compatíveis com AES-256 bits. Se estiver atualizando para o portal de relatórios 2.0, aumente o campo Tamanho do campo para senha de 50 para 150 no banco de dados **users.mdb**. O aumento do tamanho do campo é necessário para acomodar senhas com criptografia atualizada.
>* Se estiver atualizando para o portal de relatórios 2.0, aumente o tamanho do campo para o campo **Password** de 50 para 150 no banco de dados users.mdb. O aumento do tamanho do campo é necessário para acomodar senhas com criptografia atualizada.
>* O portal de relatórios agora apresenta algoritmos de hash mais fortes com suporte para salting. Se estiver atualizando para **Portal de relatórios 2.1**, adicione um novo campo de texto, *Senha* com tamanho de campo de 20 caracteres no banco de dados [!DNL users.mdb]. Este campo é necessário para armazenar o sal da senha.

>


