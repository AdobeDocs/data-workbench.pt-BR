---
description: Atualização de segurança para o portal de relatórios da análise de big data.
title: Portal de relatórios do DWB 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Portal de relatórios do DWB 2.1{#dwb-report-portal}

Atualização de segurança para o portal de relatórios da análise de big data.

**Atualização de segurança importante**

O Portal de relatórios agora apresenta algoritmos de hash mais fortes com suporte a salting. Se você estiver atualizando para o Portal de relatórios 2.1, adicione um novo campo de texto, PasswordSal com 20 caracteres no tamanho do campo no banco de dados users.mdb. Este campo é necessário para armazenar o sal da senha.
