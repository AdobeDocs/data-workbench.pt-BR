---
description: O Windows Certificate Store permite que você armazene o certificado do cliente e a chave privada no Windows Certificate Store para comunicação SSL com servidores.
title: Windows Certificate Store
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Certificate Store{#windows-certificate-store}

O Windows Certificate Store permite que você armazene o certificado do cliente e a chave privada no Windows Certificate Store para comunicação SSL com servidores.

O Windows Certificate Store para o Cliente é um novo recurso que permite armazenar o certificado de comunicação SSL e a chave privada no Windows Certificate Store em vez de no `Insight/Certificates/<CertName>.pem` arquivo. O uso do Windows Certificate Store pode ser preferível se você usar o repositório de certificados para outros aplicativos e desejar fazer o gerenciamento de certificados em um local, ou para usuários que desfrutam do registro de auditoria adicional do Windows fornecido pelo Windows Certificate Store.

>[!NOTE]
>
>O licenciamento com o servidor de licenças ainda é mantido usando o `<Common Name>.pem` arquivo existente e o certificado obtido do repositório de certificados será usado apenas para comunicação com os servidores especificados.

## Pré-requisitos {#section-69b18600052145ff8e5299b7123e69c5}

1. Você deve ter acesso ao [!DNL certmgr.msc] arquivo com a capacidade de importar um certificado e uma chave para a loja **Pessoal** . (Isso deve ser verdadeiro por padrão para a maioria dos usuários do Windows.)

1. O usuário que faz a configuração deve ter uma cópia da ferramenta de linha de comando **OpenSSL** .
1. O servidor e o cliente já devem estar configurados para usar um certificado SSL personalizado, conforme descrito em [Usando certificados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd)personalizados, dando instruções para armazenar o certificado do cliente no repositório de certificados do Windows em vez de armazená-lo no diretório **Certificados** .

## Configuração do Windows Certificate Store {#section-3629802122e947d4b4f63e8b732cfe27}

O Windows Certificate Store para Clientes está ativado seguindo estas etapas:

**Etapa 1: Importe o certificado SSL e a chave privada do usuário para o Windows Certificate Store.**

Em [Usando certificados](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) personalizados, você é direcionado a colocar o certificado SSL e a chave no seguinte diretório:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

O nome do certificado é `<Common Name>.pem` (como [!DNL Analytics Server 1.pem](não o [!DNL trust_ca_cert.pem] arquivo).

Antes que o certificado e a chave privada possam ser importados, eles devem ser convertidos de . [!DNL pem] para um [!DNL .pfx] formato, como [!DNL pkcs12.pfx] ).

1. Abra um prompt de comando ou terminal e navegue até o diretório:

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
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
