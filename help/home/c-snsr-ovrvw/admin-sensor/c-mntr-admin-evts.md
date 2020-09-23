---
description: Para detectar erros de sensor o mais rápido possível e repará-los antes que eles causem problemas importantes ou paralisações, você deve monitorar regularmente os registros de Eventos.
solution: Analytics
title: Monitorar eventos administrativos
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---


# Monitorar eventos administrativos{#monitoring-administrative-events}

Para detectar erros de sensor o mais rápido possível e repará-los antes que eles causem problemas importantes ou paralisações, você deve monitorar regularmente os registros de Eventos.

**Frequência recomendada:** Pelo menos por hora

Você pode monitorar esses eventos usando o Visualizador de Eventos do Windows ou o arquivo Unix Syslog e os [!DNL *.sensor-log] arquivos localizados por padrão na [!DNL Logs] pasta no diretório de [!DNL Sensor] instalação. Esses arquivos indicam a presença de erros durante a coleta de dados, especialmente se um usuário [!DNL Sensor] não conseguir se conectar aos dados de enfileiramento do público alvo [!DNL data workbench server] e start.

## Monitoramento de Eventos no Windows {#section-7c0443a356af4381bf22259654f5cd17}

O sensor registra erros no Log de aplicativos do Visualizador de Eventos do Windows com uma fonte de &quot;Adobe&quot;.

As mensagens são registradas como &quot;Informações&quot;, &quot;Aviso&quot; ou &quot;Erro&quot;, dependendo de sua gravidade.

**Para abrir o Visualizador** de Eventos do Windows:

* Clique em **Start > Painel de controle do Campaign > Ferramentas administrativas > Visualizador** de Eventos.

## Monitoramento de Eventos no Unix {#section-5de3947891fb47ac88b7c855e545d54a}

O sensor registra erros no [!DNL syslog] daemon.

O daemon syslog grava mensagens de erro em arquivos de registro com base nas regras especificadas no arquivo syslog.conf. Os erros são registrados com os sinalizadores &quot;LOG_DAEMON&quot; e &quot;LOG_NOTICE&quot; ou &quot;LOG_ERR&quot;, dependendo da gravidade.

**Para abrir o syslog do Unix**

O syslog do Unix normalmente está localizado em [!DNL /var/adm/messages] ou [!DNL /var/log/messages].

Navegue até o local apropriado e abra o syslog.

## Como entender os formatos de mensagem {#section-a0899add30fd4b2da58a23b9e3324693}

Todas as mensagens do sensor contêm a string &quot;Sensor&quot; e são numeradas para refletir a importância da mensagem sendo exibida.

| Número da mensagem | Significado da mensagem | String de mensagem |
|---|---|---|
| 1xxx | Informativo | Número de informações do sensor |
| 2xxx | Aviso | Aviso do sensor # |
| 3xxx | Erro de configuração | Erro de sensor # |
| 4xxx | Erro operacional | Erro de sensor # |
| 5xxx | Erro interno | Erro de sensor # |

>[!NOTE]
>
>Os avisos (2xxx) não estão em uso no momento. Esses números são reservados para uso futuro.

Sua ferramenta de gerenciamento de rede pode ser configurada para monitorar suas mensagens a cada 5 a 10 minutos em busca de erros na fonte do &quot;Sensor&quot; e alertar a equipe apropriada sobre problemas que possam exigir intervenção. Você pode optar por monitorar o sistema somente para determinados tipos de mensagens de Evento, como a sequência de caracteres &quot;Erro de sensor&quot;. Como alternativa, você pode aplicar regras diferentes a eventos com o prefácio &quot;Informações do sensor&quot;, &quot;Aviso do sensor&quot; e sequências de &quot;Erro do sensor&quot;.

## Como identificar mensagens importantes {#section-5a20f5dc18ca4012931d194db855e54e}

Nos registros de eventos, você deve prestar atenção especial e endereçar imediatamente quaisquer mensagens relacionadas ao tamanho da fila.

Por exemplo, mensagens como &quot; [!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot; precisam de atenção.

## Respondendo a mensagens de Evento do sensor {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tabelas que descrevem eventos de sensor e ações sugeridas para as plataformas de servidor da Web suportadas.

**Todas as plataformas**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mensagem de evento </th> 
   <th colname="col2" class="entry"> Ação sugerida </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Informações do sensor 1010: Sensor inicializado. </td> 
   <td colname="col2"> Nenhuma ação necessária. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informações do sensor 1011: Sensor terminado. Total de cliques na fila ## </td> 
   <td colname="col2"> Nenhuma ação necessária. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informações do sensor 1012: A fila de Adobe disk está #% cheia </td> 
   <td colname="col2"> Esta mensagem é registrada sempre que a utilização da fila de discos ultrapassa um limite de 10%. Se essa porcentagem continuar crescendo, as ações devem ser tomadas antes que a fila esteja cheia e os dados sejam perdidos. O problema mais provável é que o Sensor parou de se comunicar com o Insight Server. Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informações do sensor 1013: Configuração do sensor alterada </td> 
   <td colname="col2"> Nenhuma ação necessária. O sensor detectou uma alteração em um de seus arquivos de configuração e será recarregado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informações do sensor 1014: Problema ao semear gerador de números aleatórios </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informações do sensor 1016: Nome do arquivo de configuração carregado </td> 
   <td colname="col2"> Nenhuma ação necessária. O sensor carregou com êxito o arquivo de configuração listado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informações do sensor 1017: Nome do arquivo de experimento carregado </td> 
   <td colname="col2"> Nenhuma ação necessária. O sensor carregou com êxito o arquivo de experimento listado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 3016: Não é possível carregar o arquivo de configuração /mypath/myfile </td> 
   <td colname="col2"> Confirme se o arquivo de configuração do sensor especificado na configuração do servidor da Web existe e tem as permissões necessárias para ser lido pelo processo do servidor da Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensor 3017: Não é possível carregar o arquivo de configuração de experimento controlado /mypath/myfile </p> </td> 
   <td colname="col2"> <p>Confirme se o arquivo de experimento controlado especificado em txlogd.conf existe e se o processo txlogd tem as permissões necessárias para ler o arquivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 3018: Não é possível analisar listas de filtro de conteúdo. Verificar arquivo de configuração txlogd </td> 
   <td colname="col2"> Verifique a sintaxe das entradas ContentFilterInclude e ContentFilterExclude em txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 3023: Falha ao criar bloqueio (g_lockThrottle) </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 3024: Falha ao criar bloqueio (g_lockConfigCheck) </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 4014: Não foi possível abrir a fila de discos. </td> 
   <td colname="col2"> Verifique o nome do arquivo QueueFile em txlogd.conf e, se você acredita que esteja correto, entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 4020: Não é um arquivo de fila </td> 
   <td colname="col2"> Verifique o nome do arquivo QueueFile em txlogd.conf e, se você acredita que esteja correto, entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 4021: A fila está cheia </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 4022: Não é possível mapear o bloco de memória de comprimento &lt;x&gt; no deslocamento &lt;y&gt; </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 5012: Não foi possível criar mutex. </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 5013: Não foi possível adquirir mutex. </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 5030: Erro de bifurcação de desova. </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 5031: setsid falhou. </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 5032: Erro de bifurcação de desova. </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 5033: chdir falhou. </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 5034: Sinal recebido </td> 
   <td colname="col2"> O programa foi provavelmente encerrado por um sinal externo. Se a fonte desse sinal não puder ser determinada, entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 5035: Saída chamada do principal externo </td> 
   <td colname="col2"> Entre em contato com o Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erro de sensor 5036: txlogd já está em execução </td> 
   <td colname="col2"> Outra instância do daemon txlogd já está em execução. Pare a outra instância primeiro se quiser executar uma nova. </td> 
  </tr> 
 </tbody> 
</table>

**Servidor HTTP Apache/IBM**

| Mensagem de evento | Ação sugerida |
|---|---|
| Erro de sensor 3015: A diretiva VisualSciencesConfig está ausente de httpd.conf. | Este é um erro de configuração. A diretiva VisualSciencesConfig deve estar em httpd.conf com um parâmetro que é a localização de txlogd.conf. |
| Erro de sensor 3019: vys-cookie não foi chamado antes de vys-log. Entre em contato com o suporte. | Entre em contato com o Adobe ClientCare. |
| Erro de sensor 3025: Subsolicitação aponta para si mesmo | Entre em contato com o Adobe ClientCare. |

**Servidor AOL**

| Mensagem de evento | Ação sugerida |
|---|---|
| Erro de sensor 3015: a seção ns/server/[server]/module/[module] está ausente no arquivo de configuração do AOLServer. | Este é um erro de configuração. Correto, conforme indicado no erro. |
| Erro de sensor 3019: vys-cookie não foi chamado antes de vys-log. Entre em contato com o suporte. Entre em contato com o Adobe ClientCare. | Entre em contato com o suporte. Entre em contato com o Adobe ClientCare. |
| Erro de sensor 3020: VisualSciencesConfig ausente como primeira entrada na seção [section] no arquivo de configuração do AOLServer. | Este é um erro de configuração. Correto, conforme indicado no erro. |
| Erro de sensor 3021: VisualSciencesConfig não tem um valor na seção [section] no arquivo de configuração do AOLServer. | Este é um erro de configuração. Correto, conforme indicado no erro. |

**Servidores Web iPlanet e Java System**

| Mensagem de evento | Ação sugerida |
|---|---|
| Erro de sensor 3011: Diretiva de inicialização obrigatória. Como Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Este é um erro de configuração. A diretiva &quot;iPlanet init&quot; está faltando. |
| Erro de sensor 3015: o arquivo de configuração não está especificado na diretiva iPlanet Init | Este é um erro de configuração. O caminho para o arquivo de configuração não foi fornecido na diretiva iPlanet Init. |
| Erro de sensor 3019: vys-cookie não foi chamado antes de vys-log. Verifique o arquivo de configuração | o cookie vys deve ser especificado como a primeira diretiva NameTrans para cada servidor virtual de software. |

