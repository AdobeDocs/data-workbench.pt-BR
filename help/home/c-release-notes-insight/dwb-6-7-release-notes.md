---
description: Novos recursos, correções e problemas conhecidos no Análise de big data 6.7.
title: Notas de versão do Análise de big data 6.7
uuid: b84f5f2b-4f1c-490c-982b-6bd8d3a63e25
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Notas de versão do Análise de big data 6.7{#data-workbench-release-notes}

Novos recursos, correções e problemas conhecidos no Análise de big data 6.7.

## Notas de versão do Análise de big data 6.7 {#topic-7655534554ac4a4b816af1bd73b06aad}

Novos recursos, correções e problemas conhecidos no Análise de big data 6.7.

## Novos recursos da versão 6.7 {#section-8bd7a36ac3a24b8497a9ea9724e0d750}

**Novo modelo de autenticação para a estação de trabalho de análise de big data (integração IMS)**

A estação de trabalho de análise de big data suporta autenticação de usuário por meio do nome de usuário e senha. Com esse novo método, os administradores podem criar e gerenciar suas próprias contas de usuário, eliminando a necessidade de entrar em contato com o Atendimento ao cliente.

Para obter mais informações, consulte [Auto-provisionamento de usuários](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html).

**Pesquisa de arquivo simples**

A estação de trabalho de análise de big data suporta autenticação de usuário por meio do nome de usuário e senha. Com esse novo método, os administradores podem criar e gerenciar suas próprias contas de usuário, eliminando a necessidade de entrar em contato com o Atendimento ao cliente.

Anteriormente, a pesquisa de arquivo simples carregava todo o arquivo para buffers em memória, aumentando o uso de memória e criando problemas de desempenho em outros subsistemas. Agora, os arquivos podem ter a memória mapeada e serem armazenados em cache no Windows, otimizando o uso de memória ao definir *Arquivos de pesquisa com memória mapeada* como verdadeiro no [!DNL MemorySettings.cfg].

Para obter mais informações, consulte [Auto-provisionamento de usuários](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-self-provisioning-users.html).

**Uso de memória**

Large Page usage can now be disabled by setting *Use Large Pages* to false in [!DNL MemorySettings.cfg]. Consulte [Monitoramento de uso de memória](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/admin-dwb-server/t-mntr-mry-usg.html) para obter mais informações.

**Codificações de segurança**

Suporte adicionado para ECDHE e DHE.

Email support in [!DNL User List.cfg]

Added support for Email attribute in [!DNL User List.cfg]. Para obter mais informações, consulte [Administração de usuário dos membros do grupo](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/admin-dwb-server/access-control/dwb-self-admin-member-access.html).

**Menu de ajuda**

O menu Ajuda mostra um atalho para o diretório Abrir certificados.

**`TargetBulkUpload`exportar **

Os URLs serão fornecidos no final do arquivo de rastreamento da exportação e do arquivo `targetbulkuploadexportname.log.completed` para rastrear o registro de lotes paralisados.

Um novo arquivo, [!DNL TargetBulkUpload.cfg], foi fornecido para configurar o intervalo de Limite de tempo máximo (em minutos). O arquivo foi encontrado em [!DNL Server\Admin\Export\].

## Correções {#section-160baf6ea04c45a993777ee4260691ed}

* Corrigido um problema no qual a dimensão de click-through de campanha exibia valores inflados.
* Correção de um problema com a geração de arquivos do Excel a partir do servidor de relatório.
* A codificação RC4 agora está desativada por padrão.
* Correção de um problema que resultava em falha da estação de trabalho Análise de big data ao adicionar um elemento de dimensão a uma tabela de legenda de valor.
* Correção de um problema com exportações do Análise de big data para o AAM que causava tempos limite.
* Correção de um problema que resultava em falha da estação de trabalho Análise de big data quando um usuário sem nível de acesso suficiente salvava o espaço de trabalho no Servidor.
* Correção de um problema que fazia com que o formato de data [!DNL report.cfg] estivesse incorreto ou não estivesse localizado.
* Correção de um problema que fazia com que linhas móveis e de produtos no feed AVRO exibissem informações confusas.
* Correção de um problema que impedia a ordem de `*.1cd` e `*.1ad` arquivos em [!DNL order.txt].

* A opção Enviar para o servidor foi desativada para o algoritmo de Maximização de expectativas durante a execução de Clustering.
* Correção de um problema com o `TargetBulkUpload` executável que parava e falhava ao ser executado completamente.

## Problemas conhecidos {#section-d76322bdac5043f087ab303dc68b8fff}

* Ao sair, o [!DNL user cache.db] arquivo é limpo.
* Não há suporte para endereços de email de usuário IMS que contenham caracteres &#39;+&#39; ou &#39;%&#39;.
* O usuário não consegue fazer logout durante um erro no status da conexão. Como solução, faça logout no modo offline.
* A janela de logon IMS não é renderizada corretamente em algum hardware com alta resolução e alta DPI. Como solução, clique com o botão direito do mouse em [!DNL Insight.exe] e navegue até **[!UICONTROL Properties]** > **[!UICONTROL Compatability]** e marque a caixa **[!UICONTROL Override high DPI scaling behavior]**.

## Requisitos de atualização {#section-b74adf981ac8446a8d7ffcdc4e9cf939}

1. Atualize [!DNL trust_ca_cert.pem] os servidores Insight que fazem parte do pacote de compilação.
1. Atualize o certificado do Servidor e do Servidor de relatórios baixando novos certificados em [https://aap.adobe.com](https://aap.adobe.com).
1. Para atualizar automaticamente a estação de trabalho e o servidor de relatórios, atualize manualmente [!DNL trust_ca_cert.pem] para ambos baixando-os do servidor de licenças.
1. O recurso de atualização automática do sensor requer a versão 5.0 para se comunicar com o Insight Server versão 6.70. Além disso, o Sensor [!DNL trust_ca_cert.pem] deve ser atualizado manualmente baixando-o do License Server.

## Atualizações do sistema {#section-c1b4949ea734440aa62658ac313261db}

Os novos arquivos incluem:

1. [!DNL Server\Admin\Export\TargetBulkUpload.cfg]
1. [!DNL Server\Components for Processing Servers\MemorySettings.cfg]
1. [!DNL Server\Components\MemorySettings.cfg]

Os arquivos atualizados incluem:

1. [!DNL trust_ca_cert.pem] para todos os componentes.
1. [!DNL Access Control.cfg] para suportar a configuração de IMS.
1. [!DNL Base\Context\meta.cfg] para suporte aos formatos Data inicial e Data final em [!DNL Report.cfg]

1. Adições para [!DNL Insight.cfg] suportar proxy para autenticação IMS:

   ```
   IMS Proxy Info = IMSProxyInfo: 
     Proxy Password = EncryptedString:
     Proxy User Name = string:
   ```

Consulte as notas [de versão](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) arquivadas da Análise de big data 5.3 a 5.52.
