---
description: Novos recursos introduzidos no Análise de big data 6.0.4, incluindo correções de erros e problemas conhecidos.
solution: Analytics
title: Notas de versão do Análise de big data 6.0
topic: Data workbench
uuid: b348425e-3304-4db7-a280-479a34452bdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Notas de versão do Análise de big data 6.0

Novos recursos introduzidos no Análise de big data 6.0.4, incluindo correções de erros e problemas conhecidos.

## Novos Recursos {#section-1225066ea8f44cf68e42e019d0bca816}

A análise de big data (Insight 6.0) inclui esses novos recursos e visualizações para recursos de relatório adicionais e ferramentas de análise preditiva.

| Recursos do Análise de big data | Descrição |
|---|---|
| [Visualização de funil](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | A visualização de funil permite definir o fluxo de processos sequenciais de seus clientes e fornece visibilidade ao fallout de visitantes em cada etapa do processo. |
| [Cluster do visitante](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | O agrupamento permite que você aproveite as características do cliente para categorizar os visitantes dinamicamente e gerar conjuntos de clusters com base em entradas de dados selecionadas para análise e direcionamento do cliente. |
| [Análise de correções](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | A Análise de correlação permite identificar rapidamente relações de dados relevantes para estender e aprimorar sua análise. |
| [Distribuição do DeviceAtlas atualizada](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | O arquivo JSON DeviceAtlas será distribuído em um arquivo .bundle (um .tar.gz renomeado) junto com DeviceAtlas.dll e DeviceAtlas64.dll. |

## Requisitos de atualização do cliente {#section-f316103b48374b6eac77e8feb5c47ecf}

Conclua estas tarefas de atualização para os recursos do cliente da análise de big data (Insight 6.0):

**Atualização do arquivo .zbin para o cliente**

A análise de big data agora oferece suporte a um Editor de método de entrada (IME) como um processo de entrada de texto secundário que permite inserir caracteres internacionais do teclado usando uma caixa de texto flutuante. A análise de big data suporta inglês por padrão, mas também permite carregar outros arquivos para suportar idiomas internacionais, como um teclado chinês virtual (Pinyin IME).

Um novo arquivo de dicionário (um arquivo .zbin) é necessário para o aplicativo cliente antes de atualizar para a versão 6.0. Você pode obter o arquivo .zbin necessário do perfil Software and Docs (Softdocs).

Pré-requisitos:

* Antes de atualizar para o cliente Insight 6.0 e o Servidor de relatórios 6.0, o administrador do Insight deve primeiro atualizar para o Insight Server 6.0.
* O administrador do Insight precisará escolher um arquivo zbin com base no idioma (pt-br.zbin, zh-cn.zbin), copiar o arquivo de idioma, renomeá-lo para insight.zbin e colocar o arquivo renomeado no diretório raiz do Servidor de relatórios no qual o executável está localizado. Em seguida, reinicie o Insight Report Server.

Consulte os Requisitos [de atualização do](../../../home/c-release-notes-insight/release-notes.md) servidor para obter informações adicionais sobre atualização do servidor.

**Para atualizar o arquivo zbin para o cliente (da versão 5.x para a 6.0)**

1. Para garantir que o cliente não seja atualizado do Insight Server durante essa atualização, defina o argumento Insight.cfg como falso.

   ```
   Update Software = bool: false
   ```

1. Reinicie o cliente Insight.
1. Navegue até o perfil Software and Docs (perfil SoftDocs) e baixe o arquivo necessário **[!UICONTROL Insight.zbin]** : [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Copie o arquivo Insight.zbin para a mesma pasta do arquivo Insight.exe.
1. Para garantir que o cliente Insight seja atualizado a partir do Insight Server, altere o argumento do arquivo Insight.cfg para true:

   ```
   Update Software = bool: true
   ```

1. Reinicie o cliente.

   Seu cliente será sincronizado com o servidor e você verá uma mensagem informando que seu cliente está baixando. Ao concluir o download, você receberá uma mensagem perguntando se deseja reiniciar o cliente Insight.
1. Clique em **OK** para reiniciar o cliente.

   O cliente iniciará e atualizará para a versão 6.0.

1. Reinicie o cliente novamente para que a sincronização do cliente Insight.zbin tenha efeito.

   Se você receber a seguinte mensagem, isso significa que o zbin não foi colocado no local correto da pasta ao lado do arquivo Insight.exe.

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   Para corrigir o problema, exclua Insight.exe e renomeie a versão mais recente de Insight.exe.old para Insight.exe e inicie novamente com a Etapa 1 acima.

## Requisitos de atualização do servidor {#section-d6edba8b36234957ba8d06b555667a5a}

Conclua estas tarefas de atualização para os recursos do servidor Insight 6.0:

**Atualize todos os pacotes** do Insight Server 6.0. O Insight 6.0 inclui pacotes de servidor que precisam ser atualizados, incluindo o novo perfil do Predictive Analytics.

>[!IMPORTANT]
>
>Recomenda-se que os usuários atualizem seus clusters de servidores com novas instalações do Insight Server 6.0 ao atualizar.

Também é recomendável que o cliente atualize seus clusters de servidor com a nova instalação do Insight Server 6.0.

## Cluster do Servidor de Atualização

**Prepare o arquivo de idioma (arquivo .zbin).** O administrador do Insight seleciona o `<language>.zbin` arquivo para o idioma desejado (por exemplo: en-us.zbin , zh-cn.zbin) localizado na `/localization/<language>.zbin` pasta. Em seguida, o administrador copia o arquivo de idioma e o renomeia para &quot;insight.zbin&quot;.

Depois de preparar o arquivo de idioma (.zbin), o Insight Client e o Servidor de relatórios precisam ser atualizados. O Insight Client é atualizado durante o processo [de atualização do](../../../home/c-release-notes-insight/release-notes.md)cliente, mas na maioria dos casos o administrador do Insight atualizará o Servidor de relatórios.

**Atualize o Servidor de relatórios com um arquivo de idioma (arquivo .zbin)**.

Para todos os idiomas, o Servidor de Relatório 6.0 requer o arquivo &quot;insight.zbin&quot; copiado para a pasta raiz do Servidor de Relatório.

Atualize os arquivos de idioma do Servidor de relatórios:

1. Adicione o arquivo renomeado como &quot;insight.zbin&quot; ao diretório raiz do ReportServer.
1. O arquivo de configuração do Servidor de relatórios (reportserver.cfg) requer configurações de fonte para idiomas de byte duplo. Por exemplo, o chinês exige a adição de fontes usando o SimSun:

   ```
   Report Server.cfg - Add Fonts 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Um parâmetro para o Report Server 6.0 precisa ser transmitido na linha de comando para localização, por exemplo:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Se uma localidade não for especificada, o Servidor de relatórios assumirá como padrão o idioma selecionado no arquivo insight.zbin.

   Siga as etapas para iniciar o ReportServer como um serviço com os parâmetros Locale:

   1. Inicie um prompt de comando como administrador.
   1. Navegue até a pasta de instalação do ReportServer.
   1. Digite o seguinte comando para iniciar o serviço:

      * Para inglês: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Para chinês: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Para verificar se o ReportServer está em execução com os parâmetros corretos:

   1. Abra o Windows Service Manager.
   1. Clique com o botão direito do mouse [!DNL Adobe Insight Report Server - Properties].
   O caminho para o executável conterá os parâmetros:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Modifique o arquivo de Configuração de perfil para o Predictive Analytics**. O administrador do Insight precisará modificar o arquivo custom profile.cfg para incluir o perfil do Predictive Analytics disponível no Insight.

Exemplo da entrada profile.cfg:

```
Example ("profile.cfg"): 
Profile = profileInfo:  
  Active = bool: true 
  Directories = vector: 5 items 
    0 = string: Base\\  
    1 = string: Predictive Analytics\\ 
    2 = string: Geography\\ 
    3 = string: Adobe SC\\ 
    4 = string: Custom Profile\\ 
```

**Atualize o arquivo** PAServer.cfg. Se você quiser enviar trabalhos de cluster do Predictive Analytics para os Servidores Insight, será necessário configurar o arquivo PAServer.cfg para lidar com envios de cluster do lado do servidor.

O perfil personalizado deve herdar o PAServer.cfg do perfil do Predictive Analytics (Server\Profiles\Predictive Analytics\Dataset). Configure e salve o PAServer.cfg de acordo com o site de implementação.

>[!NOTE]
>
>Depois que PAServer.cfg é configurado e salvo no perfil personalizado, é necessário reiniciar o Insight Server no site.

**Atualizar o Servidor de Relatório.** Será necessário atualizar as fontes e os parâmetros de inicialização do Servidor de relatórios.

Pré-requisitos:

* Antes de atualizar o Report Server 6.0, o administrador do Insight deve primeiro atualizar para o Insight Server 6.0.
* Para todos os idiomas, o Servidor de Relatório 6.0 requer a adição do Insight.zbin à pasta raiz do Servidor de Relatório. Verifique se o arquivo `base/localization/<language>.zbin` foi copiado e renomeado para &quot;insight.zbin&quot;. Copie-o para a raiz do diretório do Servidor de relatórios.

Atualize os parâmetros Fontes e Inicialização:

1. O Servidor de Relatório exige a configuração de fonte para byte duplo para produzir em idiomas diferentes,

   por exemplo:

   Report Server.cfg - Adicionar fontes

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. O parâmetro para o Servidor de relatórios 6.0 precisa ser passado na linha de comando para fins de localização.

   Para iniciar o Servidor de relatórios como um serviço com os parâmetros Locais:

   1. Pare o Serviço de Servidor de Relatórios.
   1. Inicie um prompt de comando como administrador.
   1. Navegue até a pasta de instalação do Servidor de relatórios.
   1. Digite o seguinte comando para iniciar o serviço:

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

Para verificar se o Servidor de relatórios está em execução com os parâmetros corretos:

1. Abrir o Windows Service Manager
1. Clique com o botão direito do mouse [!DNL Adobe Insight Report Server - Properties].
1. O caminho para o executável conterá os parâmetros:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Atualize o feed de dados do SiteCatalyst para o Insight 6.0**. O formato de nome de arquivo do feed de dados do SiteCatalyst para o Insight 6.0 foi alterado.

Formato de nome de arquivo atual:

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

Novo formato de nome de arquivo:

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>Essa alteração não afeta os usuários implantados atualmente com a versão *wbench/ecom* do feed de dados do SiteCatalyst.

A alteração no formato do nome de arquivo permitirá o uso total das declarações de hora de início e término do Insight durante o processamento do log. Isso permite que o processo avalie se o conteúdo do arquivo deve ser lido, em vez de filtrar todos os arquivos de origem usando uma pesquisa linha por linha.

Na maioria dos casos, um processo de renomeação foi implementado após o recebimento do arquivo para fornecer o uso total desse recurso. Essa modificação fornece a convenção de nomenclatura necessária por padrão, sem a necessidade e a sobrecarga de um processo secundário.

Para usar o novo feed de dados do SiteCatalyst:

1. Determine como o processo de recebimento processará o novo formato de nome de arquivo.

   Os scripts padrão de renomeação/movimentação implantados durante a implementação movem os arquivos com uma extensão &quot;.gz&quot; e só executa uma renomeação se o nome do arquivo corresponder ao formato do nome do arquivo com o RSID anterior.

   O novo formato de nome de arquivo:

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. Avalie os caminhos de origem de log definidos para confirmar que todos os arquivos serão lidos.

   Se você já tiver um script de renomeação implementado, então já está definindo suas fontes de log para ler esse novo formato de arquivo.

## Correções {#section-203f917dd6224114a1f801309c4c2cee}

* Agora, a combinação de teclas para deixar um espaço de trabalho sem salvar as alterações foi atualizada para **[!UICONTROL `<Ctrl>`+`<Backspace>`]**. Anteriormente, você evitava alterações e fechava um espaço de trabalho pressionando`<Ctrl>`+`<Delete>`.

## Notas de versão do Análise de big data 6.0.4{#data-workbench-release-notes}

Novos recursos introduzidos no Análise de big data 6.0.4, incluindo correções de erros e problemas conhecidos.

Para exibir os recursos e as correções anteriores com base em cada versão anterior, consulte os arquivos [das notas de](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html)versão.

## Novos Recursos {#section-2-1225066ea8f44cf68e42e019d0bca816}

O Análise de big data 6.0.4 inclui esses novos recursos e visualizações para recursos de relatório adicionais e ferramentas de análise preditiva.

**Visualização** de Pontuação de propensão. A análise de big data calcula as pontuações para cada visitante como uma probabilidade estimada de que um evento especificado possa ocorrer. A visualização de Pontuação do visitante permite criar uma dimensão de pontuação que fornece uma probabilidade de um evento especificado para cada visitante de interesse com base nas variáveis de entrada.

![](assets/visitor_scoring_visual.png)

Consulte Pontuação de [propensão](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40) para obter mais informações sobre esse recurso.

## Requisitos de atualização {#section-08bd6fe3da8740fcb19688e8cac6f223}

**A ID da Fonte de Log deve ser definida**. A partir da versão 6.04, se a ID da fonte de registro não estiver definida, você receberá o seguinte erro:

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

A Gravação de Linhas por Fonte de Log foi adicionada no Análise de big data 6.0 e pode ser definida no perfil personalizado Log Processing.cfg adicionando uma ID de Fonte de Log exclusiva. Se você tiver uma ID de fonte de registro em branco, poderá ver problemas de processamento de log, como a leitura incompleta dos dados de fonte de log e outras discrepâncias.

```
Log Processing.cfg 
Log Sources = vector: 2 items 
  0 = VisualSensor: 
    Compressed = bool: false 
    Log Paths = vector: 1 items 
      0 = Path: \some path\ 
    Log Server = serverInfo:  
      Address = string:  
      Name = string:  
      Port = int: 80 
      Proxy Address = string:  
      Proxy Password = string:  
      Proxy Port = int: 8080 
      Proxy User Name = string:  
      SSL Client Certificate = string: Certificates\\server_cert.pem 
      SSL Server Common Name = string:  
      Use SSL = bool: false 
     
Log Source ID = string: <Name your ID Here>
    Name = string:  
    Recursive = bool: false
```

**Capacidade de delegar recursos do FSU**

Em [!DNL Profiles/`<profilename>`/dataset/Cluster.cfg], agora é possível especificar FSUs (File Server Units, Unidades de servidor de arquivos) separadas para os servidores Normalizar e Lista de origem. Esses serviços não estão mais vinculados ao FSU mestre.

>[!NOTE]
>
>Se o Servidor de lista não for especificado, o Servidor de lista herdará as configurações do Servidor de normalização.

Example in the [!DNL cluster.cfg] file.

```
Cluster = ClusterConfig: 
  Normalize Server = serverInfo: 
    Address = string: normalizeserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false 
  List Server = serverInfo: 
    Address = string: sourcelistserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false
```

## Erros corrigidos {#section-3b4b85a35f534288adf8a5246ef028cc}

* No Análise de big data 6.0, a Matriz de correlação e o Construtor de cluster não suportam Computação em segundo plano. Isso foi corrigido na versão 6.0.4.
* Anteriormente, se você tivesse uma seleção no Funil e removesse uma etapa, poderia ocorrer uma violação de acesso. Isso foi resolvido.
* Corrigida uma possível condição de bloqueio na Exportação de segmento que pode causar problemas em condições de carga pesada.
