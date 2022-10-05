---
description: Criptografar senhas e outras strings ao se comunicar entre o cliente e o servidor.
title: Criptografia de cadeia de caracteres
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
exl-id: 43696ff1-3153-4d85-b9a9-c2752dd2c29a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Criptografia de cadeia de caracteres{#string-encryption}

{{eol}}

Criptografar senhas e outras strings ao se comunicar entre o cliente e o servidor.

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
