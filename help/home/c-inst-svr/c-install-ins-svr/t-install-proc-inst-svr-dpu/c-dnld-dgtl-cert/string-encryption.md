---
description: Criptografe senhas e outras strings ao se comunicar entre o cliente e o servidor.
title: Criptografia de cadeia de caracteres
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Criptografia de cadeia de caracteres{#string-encryption}

Criptografe senhas e outras strings ao se comunicar entre o cliente e o servidor.

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
