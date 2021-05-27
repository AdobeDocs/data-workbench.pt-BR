---
description: A Adobe usa certificados digitais X.509 para identificar e autenticar os componentes cliente e servidor que compõem uma implementação.
title: Compreender os certificados digitais
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
exl-id: 967e9d5b-7972-497e-8902-8db0eb304f27
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 54%

---

# Compreender os certificados digitais{#understanding-digital-certificates}

A Adobe usa certificados digitais X.509 para identificar e autenticar os componentes cliente e servidor que compõem uma implementação.

Ao instalar [!DNL Report Server], você deve instalar o certificado digital que autoriza um indivíduo nomeado (por exemplo, Jane Smith) a usar o aplicativo cliente instalado.

>[!NOTE]
>
>Se precisar migrar [!DNL Report Server] para outra máquina ou outro usuário nomeado, obtenha um novo certificado do Adobe. Para isso, entre em contato com o Atendimento ao cliente da Adobe.

[!DNL Report Server] O apresenta este certificado digital para obter acesso a um componente de servidor. Um administrador do componente de servidor pode restringir o acesso aos recursos do servidor com base no nome comum ou nos valores da unidade organizacional exibidos no certificado do cliente.

Os certificados digitais X.509 instalados com aplicativos Adobe também permitem que os componentes cliente e servidor troquem informações por SSL (Secure Sockets Layer). O SSL protege as transmissões via HTTP usando um sistema de criptografia de chave pública e privada. A implementação do SSL pela Adobe é compatível com chaves RSA de 1024 bits e usa um algoritmo de criptografia RC4 de 128 bits.

Além da segurança, o certificado digital que você instala também funciona como uma chave de licença que permite executar o [!DNL Report Server] instalado. Para funcionar adequadamente, um certificado digital deve ser atual e bloqueado por nó, caso contrário o aplicativo não será iniciado.

## Certificados bloqueados por nó {#section-3338f1558e7844888dced8f395888744}

Um certificado bloqueado por nó é um certificado digital que foi registrado na máquina na qual está instalado. O bloqueio de nó associa permanentemente um certificado a um identificador de nó específico (um valor que identifica exclusivamente uma máquina específica). Para que o nó bloqueie o certificado, a máquina deve ter acesso à Internet ao Adobe License Server ou a um servidor proxy que tenha acesso ao License Server.

Se estiver instalando em uma máquina que não acesse a Internet, obtenha e instale um certificado especial pré-bloqueado, conforme descrito em [Usar certificados digitais em computadores sem acesso à Internet](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) nesta página.

Se estiver instalando em uma máquina que possa acessar a Internet, o certificado digital será bloqueado automaticamente no nó na primeira vez que você iniciar [!DNL Report Server]. Depois do bloqueio por nó, o certificado não pode ser usado em outra máquina. Se precisar migrar [!DNL Report Server] para outra máquina, obtenha um certificado novo e desbloqueado do Adobe.

## Certificados atuais {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Além do bloqueio por nó, um certificado digital deve estar atualizado. Para permanecer atual, o certificado deve ser revalidado regularmente (geralmente a cada 30 dias, mas pode variar dependendo do contrato com o Adobe). Se o computador tiver acesso à Internet, o processo de revalidação será totalmente transparente. [!DNL Report Server] O se conecta automaticamente ao License Server e revalida o certificado quando necessário. Se o computador não tiver acesso à Internet, será necessário instalar manualmente os certificados atualizados, conforme descrito na seção a seguir.

## Usar certificados digitais em máquinas sem acesso à Internet {#section-18cce05e2204407bb2b6b75deab9197d}

Se a instalação for em uma máquina sem acesso à Internet, solicite um certificado pré-bloqueado para a instalação do [!DNL Report Server]. Um certificado pré-bloqueado é um certificado digital que é bloqueado manualmente pela Adobe para o identificador de nó do computador.

Para solicitar um certificado pré-bloqueado, envie o identificador do nó e o número do certificado para o Atendimento ao cliente da Adobe. Para obter o identificador de nó da máquina, entre em contato com o Atendimento ao cliente do Adobe para solicitar o utilitário Adobe [!DNL Node Identifier]. Você também pode obter o identificador do nó a partir do alerta que [!DNL Report Server] causa problemas ao tentar se conectar ao License Server e não conseguir. Ao receber o certificado pré-bloqueado, instale-o conforme descrito nas duas últimas etapas de [Procedimentos de instalação de certificados digitais](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d).

Quando o certificado precisar ser revalidado, baixe um novo certificado validado do License Server e reinstale-o no computador (a menos que o contrato com o Adobe diga o contrário).
