---
description: O Windows Certificate Store permite que você armazene o certificado do cliente e a chave privada no Windows Certificate Store para comunicação SSL com servidores.
title: Windows Certificate Store
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: ht
source-git-commit: a766b64ef809e2223fed869d8d63b75f270a3d39
workflow-type: ht
source-wordcount: '1000'
ht-degree: 100%

---


# Windows Certificate Store {#windows-certificate-store}

O Windows Certificate Store permite que você armazene o certificado do cliente e a chave privada no Windows Certificate Store para comunicação SSL com servidores.

O Windows Certificate Store para o Cliente é um novo recurso que permite armazenar o certificado de comunicação SSL e a chave privada no Windows Certificate Store ao invés de no arquivo `Insight/Certificates/<CertName>.pem`. O uso do Windows Certificate Store pode ser preferível se você usar o armazenamento de certificados para outros aplicativos e desejar fazer o gerenciamento de certificados em um local, ou para usuários que desfrutam do registro de auditoria de logon adicional do Windows fornecido pelo Windows Certificate Store.

>[!NOTE]
>
>O licenciamento com o servidor de licenças ainda é mantido usando o arquivo `<Common Name>.pem` existente e o certificado obtido do armazenamento de certificados será usado apenas para comunicação com os servidores especificados.

## Pré-requisitos {#section-69b18600052145ff8e5299b7123e69c5}

1. Você deve ter acesso ao arquivo [!DNL certmgr.msc] com a capacidade de importar um certificado e uma chave para o armazenamento **Pessoal**. (O que deve ser verdadeiro por padrão para a maioria dos usuários do Windows.)

1. O usuário que faz a configuração deve ter uma cópia da ferramenta de linha de comando **OpenSSL**.
1. O servidor e o cliente já devem estar configurados para usar um certificado SSL personalizado, conforme descrito em [Usar certificados personalizados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd), que dá instruções para armazenar o certificado do cliente no Windows Certificate Store em vez de armazená-lo no diretório **Certificados**.

## Configurar o Windows Certificate Store {#section-3629802122e947d4b4f63e8b732cfe27}

Siga estas etapas para ativar o Windows Certificate Store:

**Etapa 1: importe o certificado SSL e a chave privada do usuário para o Windows Certificate Store.**

Em [Usar certificados personalizados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd), você é direcionado a colocar o certificado SSL e a chave no seguinte diretório:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

O nome do certificado é `<Common Name>.pem` (como [!DNL Analytics Server 1.pem], não o arquivo [!DNL trust_ca_cert.pem]).

Antes de ser possível importar o certificado e a chave privada, converta-os do formato .[!DNL pem] para um formato [!DNL .pfx], como [!DNL pkcs12.pfx]).

1. Abra um prompt de comando ou terminal e navegue até o diretório:

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
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
