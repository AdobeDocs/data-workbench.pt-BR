---
description: Agora você pode usar CSV, TSV, Exportação de segmentos e Exportação de segmentos com cabeçalho usando protocolos FTP e SFTP para exportar arquivos de segmento do cliente (estação de trabalho) para o servidor.
title: Exportar um segmento usando entrega S/FTP
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Exportar um segmento usando entrega S/FTP{#export-a-segment-using-s-ftp-delivery}

Agora você pode usar CSV, TSV, Exportação de segmentos e Exportação de segmentos com cabeçalho usando protocolos FTP e SFTP para exportar arquivos de segmento do cliente (estação de trabalho) para o servidor.

**Configuração de arquivos de configuração de exportação S/FTP**

Para definir a configuração de exportação, dois novos arquivos de configuração de exportação foram adicionados para configurar uma conexão FTP ou SFTP, permitindo que os detalhes do servidor sejam separados do arquivo *FTPServerInfo.cfg* e as credenciais sejam escolhidas da pasta *FTPUserCredentials* (correspondente ao Nome do servidor fornecido nos argumentos de comando).

* Defina o arquivo **FTPServerInfo.cfg** .

   Digite as informações do servidor FTP e defina as tentativas de conexão permitidas da estação de trabalho. Edite da estação de trabalho ou do servidor no arquivo [!DNL Server\Addresses\Export\] **[!DNL FTPServerInfo.cfg]** .

   ```
   FTP Servers = vector: 1 items 
     0 = ftpServerInfo:  
       Address = string:  
       Name = string:  
       Port = int: 21 
   Connect Retries = vector: 1 items 
     0 = connectServerRetries:  
       Retries = int: 0 
       Server Name = string:
   ```

* Defina o arquivo **FTPUserCredentials.cfg** .

   Digite as credenciais do usuário para conectar-se aos servidores usando o arquivo [!DNL Server\Admin\Export\] **[!DNL FTPUserCredentials.cfg]** . Este arquivo contém as credenciais de usuário necessárias para se conectar aos servidores e só pode ser editado do servidor e não da estação de trabalho (cliente).

   ```
   FTP User Credentials = vector: 1 items 
     0 = ftpUserCredInfo: 
       User Name = string:  
       User Password = EncryptedString:  
       Server Name = string:  
       Public Key Path = string:  
       Private Key Path = string:  
       Passphrase = EncryptedString:
   ```

   >[!NOTE]
   >
   >Certifique-se de que as chaves SSH geradas para autenticação estejam no formato idêntico àquelas geradas quando você usa o comando SSH Keygen.
   >
   >Exemplo para geração de teclas SSH usando keygen:
   >
   >
   ```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   Há seis parâmetros no arquivo **FTPUserCredentials.cfg** necessários para várias transferências FTP ou SFTP.

   1. *Nome do Usuário*
   1. *Senha do usuário*
   1. *Nome do servidor*
   1. *Caminho da chave pública*
   1. *Caminho da chave privada*
   1. *Senha*
   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Protocolo </th> 
      <th colname="col2" class="entry"> Parâmetros </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>FTP </p> </td> 
      <td colname="col2"> <p>Defina os parâmetros 1, 2, 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP usando autenticação de senha </p> </td> 
      <td colname="col2"> <p>Defina os parâmetros 1, 2, 3 quando a transferência usar a autenticação de senha (-p nos argumentos de comando). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP usando autenticação de chave </p> </td> 
      <td colname="col2"> <p>Defina os parâmetros 1, 2, 3, 4, 5, 6 quando a transferência usar a autenticação de chave (-k nos argumentos de comando). </p> </td> 
      </tr> 
    </tbody> 
    </table>

**Configuração dos comandos FTP e SFTP Export**

1. Abra uma tabela de exportação.

   Na estação de trabalho, clique com o botão direito do mouse em uma Tabela *de* detalhes e escolha um dos tipos de exportação: CSV, TSV, Exportação de segmentos ou Exportação de segmentos com cabeçalho. Ou abra o [!DNL .export] arquivo a partir de um prompt de comando e edite (consulte [Configuração de segmentos para exportação](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372)).

1. No campo *Comando* , defina-o para apontar para o executável de exportação:

   ```
   ExportIntegration.exe
   ```

1. Defina os campos Argumentos *de* Comando como mostrado abaixo para o protocolo e autenticação necessários:

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP** (se estiver usando a senha para autenticação)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -p>
   ```

   **SFTP** (se estiver usando chaves para autenticação)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -k>
   ```

   ![](assets/SFTP_command_arguments.png)

Todos os Argumentos de Comando são obrigatórios e precisam ser inseridos conforme mostrado.

## Exportação S/FTP usando chaves privadas/públicas {#section-0534424d79a54a47b82594cfa7b3c17f}

Para implementar a Exportação FTP e SFTP usando chaves privadas e públicas, coloque os arquivos de configuração nestas pastas:

* Coloque **FTPServerInfo.cfg** na [!DNL Server/Addresses/Export/] pasta.
* Coloque **FTPUserCredentials.cfg** na [!DNL Server/Admin/Export/] pasta.

Seis parâmetros estão incluídos no arquivo **FTPServerInfo.cfg** :

1. *Nome do Usuário*
1. *Senha do usuário*
1. *Nome do servidor*
1. *Caminho da chave pública*
1. *Caminho da chave privada —* coloque o caminho da chave privada no arquivo de configuração sem a extensão, por exemplo:

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *Senha*

O FTP usa os parâmetros 1, 2 e 3.

O SFTP usa os parâmetros 1, 2 e 3 quando a transferência usa autenticação por senha.

O SFTP usa todos os seis parâmetros quando a transferência é feita usando a autenticação de chave. Por exemplo, se você estiver usando chaves para autenticação:

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

Os arquivos de configuração precisam estar no local correto.

>[!NOTE]
>
>As chaves públicas precisam apontar para um arquivo **.pem** e não para um local de pasta. Você pode criar chaves usando uma função de geração de chave SSH de aplicativos como Cygwin. (O Putty gera chaves em um formato .ppk sem suporte.)
