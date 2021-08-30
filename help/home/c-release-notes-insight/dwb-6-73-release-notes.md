---
description: Novos recursos e correções no Data Workbench 6.73.
title: Notas de versão do Data Workbench 6.73
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
exl-id: 911c0cb7-ad95-4dbb-90ff-8e5c40b19f7f
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 26%

---

# Notas de versão do Data Workbench 6.73{#data-workbench-release-notes}

Novos recursos e correções no Data Workbench 6.73.

## Correções {#section-160baf6ea04c45a993777ee4260691ed}

* Correção de um problema na Workstation que impedia que usuários fizessem logon em alguns hardwares com alta resolução e alta taxa de DPI.
* Correção de um problema no servidor em que Email estava ausente nos nomes de arquivo do Arquivo ao usar o logon IMS.
* Atualização do OpenSSL para a versão 1.1.0h, que inclui várias correções de vulnerabilidade e novas Cifras SSL.
* Atualização das bibliotecas de código aberto listadas abaixo para as versões estáveis mais recentes

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Adição de registro de erro quando a contagem de linhas do arquivo de Pesquisa excede o limite suportado de 357913908 linhas.

## Problema conhecido {#section-f2cb932f6225457a872fb916a78df89a}

* A Data Workbench Workstation versão 6.73 não se conecta aos Servidores Data Workbench versões 6.61 e posteriores. O motivo é que as versões mais antigas do servidor usam uma forma fraca de cifras não suportadas na versão 6.73. Para habilitar o suporte para versões mais antigas

   1. Substitua a lista de Cifras SSL padrão no servidor com uma lista de cifras forte suportada pelo OpenSSL versão 1.0.1h. Para substituir, adicione as chaves &quot;Ciphers SSL&quot; nos arquivos &quot;Communications.cfg&quot; disponíveis nos diretórios &quot;Components&quot; e &quot;Components for Processing Servers&quot;. Por exemplo: `SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >Verifique se a chave está colocada no mesmo nível da porta SSL. Para obter detalhes, consulte [Configurações de Comunicação](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. Coloque o arquivo trust_ca_cert.pem mais recente no servidor 6.61 e em servidores mais antigos. Esta configuração se aplica a todas as versões da Workstation 6.7x.

Consulte [notas de versão arquivadas](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) para a Data Workbench 5.3 a 5.52.
