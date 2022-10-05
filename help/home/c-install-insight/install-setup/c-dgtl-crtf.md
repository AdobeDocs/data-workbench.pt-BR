---
description: Depois de instalar os arquivos de programa Insight, baixe e instale o certificado digital fornecido a você pelo Adobe.
title: Download e instalação do certificado digital (Insight)
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
exl-id: 0dff95ae-880b-45d5-96df-4eb6bea58891
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2744'
ht-degree: 39%

---

# Download e instalação do certificado digital{#downloading-and-installing-the-digital-certificate}

{{eol}}

Depois de instalar os arquivos de programa Insight, baixe e instale o certificado digital fornecido a você pelo Adobe.

## Download e instalação do certificado digital {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

Depois de instalar os arquivos de programa Insight, baixe e instale o certificado digital fornecido a você pelo Adobe.

## Compreender os certificados digitais {#concept-9eed01c8d95440cda6ce29d68e65098c}

A Adobe usa certificados digitais X.509 para identificar e autenticar os componentes cliente e servidor que compõem uma implementação.

<!--
c_undst_dgtl_crtf.xml
-->

Ao instalar o Insight, você deve instalar o certificado digital que autoriza um indivíduo nomeado (por exemplo, Jane Smith) a usar o aplicativo cliente instalado.

>[!NOTE]
>
>Se precisar migrar o Insight para outro computador ou outro usuário nomeado, obtenha um novo certificado do Adobe. Para isso, entre em contato com o Atendimento ao cliente da Adobe.

O Insight apresenta esse certificado digital para obter acesso a um componente de servidor. Um administrador de um componente de servidor pode restringir o acesso aos recursos do servidor com base no nome comum ou nos valores da unidade organizacional que aparecem no certificado do usuário.

Os certificados digitais X.509 instalados com aplicativos Adobe também permitem que os componentes cliente e servidor troquem informações por SSL (Secure Sockets Layer). O SSL protege as transmissões via HTTP usando um sistema de criptografia de chave pública e privada. A implementação do SSL pela Adobe é compatível com chaves RSA de 1024 bits e usa um algoritmo de criptografia RC4 de 128 bits.

Além da segurança, o certificado digital que você instala também funciona como uma chave de licença que permite executar o Insight. Para funcionar adequadamente, um certificado digital deve ser atual e bloqueado por nó, caso contrário o aplicativo não será iniciado.

## Certificados bloqueados por nó {#section-984aa8f2f5a1448cadc4afea978aedc9}

Um certificado bloqueado por nó é um certificado digital que foi registrado no computador em que está instalado. O bloqueio de nó associa permanentemente um certificado a um identificador de nó específico (um valor que identifica exclusivamente um computador específico). Para que o nó bloqueie o certificado, o computador deve ter acesso à Internet ao Adobe License Server ou a um servidor proxy que tenha acesso ao License Server.

Se estiver instalando em um computador que não acesse a Internet, obtenha e instale um certificado especial pré-bloqueado, conforme descrito em [Usar certificados digitais em computadores sem acesso à Internet](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1).

Se estiver instalando em um computador que possa acessar a Internet, o certificado digital será bloqueado automaticamente no nó na primeira vez que o Insight for iniciado. Após ser bloqueado por nó, o certificado não poderá ser usado em nenhum outro computador. Se precisar migrar o Insight para outro computador, obtenha um certificado novo e desbloqueado do Adobe.

## Certificados atuais {#section-0816b031df3e415ab3f0205b720c723e}

Além de ser bloqueado por nó, o certificado digital deve estar atualizado. Para permanecer atual, o certificado deve ser revalidado regularmente (geralmente a cada 30 dias, mas pode variar dependendo do contrato com a Adobe). Se o computador tiver acesso à Internet, o processo de revalidação será totalmente transparente. O Insight conecta-se automaticamente ao License Server e revalida o certificado quando necessário. Se o computador não tiver acesso à Internet, instale manualmente um certificado atualizado conforme descrito na seção a seguir.

## Usar certificados digitais em computadores sem acesso à Internet {#section-d3c060131d7f45cda27f68848b704fa1}

Se estiver instalando em um computador que não acesse a Internet, solicite um certificado pré-bloqueado para a instalação do Insight. Um certificado pré-bloqueado é um certificado digital que é bloqueado manualmente pelo Adobe para o identificador de nó do computador.

Para solicitar um certificado pré-bloqueado, envie o identificador do nó e o número do certificado para o Atendimento ao cliente do Adobe. Para obter o identificador de nó do computador, entre em contato com o Atendimento ao cliente do Adobe para solicitar o Adobe [!DNL Node Identifier] utilitário. Você também pode obter o identificador do nó a partir do alerta de que o Insight apresenta problemas ao tentar se conectar ao License Server e não conseguir. Ao receber o certificado pré-bloqueado, instale-o conforme descrito nas duas últimas etapas de [Instalar certificados digitais](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38).

Quando o certificado precisar ser revalidado, baixe um novo certificado validado do License Server e reinstale-o no computador (a menos que o contrato com o Adobe diga o contrário).

## Instalar certificados digitais {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**Para baixar e instalar o certificado digital**

1. Abra seu navegador da Web para [!DNL https:\\license.visualsciences.com].

   >[!NOTE]
   >
   >O navegador pode solicitar que você apresente um certificado digital neste momento. Se isso acontecer, clique em **[!UICONTROL Cancel]** para fechar a caixa de diálogo.

1. Na tela de logon, digite o [!DNL Account Name] e os [!DNL Password] que recebeu da Adobe e clique em **[!UICONTROL login]**.
1. Localize o certificado emitido para a sua instância do Insight ( *Seu nome*.pem) e clique no link ![](assets/btn_save_certificatedownload.PNG) ícone associado a esse certificado.
1. Quando solicitado a salvar o certificado, clique em **[!UICONTROL Save]**.
1. Baixe o arquivo para a [!DNL Certificates] no diretório em que você instalou o Insight.

   Esta pasta contém um arquivo de certificado chamado [!DNL trust_ca_cert.pem]. Ambos os arquivos de certificado devem estar sempre presentes para que o Insight funcione.

## Windows Certificate Store {#concept-4acb13b7de9340ea8cde8ad84b93358d}

O Windows Certificate Store permite que você armazene o certificado do cliente e a chave privada no Windows Certificate Store para comunicação SSL com servidores.

<!--
crypto-api.xml
-->

O Windows Certificate Store para o Cliente é um novo recurso que permite armazenar o certificado de comunicação SSL e a chave privada no Windows Certificate Store ao invés de no arquivo `Insight/Certificates/<CertName>.pem`. O uso do Windows Certificate Store pode ser preferível se você usar o armazenamento de certificados para outros aplicativos e desejar fazer o gerenciamento de certificados em um local, ou para usuários que desfrutam do registro de auditoria de logon adicional do Windows fornecido pelo Windows Certificate Store.

>[!NOTE]
>
>O licenciamento com o servidor de licenças ainda é mantido usando o arquivo `<Common Name>.pem` existente e o certificado obtido do armazenamento de certificados será usado apenas para comunicação com os servidores especificados.

## Pré-requisitos {#section-69b18600052145ff8e5299b7123e69c5}

1. Você deve ter acesso ao arquivo [!DNL certmgr.msc] com a capacidade de importar um certificado e uma chave para o armazenamento **Pessoal**. (O que deve ser verdadeiro por padrão para a maioria dos usuários do Windows.)

1. O usuário que faz a configuração deve ter uma cópia da ferramenta de linha de comando **OpenSSL**.
1. O servidor e o cliente já devem estar configurados para usar um certificado SSL personalizado, dando instruções para armazenar o certificado do cliente no Windows Certificate Store em vez de armazená-lo no **Certificados** diretório.

## Configurar o Windows Certificate Store {#section-3629802122e947d4b4f63e8b732cfe27}

Siga estas etapas para ativar o Windows Certificate Store:

**Etapa 1: importe o certificado SSL e a chave privada do usuário para o Windows Certificate Store.**

Em [Usar certificados personalizados no Data Workbench](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) você é direcionado a colocar o certificado SSL e a chave no seguinte diretório:

```
<
<filepath>
  DWB Install folder
</filepath>>\Certificates\
```

O nome do certificado é `<Common Name>.pem` como o Analytics Server 1.pem (não o arquivo trust_ca_cert.pem.)

Antes de ser possível importar o certificado e a chave privada, converta-os do formato .[!DNL pem] para um formato [!DNL .pfx], como [!DNL pkcs12.pfx]).

1. Abra um prompt de comando ou terminal e navegue até o diretório:

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
   ```

1. Execute [!DNL openssl] com os seguintes argumentos (com o nome real do arquivo [!DNL .pem]):

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Se solicitado, pressione **Enter** para ignorar a inserção de uma senha de exportação.

1. Execute [!DNL certmgr.msc] a partir do prompt de execução, do menu iniciar ou da linha de comando.
1. Abra o armazenamento de certificados **Pessoais** do usuário atual.

   ![](assets/6_5_crypto_api_0.png)

1. Clique com o botão direito do mouse em **Certificados** e em **Todas as Tarefas** > **Importar**.

   Verifique se a opção **Usuário atual** está selecionada e clique em **Avançar**.

   ![](assets/6_5_crypto_api_4.png)

1. Clique em **Procurar** e selecione o arquivo `<CommonName>.pfx` criado anteriormente. Altere a caixa suspensa de extensão de arquivo de um Certificado X.509 para o **Personal Information Exchange** ou para **Todos os arquivos** para visualizá-lo.

   Selecione o arquivo e clique em **Abrir** depois em **Avançar**.

1. Não digite uma senha e verifique se apenas as opções **Marcar essa chave como exportável** e **Incluir todas as propriedades estendidas** estão selecionadas.

   ![](assets/6_5_crypto_api_3.png)

   Clique em **Avançar**.

1. Certifique-se de que a opção **Colocar todos os certificados no seguinte armazenamento** esteja selecionada e que o armazenamento de certificados listado seja **Pessoal**. (Se você for um usuário avançado, poderá selecionar outro armazenamento nesse momento, mas altere a configuração posteriormente.)

1. Clique em **Avançar** e em **Concluir**. Você deve ver uma caixa de diálogo informando que a importação foi concluída e ver seu certificado na pasta Certificados do armazenamento.

   >[!NOTE]
   >
   >Preste atenção especial aos campos **Emitido para** e **Emitido por**. Você vai precisar deles na próxima etapa.

**Etapa 2: edite o arquivo Insight.cfg.**

Edite o arquivo [!DNL Insight.cfg] para direcionar o Data Workbench a usar o recurso Windows Certificate Store. Cada entrada de servidor neste arquivo deve ter alguns parâmetros adicionais especificados. Se os parâmetros forem omitidos, a estação de trabalho usará a configuração de certificado existente como padrão. Se especificar os parâmetros mas os valores forem incorretos, a estação de trabalho informará um estado de erro e você precisará consultar o arquivo de log para obter informações sobre os erros.

1. Abra o arquivo **Insight.cfg** (localizado no diretório de instalação do **Insight**).

1. Role para baixo até a entrada do servidor que você deseja configurar. Se quiser usar o Windows Certificate Store para cada servidor, faça essas modificações em cada entrada no vetor de objetos [!DNL serverInfo].
1. Adicione esses parâmetros ao seu arquivo [!DNL Insight.cfg]. Faça essa operação a partir da estação de trabalho ou manualmente adicionando os seguintes parâmetros ao objeto [!DNL serverInfo]. (Não esqueça de usar espaços ao invés de caracteres de tabulação e não cometa outros erros tipográficos ou de sintaxe neste arquivo. )

   ```
   SSL Use CryptoAPI = bool: true
   SSL CryptoAPI Cert Name = string: <Common Name>
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC
   SSL CryptoAPI Cert Store Name = string: My
   ```

   O booliano ativa ou desativa o recurso. O nome do certificado corresponde ao **Emissor para** no gerenciador de certificados. O nome do emissor do certificado corresponde a **Emitido por**, e o **Nome do armazenamento** deve corresponder ao nome do armazenamento do certificado.

   >[!NOTE]
   >
   >O nome “Pessoal” no Gerenciador de certificados (certmgr.msc) se refere ao armazenamento de certificados chamado **Meu.** Consequentemente, se você importar o certificado de comunicação SSL e a chave (.PFX) para o armazenamento de certificados **Pessoal** conforme recomendado, defina a cadeia de caracteres **SSL CryptoAPI Cert Store Name** como “Meu”. A definição deste parâmetro para &quot;Pessoal&quot; não funcionará. Esta é uma peculiaridade do Windows Certificate Store.

   Encontre uma lista completa dos armazenamentos de sistema predefinidos aqui: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Seu sistema pode ter armazenamentos de certificados adicionais. Se quiser usar um armazenamento diferente de “Pessoal”u (como **Me**), obtenha o nome canônico do armazenamento de certificados e coloque-o no arquivo [!DNL Insight.cfg]. (O nome do armazenamento do sistema “Meu” é chamado inconsistentemente de “Meu” e “MEU” na documentação do Windows. Aparentemente, o parâmetro não distingue entre maiúsculas e minúsculas.)

1. Depois de adicionar esses parâmetros e verificar se os valores correspondem à lista no Gerenciador de certificados do Windows, salve o arquivo [!DNL Insight.cfg].

Inicie agora a estação de trabalho (ou desconecte/reconecte ao servidor). O Data Workbench deve carregar o certificado e a chave do armazenamento de certificados e conectar-se normalmente.

## Saída de registro {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Quando um certificado não é encontrado ou é inválido, essa mensagem de erro é emitida para o arquivo [!DNL HTTP.log].

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>A estrutura de logon L4 pode ser ativada pela configuração do arquivo [!DNL L4.cfg] (consulte o gerente de conta para essa configuração).

## Usar certificados personalizados no Data Workbench {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

Instruções para usar certificados personalizados.

<!--
using-custom-certificates-DWB.xml
-->

Um certificado usado pelo cliente ou servidor do Data Workbench precisa ser assinado por uma autoridade de certificação confiável (autoridade de certificação). Os clientes do Data Workbench recebem certificados assinados pela CA da Visual Sciences. Esses certificados são confiáveis pelo software Data Workbench, já que a variável [!DNL trust_ca_cert.pem] (fornecido junto com o software Insight e armazenado no **Certificados** diretório de servidores e clientes) contém um *Certificado CA raiz* para a CA da Visual Sciences. Esses certificados são usados para licenciamento do software e autenticação quando clientes e servidores se comunicam usando SSL. Somente certificados emitidos pela CA da Visual Sciences podem ser usados para licenciamento, mas outros certificados podem ser usados para comunicação e autenticação. Os certificados emitidos por CA que não a Visual Sciences são a seguir referidos como *certificados personalizados.*

**Observação importante:** Para servidores e clientes, o software Data Workbench usa os arquivos de certificado instalados no cliente ou no servidor **Certificados** diretório ou certificados explicitamente identificados em sua configuração. No entanto, também é possível usar o Windows Certificate Store para clientes.

As instruções a seguir descrevem os procedimentos a seguir para a utilização de certificados personalizados para a comunicação entre clientes e servidores do Data Workbench. Nem todos os detalhes são um requisito difícil e podem ser utilizadas diferentes variações no processo. No entanto, os procedimentos abaixo foram testados para funcionar.

## Configuração de certificados de cliente personalizados {#section-2083fd41973e451fa404e7a4ae4da591}

1. Adicionar o certificado da autoridade de certificação emissora ao [!DNL trust_cert_ca.pem], que é instalado no **Certificados** diretório do cliente e de cada servidor em cada cluster que deve ser acessado usando este certificado personalizado.

1. Obtenha um certificado personalizado para cada servidor no cluster com as seguintes condições:

   1. O certificado é formatado como um [!DNL .pem] certificado.
   1. O certificado contém sua chave e é não criptografado (ou seja, não tem senha/senha).

      Um certificado contém sua chave com uma das seguintes linhas:

      ```
      BEGIN PRIVATE KEY
      BEGIN RSA PRIVATE KEY
      ```

      Uma maneira de remover a frase de senha de um [!DNL .pem] certificado:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. O certificado tem o CN, O, OU, etc. conforme necessário para este cliente nos servidores [!DNL Access Control.cfg] arquivo.
   1. O certificado foi emitido com um *propósito&#42;&#42;&#42;* de *cliente* (ou ambos *server* **e** *cliente*).

      Para verificar se um certificado tem um código de finalidade de servidor e/ou cliente, os seguintes comandos podem ser usados:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para certificados de servidor, ambos os comandos devem fornecer:

      ```
      custom_communications_cert.pem: OK
      ```

      Para um certificado de cliente, somente o segundo comando é necessário para fornecer [!DNL OK].

1. Coloque o certificado no **Certificados** diretório.
1. Em [!DNL Insight.cfg] nos termos do *serverInfo* para cada cluster que deseja usar este certificado, verifique se *certificado de cliente personalizado* é nomeado, como:

   ```
   Servers = vector: 1 items
     0 = serverInfo:
       SSL Client Certificate = string:
     <my_custom_client_cert.pem>
   ```

## Configurar certificados de servidor personalizados {#setting-up-custom-server-certificates}

Esta seção parte do princípio que você tem um cluster em execução, usando certificados emitidos pela Visual Sciences e a configuração segue práticas comuns (como *Componentes para servidores de processamento* no principal é sincronizado com o *Componentes* diretórios de todas as DPUs).

1. Adicionar o certificado da autoridade de certificação emissora ao [!DNL trust_cert_ca.pem] que é instalado em cada servidor no cluster e em todos os clientes que precisam se comunicar com esse cluster.
1. Obtenha um certificado personalizado para cada servidor no cluster com estes requisitos:

   1. O certificado personalizado é formatado como um [!DNL .pem] certificado.
   1. O certificado contém sua chave e é não criptografado (ou seja, não tem senha/senha).

      Um certificado contém sua chave se tiver uma linha como:

      ```
      BEGIN PRIVATE KEY
      BEGIN RSA PRIVATE KEY
      ```

      Uma maneira de remover a frase de senha de um [!DNL .pem] certificado:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. O certificado tem o mesmo CN que o [!DNL server_cert.pem] atualmente instalado no servidor.
   1. O certificado foi emitido com o objetivo de *server* e *cliente*.

      Para verificar se um certificado tem um código de finalidade de servidor e/ou cliente, os seguintes comandos podem ser usados:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para certificados de servidor, ambos os comandos devem fornecer:

      ```
      custom_communications_cert.pem: OK
      ```

      Para um certificado de cliente, somente o segundo comando é necessário para fornecer [!DNL OK].

1. Instale o certificado personalizado de cada servidor na **Certificados** diretório do servidor como [!DNL custom_communications_cert.pem].

1. Usando um editor de texto, adicione a seguinte linha em **Communications.cfg** em ambas as *Componentes* e *Componentes para servidores de processamento* diretórios , logo abaixo da primeira linha ( [!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Reinicie todos os servidores.

**Sobre o Aviso de Falha de Certificado**

Quando o servidor ou cliente do Insight está procurando um **licença** no **Certificados** , ele tenta validar todos os certificados (exceto [!DNL trust_ca_cert.pem]), contra uma cópia codificada do certificado CA Insight, que falha em qualquer certificado personalizado presente no diretório. O servidor emite este aviso:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Esse aviso pode ser ignorado com segurança.

## Criptografia de cadeia de caracteres {#concept-35da0b53650a4d7e82b240ad27f6d45a}

Criptografar senhas e outras strings ao se comunicar entre o cliente e o servidor.

<!--
string_encryption.xml
-->

Ao se comunicar entre o cliente do Data Workbench (estação de trabalho) e o servidor, é possível salvar um parâmetro Value (como uma senha) com o Tipo de *EncryptedString*. Isso oculta o parâmetro e salva a string no valor *Armazenamento de Credenciais do Windows* no servidor com a chave correspondente retornada. Isso armazena principalmente as credenciais usadas nas exportações, mas pode ser usado para criptografar qualquer parâmetro.

* Uma nova pasta foi adicionada no Servidor\**EncryptStrings**.

   É aqui que você define o arquivo de configuração para criptografar cadeias de caracteres.

* Um novo arquivo de configuração foi adicionado em Servidor\Componente\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Esse arquivo pesquisa a variável *Servidor*\*Pasta EncryptStrings* para arquivos de configuração de criptografia.

**Para criptografar uma cadeia de caracteres**:

1. Crie um **EncryptedStrings.cfg** arquivo de configuração para uma string com esses campos definidos:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier
     Value = string: // Value to be encrypted
   ```

   * *Valor* - Esse campo contém a cadeia de caracteres de texto simples que precisa ser criptografada.

      Essa é apenas a criptografia do lado do servidor. O *Valor* é criptografada somente no computador servidor.

   * *Nome* - Este campo contém um valor que identifica a cadeia de caracteres criptografada.
   * *EncryptValue* - Este campo ficará vazio no arquivo de configuração de entrada. O valor criptografado será retornado neste campo.

   Você pode adicionar vários **NameEncryptValuePair** para diferentes campos de criptografia.

   >[!NOTE]
   >
   >Todos os campos Value vazios serão removidos.

1. Salve as **EncryptedStrings.cfg** arquivo para o servidor\**EncryptStrings** pasta.

**Arquivo de saída**

Um arquivo de saída será gerado com o mesmo nome do arquivo de entrada com um &lt;*filename*>.*criptografado* extensão. Por exemplo, se o arquivo de entrada for nomeado *sample.cfg* em seguida, o arquivo de saída será nomeado *sample.cfg.encrypted*.
