---
description: A Adobe usa certificados digitais X.509 para identificar e autenticar os componentes cliente e servidor que compõem uma implementação.
solution: Analytics
title: Noções básicas sobre certificados digitais
topic: Data workbench
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Noções básicas sobre certificados digitais{#understanding-digital-certificates}

A Adobe usa certificados digitais X.509 para identificar e autenticar os componentes cliente e servidor que compõem uma implementação.

Ao instalar [!DNL Report Server], você deve instalar o certificado digital que autoriza um indivíduo nomeado (por exemplo, Jane Smith) a usar o aplicativo cliente instalado.

>[!NOTE]
>
>Se precisar migrar [!DNL Report Server] para outra máquina ou outro usuário nomeado, você deverá obter um novo certificado da Adobe. Para fazer isso, entre em contato com o Atendimento ao cliente da Adobe.

[!DNL Report Server] apresenta este certificado digital para obter acesso a um componente de servidor. Um administrador do componente de servidor pode restringir o acesso aos recursos do servidor com base no nome comum ou nos valores da unidade organizacional exibidos no certificado do cliente.

Os certificados digitais X.509 instalados com aplicativos Adobe também permitem que os componentes cliente e servidor troquem informações por SSL (Secure Sockets Layer). O SSL protege as transmissões via HTTP usando um sistema de criptografia de chave pública e privada. A implementação do SSL pela Adobe suporta chaves RSA de 1024 bits e usa um algoritmo de criptografia RC4 de 128 bits.

Além da segurança, o certificado digital que você instala também funciona como uma chave de licença que permite que você execute o certificado instalado [!DNL Report Server]. Para funcionar corretamente, um certificado digital deve ser bloqueado por nó e atual, ou o aplicativo não será iniciado.

## Certificados bloqueados por nó {#section-3338f1558e7844888dced8f395888744}

Um certificado bloqueado por nó é um certificado digital que foi registrado na máquina em que está instalado. O bloqueio de nó associa permanentemente um certificado a um identificador de nó específico (um valor que identifica exclusivamente uma máquina específica). Para que o nó bloqueie seu certificado, sua máquina deve ter acesso à Internet ao Adobe License Server ou a um servidor proxy que tenha acesso ao License Server.

Se estiver instalando em uma máquina que não pode acessar a Internet, você deverá obter e instalar um certificado especial pré-bloqueado, conforme descrito em [Usando certificados digitais em computadores sem acesso](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) à Internet nesta página.

Se você estiver instalando em uma máquina que possa acessar a Internet, seu certificado digital será bloqueado automaticamente no nó na primeira vez que você iniciar [!DNL Report Server]. Depois de ser bloqueado por nó, o certificado não pode ser usado em qualquer outra máquina. Se precisar migrar [!DNL Report Server] para outra máquina, você deverá obter um certificado novo e desbloqueado da Adobe.

## Certificados atuais {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Além de estar bloqueado por nó, um certificado digital deve estar atualizado. Para permanecer atualizado, seu certificado deve ser revalidado regularmente (geralmente a cada 30 dias, mas pode variar dependendo do acordo com a Adobe). Se o computador tiver acesso à Internet, o processo de revalidação será completamente transparente. [!DNL Report Server] conecta-se automaticamente ao License Server e revalida o certificado quando necessário. Se o computador não tiver acesso à Internet, será necessário instalar manualmente os certificados atualizados conforme descrito na seção a seguir.

## Usando certificados digitais em máquinas sem acesso à Internet {#section-18cce05e2204407bb2b6b75deab9197d}

Se estiver instalando em uma máquina que não pode acessar a Internet, você deverá solicitar um certificado pré-bloqueado para a instalação do [!DNL Report Server]. Um certificado pré-bloqueado é um certificado digital que a Adobe bloqueia manualmente para o identificador de nó do computador.

Para solicitar um certificado pré-bloqueado, é necessário enviar o identificador do nó e o número do certificado para o Atendimento ao cliente da Adobe. Para obter o identificador de nó do computador, entre em contato com o Atendimento ao cliente da Adobe para solicitar o utilitário da Adobe [!DNL Node Identifier] . Você também pode obter o identificador do nó do alerta que [!DNL Report Server] ocorre quando ele tenta se conectar ao License Server e não pode. Ao receber o certificado pré-bloqueado, instale-o conforme descrito nas duas últimas etapas de Procedimentos [de instalação de certificados](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d)digitais.

Quando o certificado precisar ser revalidado, você deverá baixar um novo certificado validado do License Server e reinstalá-lo em seu computador (a menos que seu contrato com a Adobe indique o contrário).
