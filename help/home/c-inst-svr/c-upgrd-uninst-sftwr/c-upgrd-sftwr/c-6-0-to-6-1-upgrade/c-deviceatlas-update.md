---
description: O arquivo JSON DeviceAtlas será distribuído em um arquivo .bundle (um arquivo .tar.gz renomeado) junto com os arquivos DeviceAtlas.dll e DeviceAtlas64.dll.
solution: Analytics
title: Distribuição DeviceAtlas
topic: Data workbench
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribuição DeviceAtlas{#deviceatlas-distribution}

O arquivo JSON DeviceAtlas será distribuído em um arquivo .bundle (um arquivo .tar.gz renomeado) junto com os arquivos DeviceAtlas.dll e DeviceAtlas64.dll.

Quando o administrador atualiza o Insight Server para a versão 6.0, o arquivo DeviceAtlas.bundle é incluído no pacote de atualização no perfil Software e Docs (perfil de software) localizado em:

[!DNL Server Packages > v6.00 > Server_6.00.zip]

O arquivo DeviceAtlas.bundle é extraído para [!DNL Server\Lookups\DeviceAtlas].

O arquivo DeviceAtlas.bundle deve ser colocado em um diretório sincronizado com as DPUs, e o arquivo DeviceAtlas.cfg correspondente ao novo DeviceAtlasComponent deve ser colocado no diretório &quot;Components for Processing Servers&quot; no mestre de sincronização. Quando o arquivo DeviceAtlas.bundle é alterado, a próxima chamada de pesquisa do DeviceAtlas obterá resultados com base na API atualizada e/ou no arquivo JSON.

## Modificar o arquivo Transformation.cfg {#section-394823348f5740028666e62e2bd42754}

As Transformações do DeviceAtlas não precisarão mais especificar o caminho para o arquivo JSON. Qualquer DeviceAtlasTransformation anterior definida no arquivo transformation.cfg não deve mais incluir o parâmetro File que aponta para o arquivo JSON ofuscado.

Este exemplo de arquivo Transformation.cfg mostra o argumento Arquivo que deve ser excluído para evitar confusão. (Deixá-la lá não causará danos, mas apenas confusão potencial porque será ignorada.)

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

Este é um exemplo do [!DNL component] argumento necessário no arquivo DeviceAtlas.cfg.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

Este arquivo DeviceAtlas.bundle será tratado como um arquivo de configuração na perspectiva do recurso Sincronização de perfil. Além disso, os dados JSON e a DLL serão usados no nível de Componente em vez do nível de Transformação individual.

Um novo DeviceAtlasComponent, na inicialização, encontra o conglomerado .bundle, desofusca o arquivo JSON na memória, extrai os arquivos em um diretório temporário e carrega a DLL apropriada para a plataforma em execução. Esse componente também monitora as alterações no arquivo de pacote e recarrega o arquivo DLL e .cfg automaticamente se ele for alterado.

## Executando DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

A configuração correta faz uma grande diferença no tempo necessário para a transformação. A transformação pode ser configurada para ser executada somente uma vez por visitante por sessão para permitir que o DeviceAtlas acelere o processo.

**Se implantado usando o Log Processing.cfg**:

Executar as transformações duas vezes.

1. Procure apenas o [!DNL mobile id] campo, então
1. Crie condições para ignorar os campos [!DNL mobile id] e, em seguida, pesquise o restante dos campos.

**Se implantado usando Transformation.cfg**:

Implante como na Etapa 1 do Processamento de log acima ou use linhas cruzadas para suportar uma configuração condicional.

* Linhas cruzadas—Segure a chave de sessão anterior. Em seguida, identifique se a chave de sessão atual é diferente da encontrada nas linhas cruzadas. Em caso afirmativo, a transformação DeviceAtlas só será executada em um registro por sessão.

