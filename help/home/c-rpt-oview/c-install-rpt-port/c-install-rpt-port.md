---
description: Para usar o Portal de relatórios, você deve instalar e configurar um conjunto de páginas do servidor de aplicativos (ASPs) no IIS.
solution: Analytics
title: Instalação do portal de relatórios
topic: Data workbench
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalação do portal de relatórios{#installing-the-report-portal}

Para usar o Portal de relatórios, você deve instalar e configurar um conjunto de páginas do servidor de aplicativos (ASPs) no IIS.

**Antes de começar**

Os procedimentos neste capítulo descrevem como instalar e configurar [!DNL Report Portal]. Para concluir esses procedimentos, você deve:

* Tenha o Microsoft IIS instalado e saiba sua versão.
* Conheça os nomes dos conjuntos de relatórios cujos relatórios são exibidos por [!DNL Report Portal].
* Saiba o local do diretório no qual [!DNL Report Server] salva a saída desses conjuntos de relatórios. Verifique se o servidor de aplicativos IIS tem acesso a esse diretório.

>[!NOTE]
>
>* Para serem exibidos usando [!DNL Report Portal], os relatórios devem seguir convenções de nomenclatura específicas. Além disso, o diretório no qual os relatórios são salvos deve seguir uma estrutura prescrita. Para obter uma descrição desses requisitos, consulte [Verificar se seus conjuntos de relatórios são compatíveis com o Portal de relatórios...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* As senhas no portal de relatórios agora são compatíveis com AES-256 bits. Se você estiver atualizando para o Portal de relatórios 2.0, aumente o campo Tamanho do campo para senha de 50 para 150 no banco de dados **users.mdb** . É necessário aumentar o tamanho do campo para acomodar senhas com criptografia atualizada.
>* Se você estiver atualizando para o Portal de relatórios 2.0, aumente o Tamanho do campo para o campo **Senha** de 50 para 150 no banco de dados users.mdb. É necessário aumentar o tamanho do campo para acomodar senhas com criptografia atualizada.
>* O Portal de relatórios agora apresenta algoritmos de hash mais fortes com suporte a salting. Se você estiver atualizando para o Portal de **Relatório 2.1**, adicione um novo campo de Texto, *SenhaSal* com 20 caracteres no tamanho do campo no [!DNL users.mdb]banco de dados. Este campo é necessário para armazenar o sal da senha.
>



