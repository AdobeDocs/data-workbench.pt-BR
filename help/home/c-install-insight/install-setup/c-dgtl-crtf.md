---
description: Depois de instalar os arquivos do programa Insight, você deve baixar e instalar o certificado digital fornecido pela Adobe.
title: Download e instalação do certificado digital
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Download e instalação do certificado digital{#downloading-and-installing-the-digital-certificate}

Depois de instalar os arquivos do programa Insight, você deve baixar e instalar o certificado digital fornecido pela Adobe.

## Download e instalação do certificado digital {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

Depois de instalar os arquivos do programa Insight, você deve baixar e instalar o certificado digital fornecido pela Adobe.

## Noções básicas sobre certificados digitais {#concept-9eed01c8d95440cda6ce29d68e65098c}

A Adobe usa certificados digitais X.509 para identificar e autenticar os componentes cliente e servidor que compõem uma implementação.

<!--
c_undst_dgtl_crtf.xml
-->

Ao instalar o Insight, você deve instalar o certificado digital que autoriza um indivíduo nomeado (por exemplo, Jane Smith) a usar o aplicativo cliente instalado.

>[!NOTE]
>
>Se precisar migrar o Insight para outro computador ou usuário nomeado, você deverá obter um novo certificado da Adobe. Para fazer isso, entre em contato com o Atendimento ao cliente da Adobe.

O Insight apresenta esse certificado digital para obter acesso a um componente de servidor. Um administrador de um componente de servidor pode restringir o acesso aos recursos do servidor com base nos valores comuns de nome ou unidade organizacional exibidos no certificado do usuário.

Os certificados digitais X.509 instalados com aplicativos Adobe também permitem que os componentes cliente e servidor troquem informações por SSL (Secure Sockets Layer). O SSL protege as transmissões via HTTP usando um sistema de criptografia de chave pública e privada. A implementação do SSL pela Adobe suporta chaves RSA de 1024 bits e usa um algoritmo de criptografia RC4 de 128 bits.

Além da segurança, o certificado digital que você instala também funciona como uma chave de licença que permite executar o Insight. Para funcionar corretamente, um certificado digital deve ser bloqueado por nó e atual, ou o aplicativo não será iniciado.

## Certificados bloqueados por nó {#section-984aa8f2f5a1448cadc4afea978aedc9}

Um certificado bloqueado por nó é um certificado digital registrado no computador em que está instalado. O bloqueio de nó associa permanentemente um certificado a um identificador de nó específico (um valor que identifica exclusivamente um computador específico). Para que o nó bloqueie seu certificado, seu computador deve ter acesso à Internet ao Adobe License Server ou a um servidor proxy que tenha acesso ao License Server.

Se estiver instalando em um computador que não pode acessar a Internet, você deverá obter e instalar um certificado especial pré-bloqueado, conforme descrito em [Usando certificados digitais em computadores sem acesso](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1)à Internet.

Se você estiver instalando em um computador que possa acessar a Internet, seu certificado digital será bloqueado automaticamente no nó na primeira vez que você iniciar o Insight. Depois de ser bloqueado por nó, o certificado não pode ser usado em nenhum outro computador. Se precisar migrar o Insight para outro computador, você deve obter um certificado novo e desbloqueado da Adobe.

## Certificados atuais {#section-0816b031df3e415ab3f0205b720c723e}

Além de estar bloqueado por nó, seu certificado digital deve estar atualizado. Para permanecer atualizado, seu certificado deve ser revalidado regularmente (geralmente a cada 30 dias, mas pode variar dependendo do acordo com a Adobe). Se o computador tiver acesso à Internet, o processo de revalidação será completamente transparente. O Insight se conecta automaticamente ao License Server e revalida o certificado quando necessário. Se o computador não tiver acesso à Internet, você deverá instalar manualmente um certificado atualizado, conforme descrito na seção a seguir.

## Usando certificados digitais em computadores sem acesso à Internet {#section-d3c060131d7f45cda27f68848b704fa1}

Se estiver instalando em um computador que não pode acessar a Internet, você deverá solicitar um certificado pré-bloqueado para a instalação do Insight. Um certificado pré-bloqueado é um certificado digital que a Adobe bloqueia manualmente para o identificador de nó do computador.

Para solicitar um certificado pré-bloqueado, você deve enviar o identificador do nó e o número do certificado ao Atendimento ao cliente da Adobe. Para obter o identificador de nó do computador, entre em contato com o Atendimento ao cliente da Adobe para solicitar o utilitário da Adobe [!DNL Node Identifier] . Você também pode obter o identificador do nó a partir do alerta que o Insight emite quando ele tenta se conectar ao License Server e não pode. Ao receber o certificado pré-bloqueado, instale-o conforme descrito nas duas últimas etapas de [Instalação de certificados](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38)digitais.

Quando o certificado precisar ser revalidado, você deverá baixar um novo certificado validado do License Server e reinstalá-lo no computador (a menos que seu contrato com a Adobe indique o contrário).

## Instalação de certificados digitais {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**Para baixar e instalar o certificado digital**

1. Abra o navegador da Web para [!DNL http:\\license.visualsciences.com].

   >[!NOTE]
   >
   >Seu navegador pode solicitar que você apresente um certificado digital neste momento. Se isso acontecer, clique **[!UICONTROL Cancel]** para fechar a caixa de diálogo.

1. Na tela de logon, digite o [!DNL Account Name] e os [!DNL Password] que você recebeu da Adobe e clique em **[!UICONTROL login]**.
1. Localize o certificado que foi emitido para sua instância do Insight ( *Seu nome*.pem) e clique no ![](assets/btn_save_certificatedownload.PNG) ícone associado ao certificado.
1. Quando solicitado a salvar o certificado, clique em **[!UICONTROL Save]**.
1. Baixe o arquivo na [!DNL Certificates] pasta no diretório em que você instalou o Insight.

   Esta pasta contém um arquivo de certificado chamado [!DNL trust_ca_cert.pem]. Ambos os arquivos de certificado devem estar sempre presentes para que o Insight funcione.

## Windows Certificate Store {#concept-4acb13b7de9340ea8cde8ad84b93358d}

O Windows Certificate Store permite que você armazene o certificado do cliente e a chave privada no Windows Certificate Store para comunicação SSL com servidores.

<!--
crypto-api.xml
-->

O Windows Certificate Store para o Cliente é um novo recurso que permite armazenar o certificado de comunicação SSL e a chave privada no Windows Certificate Store em vez de no `Insight/Certificates/<CertName>.pem` arquivo. O uso do Windows Certificate Store pode ser preferível se você usar o repositório de certificados para outros aplicativos e desejar fazer o gerenciamento de certificados em um local, ou para usuários que desfrutam do registro de auditoria adicional do Windows fornecido pelo Windows Certificate Store.

>[!NOTE]
>
>O licenciamento com o servidor de licenças ainda é mantido usando o `<Common Name>.pem` arquivo existente e o certificado obtido do repositório de certificados será usado apenas para comunicação com os servidores especificados.

## Pré-requisitos {#section-69b18600052145ff8e5299b7123e69c5}

1. Você deve ter acesso ao [!DNL certmgr.msc] arquivo com a capacidade de importar um certificado e uma chave para a loja **Pessoal** . (Isso deve ser verdadeiro por padrão para a maioria dos usuários do Windows.)

1. O usuário que faz a configuração deve ter uma cópia da ferramenta de linha de comando **OpenSSL** .
1. O servidor e o cliente já devem estar configurados para usar um certificado SSL personalizado, dando instruções para armazenar o certificado do cliente no repositório de certificados do Windows em vez de armazená-lo no diretório **Certificados** .

## Configuração do Windows Certificate Store {#section-3629802122e947d4b4f63e8b732cfe27}

O Windows Certificate Store para Clientes está ativado seguindo estas etapas:

**Etapa 1: Importe o certificado SSL e a chave privada do usuário para o Windows Certificate Store.**

Em [Uso de certificados personalizados na Análise](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) de big data, você é direcionado a colocar o certificado SSL e a chave no seguinte diretório:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

O nome do certificado é `<Common Name>.pem` como Analytics Server 1.pem (não o arquivo trust_ca_cert.pem.)

Antes que o certificado e a chave privada possam ser importados, eles devem ser convertidos de . [!DNL pem] para um [!DNL .pfx] formato, como [!DNL pkcs12.pfx] ).

1. Abra um prompt de comando ou terminal e navegue até o diretório:

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
   ```

1. Execute [!DNL openssl] com os seguintes argumentos (com o nome do [!DNL .pem] arquivo real):

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Se solicitado, pressione **Enter** para ignorar a inserção de uma senha de exportação.

1. Executar [!DNL certmgr.msc] a partir do prompt de execução, do menu Iniciar ou da linha de comando.
1. Abra o repositório de certificados **pessoais** para o usuário atual.

   ![](assets/6_5_crypto_api_0.png)

1. Clique com o botão direito do mouse em **Certificados** e clique em **Todas as tarefas** > **Importar**.

   Verifique se a opção Usuário **** atual está selecionada e clique em **Avançar**.

   ![](assets/6_5_crypto_api_4.png)

1. Clique em **Procurar** e selecione o `<CommonName>.pfx` arquivo criado anteriormente. Será necessário alterar a caixa suspensa de extensão de arquivo de um Certificado X.509 para o **Personal Information Exchange** ou para **All Files** para visualizá-lo.

   Selecione o arquivo e clique em **Abrir** e em **Avançar**.

1. Não digite uma senha e verifique se apenas as opções **Marcar essa chave como exportável** e **Incluir todas as propriedades** estendidas estão selecionadas.

   ![](assets/6_5_crypto_api_3.png)

   Clique em **Próximo**.

1. Certifique-se de que a opção **Colocar todos os certificados no seguinte repositório** esteja selecionada e que o repositório de certificados listado seja **Pessoal**. (Se você for um usuário avançado, poderá selecionar outra loja nesse ponto, mas será necessário alterar a configuração posteriormente.)

1. Clique em **Avançar** e em **Concluir**. Você deve ver uma caixa de diálogo informando que a importação foi bem-sucedida e ver seu certificado na pasta Certificados da loja.

   >[!NOTE]
   >
   >Preste especial atenção aos campos **Emitido para** e **Emitido por** . Você vai precisar deles no próximo passo.

**Etapa 2: Edite o arquivo Insight.cfg.**

O [!DNL Insight.cfg] arquivo deve ser editado para direcionar o Análise de big data para usar o recurso Windows Certificate Store. Cada entrada de servidor neste arquivo deve ter alguns parâmetros adicionais especificados. Se os parâmetros forem omitidos, a estação de trabalho usará a configuração de certificado existente como padrão. Se os parâmetros forem especificados, mas tiverem valores incorretos, a estação de trabalho informará um estado de erro e você precisará consultar o arquivo de log para obter informações sobre erros.

1. Abra o arquivo **Insight.cfg** (localizado no diretório de instalação do **Insight** ).

1. Role para baixo até a entrada do servidor que você deseja configurar. Se você quiser usar o Windows Certificate Store para cada servidor, é necessário fazer essas modificações em cada entrada no vetor de [!DNL serverInfo] objetos.
1. Adicione esses parâmetros ao seu [!DNL Insight.cfg] arquivo. Você pode fazer isso a partir da estação de trabalho ou manualmente adicionando os seguintes parâmetros ao [!DNL serverInfo] objeto. (Não se esqueça de usar espaços em vez de caracteres de tabulação e não cometa outros erros tipográficos ou de sintaxe neste arquivo. )

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   O booliano ativa ou desativa o recurso. O nome do certificado corresponde ao **Emissor para** no gerenciador de certificados. O nome do emissor do certificado corresponde a **Emitido por**, e o Nome **da** loja deve corresponder ao nome do repositório do certificado.

   >[!NOTE]
   >
   >O nome &quot;Pessoal&quot; no Gerenciador de certificados (certmgr.msc) se refere ao armazenamento de certificados chamado **My.** Consequentemente, se você importar seu certificado de comunicação SSL e sua chave (.PFX) para o repositório de certificados **Pessoal** , conforme recomendado, deverá definir a string **SSL CryptoAPI Cert Store Name** como &quot;My&quot;. A definição deste parâmetro para &quot;Pessoal&quot; não funcionará. Esta é uma peculiaridade do repositório de certificados do Windows.

   Uma lista completa dos armazenamentos de sistema predefinidos pode ser obtida aqui: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Seu sistema pode ter armazenamentos de certificados adicionais. Se quiser usar uma loja diferente de &quot;Pessoal&quot; (como **Meu**), você deve obter o nome canônico do repositório de certificados e fornecê-lo no [!DNL Insight.cfg] arquivo. (O nome da loja do sistema &quot;My&quot; é chamado inconsistentemente de &quot;My&quot; e &quot;MY&quot; pela documentação do Windows. O parâmetro não parece fazer distinção entre maiúsculas e minúsculas.)

1. Depois de adicionar esses parâmetros e verificar se os valores correspondem à lista no Gerenciador de certificados do Windows, salve o [!DNL Insight.cfg] arquivo.

Agora você pode iniciar a estação de trabalho (ou desconectar/reconectar ao servidor). A Análise de big data deve carregar seu certificado e sua chave do repositório de certificados e conectar-se normalmente.

## Saída de registro {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Quando um certificado não é encontrado ou é inválido, essa mensagem de erro é emitida para o [!DNL HTTP.log] arquivo.

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>A estrutura de registro L4 pode ser ativada pela configuração do [!DNL L4.cfg] arquivo (consulte seu gerente de conta para configurar isso).

## Uso de certificados personalizados na Análise de big data {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

Instruções para uso de certificados personalizados.

<!--
using-custom-certificates-DWB.xml
-->

Um certificado usado pelo cliente ou servidor da Análise de big data precisa ser assinado por uma autoridade de certificação (autoridade de certificação) confiável. Os clientes do Análise de big data recebem certificados assinados pela CA do Visual Sciences. Esses certificados são confiáveis pelo software Análise de big data, já que o [!DNL trust_ca_cert.pem] (fornecido junto com o software Insight e armazenado no diretório **Certificados** tanto dos servidores quanto dos clientes) contém um Certificado *CA* raiz para a CA do Visual Sciences. Esses certificados são usados para licenciamento do software e autenticação quando clientes e servidores se comunicam entre si usando SSL. Somente certificados emitidos pela CA do Visual Sciences podem ser usados para licenciamento, mas outros certificados podem ser usados para comunicação e autenticação. Certificados emitidos por CAs que não sejam Visual Sciences são referidos abaixo como certificados *personalizados.*

**Observação importante:** Para servidores e clientes, o software Análise de big data usa os arquivos de certificado instalados no diretório ou certificados **Certificados** do cliente ou servidor explicitamente identificados em sua configuração. No entanto, você também pode usar o Windows Certificate Store para clientes.

As instruções a seguir descrevem os procedimentos a serem seguidos para usar certificados personalizados para comunicação entre clientes e servidores da Análise de big data. Nem todos os pormenores são um requisito difícil e podem ser utilizadas variações diferentes no processo. No entanto, os procedimentos abaixo foram testados para funcionar.

## Configuração de certificados de cliente personalizados {#section-2083fd41973e451fa404e7a4ae4da591}

1. Adicione o certificado da CA emissora ao [!DNL trust_cert_ca.pem], que está instalado no diretório **Certificados** do cliente e o de cada servidor em cada cluster que deve ser acessado usando este certificado personalizado.

1. Obtenha um certificado personalizado para cada servidor no cluster com as seguintes condições:

   1. O certificado é formatado como um [!DNL .pem] certificado.
   1. O certificado contém sua chave e não é criptografado (isto é, não tem senha/senha).

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

   1. O certificado tem o CN, O, OU, etc. conforme necessário para este cliente no arquivo dos servidores [!DNL Access Control.cfg] .
   1. O certificado foi emitido com uma *finalidade **** de *cliente* (ou *servidor* **e** *cliente*).

      Para verificar se um certificado tem um código de finalidade de servidor e/ou cliente, os seguintes comandos podem ser usados:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para certificados de servidor, ambos os comandos devem fornecer:

      ```
      custom_communications_cert.pem: OK
      ```

      Para um certificado de cliente, somente o segundo comando é necessário para ceder [!DNL OK].

1. Coloque o certificado no diretório **Certificados** do cliente.
1. Em [!DNL Insight.cfg] serverInfo *para cada cluster que você deseja usar este certificado, verifique se o certificado* do cliente ** personalizado está nomeado, como:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:  
     <my_custom_client_cert.pem>
   ```

## Configuração de certificados de servidor personalizados {#setting-up-custom-server-certificates}

Esta seção supõe que você tem um cluster que está ativo e em execução, usando certificados emitidos pelo Visual Sciences, e a configuração segue práticas comuns (como o diretório *Componentes para Servidores* de Processamento no mestre é sincronizado com os diretórios *Componentes* de todas as DPUs).

1. Adicione o certificado da CA emissora ao [!DNL trust_cert_ca.pem] que está instalado em todos os servidores do cluster e todos os clientes que precisam se comunicar com este cluster.
1. Obtenha um certificado personalizado para cada servidor no cluster com estes requisitos:

   1. O certificado personalizado é formatado como um [!DNL .pem] certificado.
   1. O certificado contém sua chave e não é criptografado (isto é, não tem senha/senha).

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
   1. O certificado foi emitido com uma finalidade de *servidor* e *cliente*.

      Para verificar se um certificado tem um código de finalidade de servidor e/ou cliente, os seguintes comandos podem ser usados:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Para certificados de servidor, ambos os comandos devem fornecer:

      ```
      custom_communications_cert.pem: OK
      ```

      Para um certificado de cliente, somente o segundo comando é necessário para ceder [!DNL OK].

1. Instale o certificado personalizado de cada servidor no diretório **Certificados** do servidor como [!DNL custom_communications_cert.pem].

1. Usando um editor de texto, adicione a seguinte linha ao arquivo **Communications.cfg** nos diretórios *Components* e *Components for Processing Servers (Componentes para processamento de servidores* ), logo abaixo da primeira linha ( [!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Reinicie todos os servidores.

**Sobre o Aviso de Falha de Certificado**

Quando o servidor ou cliente do Insight está procurando um certificado de **licença** no diretório **Certificados** , ele tenta validar todos os certificados (exceto [!DNL trust_ca_cert.pem]) em relação a uma cópia codificada do certificado CA do Insight, que falha em qualquer certificado personalizado presente no diretório. O servidor emite este aviso:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Este aviso pode ser ignorado com segurança.

## Criptografia de cadeia de caracteres {#concept-35da0b53650a4d7e82b240ad27f6d45a}

Criptografe senhas e outras strings ao se comunicar entre o cliente e o servidor.

<!--
string_encryption.xml
-->

Ao se comunicar entre o cliente da Análise de big data (estação de trabalho) e o servidor, é possível salvar um parâmetro Valor (como uma senha) com o Tipo de *EncryptedString*. Isso oculta o parâmetro e salva a string no Repositório *de Credenciais do* Windows no servidor com a chave correspondente retornada. Isso armazena principalmente as credenciais usadas nas exportações, mas pode ser usado para criptografar qualquer parâmetro.

* Uma nova pasta foi adicionada em Server\**EncryptStrings**.

   É aqui que você define o arquivo de configuração para criptografar strings.

* Um novo arquivo de configuração foi adicionado em Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent: 
     Path = Path: EncryptStrings\\*.cfg
   ```

   Este arquivo pesquisa a pasta *Server*\*EncryptStrings* para arquivos de configuração de criptografia.

**Para criptografar uma string**:

1. Crie um arquivo de configuração **EncryptedStrings.cfg** para uma string com estes campos definidos:

   ```
   Names = vector: 1 items 
    0 = NameEncryptValuePair: 
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server 
     Name = string: // Name for identifier  
     Value = string: // Value to be encrypted
   ```

   * *Valor* - Esse campo contém a string de texto simples que precisa ser criptografada.

      Isso é criptografia somente no servidor. A configuração *Valor* é criptografada somente no computador servidor.

   * *Nome* - Esse campo contém um valor que identifica a string criptografada.
   * *EncryptValue* - Esse campo ficará vazio no arquivo de configuração de entrada. O valor criptografado será retornado neste campo.
   Você pode adicionar vários valores **NameEncryptValuePair** para diferentes campos de criptografia.

   >[!NOTE]
   >
   >Todos os campos de Valor vazios serão removidos.

1. Salve o arquivo **EncryptedStrings.cfg** na pasta Server\**EncryptStrings**.

**Arquivo de saída**

Um arquivo de saída será gerado com o mesmo nome do arquivo de entrada com um &lt;*nome de arquivo*>.*extensão criptografada* . Por exemplo, se o arquivo de entrada for nomeado como *exemplo.cfg* , o arquivo de saída será nomeado como *exemplo.cfg.encrypted*.
