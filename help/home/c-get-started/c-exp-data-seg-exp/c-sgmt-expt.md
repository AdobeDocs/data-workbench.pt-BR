---
description: Você pode criar facilmente uma definição de Exportação de segmento a partir da visualização de Tabela de detalhes no Cliente da Análise de big data.
solution: Analytics
title: Exportação de segmento
topic: Data workbench
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportação de segmento{#segment-export}

Você pode criar facilmente uma definição de Exportação de segmento a partir da visualização de Tabela de detalhes no Cliente da Análise de big data.

Além disso, combine [!DNL Segment Exports] automaticamente os resultados em um único servidor, em vez de produzir resultados parciais em cada DPU que você deve combinar usando um processo externo. Você pode criar um arquivo de exportação de segmento, salvá-lo no [!DNL Profile Manager]e fazer upload do arquivo de saída para um servidor de sua escolha.

**Para configurar o servidor de exportação de segmentos**

O [!DNL Segment Export] recurso cria um único arquivo de saída no servidor de exportação de segmento, em vez de arquivos de saída separados criados em cada DPU. O servidor de exportação de segmento geralmente é configurado para execução no FSU.

No diretório Dataset\ no [!DNL Profile Manager], abra o [!DNL Segment Export.cfg] na Workstation e especifique o endereço do servidor. (Seu endereço pode ser um IP ou um nome de domínio totalmente qualificado.):

![](assets/segment_export_cfg.png)

Este é o IP do servidor da Análise de big data que recebe os resultados da exportação do segmento. Esta é uma configuração única. Se o não [!DNL Segment Export.cfg] estiver presente, as exportações não serão executadas.

**Para configurar os diretórios de exportação**

Para fins de segurança, os executáveis ou arquivos em lote executados após a exportação de um segmento devem residir no diretório Scripts\ configurável do servidor de exportação de segmento.

A saída [!DNL .part] e a saída final devem residir no diretório configurável Exportações. O comando a ser executado existe em Argumentos de Comando e Comando. As instâncias do %file% nos Argumentos de Comando serão substituídas pelo caminho do arquivo de saída.

>[!NOTE]
>
>Novo no Análise de big data 5.4, a pasta \Exportações é criada automaticamente. Os diretórios de exportação anteriores configurados antes da versão 5.4 exigiam um prefixo Exportações\ antes do nome de arquivo para cada exportação de segmento. A adição desse prefixo agora é redundante.

1. No servidor [!DNL Communications.cfg] de destino para [!DNL Segment Exports], adicione um SegmentExportServer à lista de servidores. (Exemplo mostrado em vermelho).

   ![](assets/communications_cfg_example.png)

   Diretório de exportações: Especifica onde colocar [!DNL .part] e exportar arquivos. Este pode ser um diretório compartilhado.

   Diretório de Scripts: Especifica o diretório de onde todos os arquivos executáveis ou em lote são executados.

1. [!DNL Access Control.cfg], no mesmo servidor, adicione acesso de leitura/gravação ao URI /SegmentExportServer/ ao Grupo de Acesso de Servidores de Cluster:

   ![](assets/accesscontrol_cfg_example.png)

1. Altere seus [!DNL .export] arquivos:

   ![](assets/segment_export_query_example.png)

1. Para cada perfil, o [!DNL Segment Export.cfg] está localizado no diretório Dataset\, com o seguinte conteúdo:

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. Certifique-se de que os diretórios a que se refere o Diretório de exportações e o Diretório de scripts existem.

   Somente executáveis e arquivos em lote no diretório Scripts podem ser executados como o comando de uma exportação de segmento.

**Para criar um arquivo de exportação de segmento**

1. Em um espaço de trabalho, crie uma Tabela de detalhes mostrando subconjuntos de dados (Visualização > Tabela de detalhes) e adicione atributos.
1. Se desejar, faça seleções no espaço de trabalho. Quaisquer seleções ou filtros são aplicados à exportação.

   ![](assets/create_segment_export_file.png)

1. No cabeçalho Tabela de detalhes, clique com o botão direito do mouse e selecione **[!UICONTROL Create Segment Export File]**.
1. Em [!DNL Save as], digite um nome para o [!DNL .export] arquivo.
1. No [!DNL .export] arquivo, configure os parâmetros conforme necessário.

   Quaisquer seleções ou filtros no espaço de trabalho são incorporados ao arquivo de exportação.

1. Save the [!DNL .export] file.

   O arquivo salvo é exibido na janela para que você [!DNL Profile Manager] salve no servidor. Quando você salva o arquivo no servidor, a exportação é iniciada.

