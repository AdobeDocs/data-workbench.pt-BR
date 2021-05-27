---
description: É possível criar facilmente uma definição de Exportação de segmento na visualização Tabela de detalhes no Cliente do Data Workbench.
title: Exportar segmento
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# Exportar segmento{#segment-export}

É possível criar facilmente uma definição de Exportação de segmento na visualização Tabela de detalhes no Cliente do Data Workbench.

Além disso, [!DNL Segment Exports] combina automaticamente seus resultados a um único servidor, em vez de produzir resultados parciais em cada DPU que você deve combinar usando um processo externo. Você pode criar um arquivo de exportação de segmento, salvá-lo no [!DNL Profile Manager] e fazer upload do arquivo de saída para um servidor de sua escolha.

**Para configurar o servidor de exportação de segmentos**

O recurso [!DNL Segment Export] cria um único arquivo de saída no servidor de exportação de segmento, em vez de arquivos de saída separados criados em cada DPU. Normalmente, o servidor de exportação de segmentos é configurado para ser executado no FSU.

No diretório Dataset\ no [!DNL Profile Manager], abra o [!DNL Segment Export.cfg] na Workstation e especifique o endereço do servidor. (Seu endereço pode ser um IP ou um nome de domínio totalmente qualificado.):

![](assets/segment_export_cfg.png)

Esse é o IP do servidor do Data Workbench que recebe os resultados da exportação do segmento. Essa é uma configuração única. Se [!DNL Segment Export.cfg] não estiver presente, as exportações não serão executadas.

**Para configurar os diretórios de exportação**

Para fins de segurança, os executáveis ou arquivos em lote executados após a exportação de um segmento devem residir no diretório Scripts\ configurável do servidor de exportação de segmento.

O [!DNL .part] e a saída final devem residir no diretório de exportações configuráveis. O comando a ser executado existe em Argumentos de Comando e Comando. As instâncias do %file% nos Argumentos de Comando serão substituídas pelo caminho do arquivo de saída.

>[!NOTE]
>
>Novo na Data Workbench 5.4, a pasta \Exportações é criada automaticamente. Os diretórios de exportação anteriores configurados antes da versão 5.4 exigiam um prefixo Exportações\ antes do nome do arquivo para cada exportação de segmento. A adição desse prefixo agora é redundante.

1. Em [!DNL Communications.cfg] no servidor de destino para [!DNL Segment Exports], adicione um SegmentExportServer à lista de servidores. (Exemplo mostrado em vermelho).

   ![](assets/communications_cfg_example.png)

   Diretório de exportações: Especifica onde colocar [!DNL .part] e arquivos de saída. Pode ser um diretório compartilhado.

   Diretório de scripts: Especifica o diretório de onde todos os arquivos executáveis ou em lote são executados.

1. [!DNL Access Control.cfg], no mesmo servidor, adicione acesso de leitura/gravação ao URI /SegmentExportServer/ ao Grupo de acesso dos servidores de cluster:

   ![](assets/accesscontrol_cfg_example.png)

1. Altere seus arquivos [!DNL .export]:

   ![](assets/segment_export_query_example.png)

1. Para cada perfil, o [!DNL Segment Export.cfg] está localizado no diretório Dataset\, com o seguinte conteúdo:

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. Verifique se os diretórios mencionados no Diretório de exportações e no Diretório de scripts existem.

   Somente executáveis e arquivos em lote no diretório Scripts podem ser executados como o comando de uma exportação de segmento.

**Para criar um arquivo de exportação de segmento**

1. Em um espaço de trabalho, crie uma Tabela de detalhes mostrando subconjuntos de dados (Visualização > Tabela de detalhes) e adicione atributos.
1. Se desejar, faça seleções no espaço de trabalho. (Qualquer seleção ou filtro é aplicado à exportação.)

   ![](assets/create_segment_export_file.png)

1. No cabeçalho da Tabela de detalhes, clique com o botão direito do mouse e selecione **[!UICONTROL Create Segment Export File]**.
1. Em [!DNL Save as], digite um nome para o arquivo [!DNL .export].
1. No arquivo [!DNL .export], configure os parâmetros conforme necessário.

   Quaisquer seleções ou filtros no espaço de trabalho são incorporados no arquivo de exportação.

1. Salve o arquivo [!DNL .export].

   O arquivo salvo é exibido no [!DNL Profile Manager] para que você salve no servidor. Quando você salva o arquivo no servidor, a exportação é iniciada.
