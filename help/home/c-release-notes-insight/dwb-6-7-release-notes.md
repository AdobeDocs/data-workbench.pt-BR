---
description: Novos recursos, correções e problemas conhecidos no Data Workbench 6.7.
title: Notas de versão do Data Workbench 6.7
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
exl-id: e5ec3224-66d1-47a6-9bf3-8be9f6568b8d
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 34%

---

# Notas de versão do Data Workbench 6.7{#data-workbench-release-notes}

Novos recursos, correções e problemas conhecidos no Data Workbench 6.7.

## Notas de versão do Data Workbench 6.7 {#topic-7655534554ac4a4b816af1bd73b06aad}

Novos recursos, correções e problemas conhecidos no Data Workbench 6.7.

## Novos recursos na versão 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Novo modelo de autenticação para a estação de trabalho de análise de big data (integração IMS)**

A estação de trabalho de análise de big data suporta autenticação de usuário por meio do nome de usuário e senha. Com esse novo método, os administradores podem criar e gerenciar suas próprias contas de usuário, eliminando a necessidade de entrar em contato com o Atendimento ao cliente.

Para obter mais informações, consulte [Auto-provisionamento de usuários](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html).

**Pesquisa de arquivo simples**

A estação de trabalho de análise de big data suporta autenticação de usuário por meio do nome de usuário e senha. Com esse novo método, os administradores podem criar e gerenciar suas próprias contas de usuário, eliminando a necessidade de entrar em contato com o Atendimento ao cliente.

Anteriormente, a pesquisa de arquivo simples carregava todo o arquivo para buffers em memória, aumentando o uso de memória e criando problemas de desempenho em outros subsistemas. Agora, os arquivos podem ter a memória mapeada e serem armazenados em cache no Windows, otimizando o uso de memória ao definir *Arquivos de pesquisa com memória mapeada* como verdadeiro no [!DNL MemorySettings.cfg].

Para obter mais informações, consulte [Auto-provisionamento de usuários](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-self-provisioning-users.html).

**Uso de memória**

O uso de Página grande agora pode ser desativado ao definir *Usar páginas grandes* como falso em [!DNL MemorySettings.cfg]. Consulte [Monitoramento de uso de memória](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html) para obter mais informações.

**Codificações de segurança**

Suporte adicionado para ECDHE e DHE.

Suporte de email em [!DNL User List.cfg]

Adição de suporte para o atributo Email em [!DNL User List.cfg]. Para obter mais informações, consulte [Administração de usuário dos membros do grupo](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html?lang=en).

**Menu de ajuda**

O menu Ajuda mostra um atalho para o diretório Abrir certificados.

**`TargetBulkUpload`exportar**

Os URLs serão fornecidos no final do arquivo de rastreamento da exportação e do arquivo `targetbulkuploadexportname.log.completed` para rastrear o registro de lotes paralisados.

Um novo arquivo, [!DNL TargetBulkUpload.cfg], foi fornecido para configurar o intervalo de Limite de tempo máximo (em minutos). O arquivo é encontrado em [!DNL Server\Admin\Export\].

## Correções {#section-160baf6ea04c45a993777ee4260691ed}

* Correção de um problema em que a dimensão Click-through da campanha exibia valores inflados.
* Correção de um problema com a geração de arquivos excel do servidor de relatório.
* A cifra RC4 agora está desativada por padrão.
* Correção de um problema que resultava em falha da estação de trabalho do Data Workbench ao adicionar um elemento de dimensão a uma tabela de legenda de valor.
* Correção de um problema com o Data Workbench para AAM exportações que estava causando tempos limite.
* Correção de um problema que resultava em falha na estação de trabalho do Data Workbench quando um usuário sem nível de acesso suficiente salvava o espaço de trabalho para Servidor.
* Correção de um problema em que o formato de data em [!DNL report.cfg] estava incorreto ou não estava localizado.
* Correção de um problema com as linhas de dispositivo móvel e de produto no feed AVRO exibindo informações confusas.
* Correção de um problema que impedia a ordem de arquivos `*.1cd` e `*.1ad` em [!DNL order.txt].

* A opção Enviar para servidor foi desativada para o algoritmo de Maximização de expectativa ao executar o Clustering.
* Correção de um problema com a paralisação do executável `TargetBulkUpload` e a falha na execução completa.

## Problemas conhecidos {#section-d76322bdac5043f087ab303dc68b8fff}

* Ao fazer logoff, o arquivo [!DNL user cache.db] é limpo.
* Não há suporte para endereços de email de usuário IMS contendo caracteres &#39;+&#39; ou &#39;%&#39;.
* O usuário não pode fazer logoff durante um erro no status da conexão. Como solução alternativa, faça logout no modo offline.
* A janela de login do IMS não é renderizada corretamente em alguns hardwares com alta resolução e alta DPI. Como solução alternativa, clique com o botão direito do mouse em [!DNL Insight.exe] e navegue até **[!UICONTROL Properties]** > **[!UICONTROL Compatability]** e marque a caixa **[!UICONTROL Override high DPI scaling behavior]**.

## Requisitos de atualização {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Atualize [!DNL trust_ca_cert.pem] nos Servidores Insight que fazem parte do pacote de compilação.
1. Atualize o certificado do Servidor e do Servidor de Relatório baixando novos certificados de [https://aap.adobe.com](https://aap.adobe.com).
1. Para atualizar automaticamente a estação de trabalho e o servidor de relatórios, atualize [!DNL trust_ca_cert.pem] manualmente para ambos baixando-os do servidor de licenças.
1. O recurso de atualização automática do sensor requer a versão 5.0 para se comunicar com o Insight Server versão 6.70. Além disso, o [!DNL trust_ca_cert.pem] do sensor deve ser atualizado manualmente baixando-o do License Server.

## Atualizações do sistema {#section-c1b4949ea734440aa62658ac313261db}

Os novos arquivos incluem:

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

Os arquivos atualizados incluem:

1. [!DNL trust_ca_cert.pem] para todos os componentes.
1. [!DNL Access Control.cfg] para suportar a configuração IMS.
1. [!DNL Base\Context\meta.cfg] para obter suporte aos formatos Data inicial e Data final em  [!DNL Report.cfg]

1. Adições a [!DNL Insight.cfg] para suportar proxy para autenticação IMS:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Consulte [notas de versão arquivadas](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) para a Data Workbench 5.3 a 5.52.
