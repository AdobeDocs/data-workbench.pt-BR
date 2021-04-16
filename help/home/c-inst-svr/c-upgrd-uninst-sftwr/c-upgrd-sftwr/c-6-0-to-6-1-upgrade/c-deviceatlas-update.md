---
description: O arquivo JSON DeviceAtlas agora será distribuído em um arquivo .bundle (um .tar.gz renomeado) junto com os arquivos DeviceAtlas.dll e DeviceAtlas64.dll.
title: Distribuição DeviceAtlas
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Distribuição DeviceAtlas{#deviceatlas-distribution}

O arquivo JSON DeviceAtlas agora será distribuído em um arquivo .bundle (um .tar.gz renomeado) junto com os arquivos DeviceAtlas.dll e DeviceAtlas64.dll.

Quando o administrador atualiza o servidor Insight para a versão 6.0, o arquivo DeviceAtlas.bundle é incluído com o pacote de atualização no perfil Software and Docs (perfil de software) localizado em:

[!DNL Server Packages > v6.00 > Server_6.00.zip]

O arquivo DeviceAtlas.bundle é extraído para [!DNL Server\Lookups\DeviceAtlas].

O arquivo DeviceAtlas.bundle deve ser colocado em um diretório sincronizado com as DPUs e o arquivo DeviceAtlas.cfg correspondente ao novo DeviceAtlasComponent deve ser colocado no diretório &quot;Components for Processing Servers&quot; na sincronização principal. Quando o arquivo DeviceAtlas.bundle é alterado, a próxima chamada de pesquisa DeviceAtlas obterá resultados com base na API atualizada e/ou no arquivo JSON.

## Modifique o arquivo Transformation.cfg {#section-394823348f5740028666e62e2bd42754}

As Transformações DeviceAtlas não precisarão mais especificar o caminho para o arquivo JSON. Qualquer DeviceAtlasTransformation anterior que esteja definido no arquivo transformation.cfg não deve mais incluir o parâmetro File que aponta para o arquivo JSON ofuscado.

Este exemplo de arquivo Transformation.cfg mostra o argumento File que deve ser excluído para evitar confusão. (Deixá-la lá não causará danos, mas somente confusão potencial porque será ignorada.)

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  
```

## Modifique o arquivo DeviceAtlas.cfg {#section-10b43705a6c846fd9ec54ea6be249f88}

Este é um exemplo do argumento [!DNL component] necessário no arquivo DeviceAtlas.cfg.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

Este arquivo DeviceAtlas.bundle será tratado como um arquivo de configuração da perspectiva do recurso Sincronização de perfil. Além disso, os dados JSON e a DLL serão usados no nível do Componente, em vez do nível de Transformação individual.

Um novo DeviceAtlasComponent, na inicialização, encontra o conglomerado .bundle, desofusca o arquivo JSON na memória, extrai os arquivos em um diretório temporário e carrega a DLL apropriada para a plataforma em execução. Esse componente também monitora as alterações no arquivo do pacote e recarrega o arquivo DLL e .cfg automaticamente se ele for alterado.

## Executando DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

A configuração correta faz uma grande diferença no tempo necessário para a transformação. A transformação pode ser configurada para ser executada somente uma vez por visitante por sessão para permitir que o DeviceAtlas acelere o processo.

**Se implantado usando Log Processing.cfg**:

Execute as transformações duas vezes.

1. Procure somente o campo [!DNL mobile id] e
1. Crie condições para ignorar o [!DNL mobile id] e, em seguida, procure o restante dos campos.

**Se implantado usando Transformation.cfg**:

Implante como na Etapa 1 do Processamento de log acima ou use linhas cruzadas para suportar uma configuração condicional.

* Linhas cruzadas — Pegue a chave de sessão anterior. Em seguida, identifique se a chave de sessão atual é diferente da encontrada nas linhas cruzadas. Nesse caso, a transformação DeviceAtlas será executada somente em um registro por sessão.
