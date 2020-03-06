---
description: Novos recursos e correções no Análise de big data 6.73.
title: Notas de versão do Análise de big data 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Notas de versão do Análise de big data 6.73{#data-workbench-release-notes}

Novos recursos e correções no Análise de big data 6.73.

## Notas de versão do Análise de big data 6.73 {#topic-7655534554ac4a4b816af1bd73b06aad56757}

Novos recursos e correções no Análise de big data 6.73.

## Correções {#section-160baf6ea04c45a993777ee4260691ed}

* Correção de um problema na Workstation que impedia que usuários fizessem logon em alguns hardwares com alta resolução e alta taxa de DPI.
* Correção de um problema no servidor em que o email estava ausente nos nomes de arquivos do Arquivo morto ao usar o logon do IMS.
* Atualização do OpenSSL para a versão 1.1.0h, que inclui várias correções de vulnerabilidade e novas Cifras SSL.
* As bibliotecas de código aberto listadas abaixo foram atualizadas para as versões estáveis mais recentes

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Adição de registro de erro quando a contagem de linhas do arquivo de Pesquisa excede o limite suportado de 357913908 linhas.

## Known issue {#section-f2cb932f6225457a872fb916a78df89a}

* A versão 6.73 da Análise de big data não se conecta aos servidores da Análise de big data versão 6.61 e anteriores. O motivo é que as versões mais antigas do servidor usam uma forma fraca de cifras não suportadas na versão 6.73. Para ativar o suporte para versões mais antigas

   1. Substitua a lista de Ciphers SSL padrão no servidor com uma lista de criptografia forte suportada pelo OpenSSL versão 1.0.1h. Para substituir, adicione a chave ‘Ciphers SSL’ nos arquivos ‘Communications.cfg’ disponíveis nos diretórios ‘Components’ e ‘Components for Processing Servers’. Por exemplo: `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Verifique se a chave está colocada no mesmo nível da Porta SSL. Para obter detalhes, consulte Configurações de [comunicações](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Coloque o arquivo trust_ca_cert.pem mais recente no servidor 6.61 e em servidores mais antigos. Esta configuração se aplica a todas as versões do Workstation 6.7x.

Consulte as notas [de versão](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) arquivadas da Análise de big data 5.3 a 5.52.
