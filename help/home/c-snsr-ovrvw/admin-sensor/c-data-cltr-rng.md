---
description: Verifique se o coletor está sendo executado usando métodos diferentes.
title: Confirmar se o coletor de dados está em execução
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Confirmar se o coletor de dados está em execução{#confirming-that-the-data-collector-is-running}

Verifique se o coletor está sendo executado usando métodos diferentes.

**Frequência recomendada:** a cada 5-10 minutos

* [Use a funcionalidade de teste de site no transmissor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Verifique se [!DNL Sensor] está configurando um cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Usando o Teste do Site {#section-a5a697c3252e40f184c0b662926170f2}

Uma maneira de verificar se o coletor está em execução é ativar a função de Teste de Site no transmissor. Quando você ativa o Teste do site, o transmissor envia periodicamente (a cada 60 segundos) uma solicitação do GET ao servidor da Web no qual o coletor está sendo executado. Se o Teste do Site não receber uma resposta do servidor da Web, ele grava uma mensagem de erro no syslog e envia uma mensagem de erro para o [!DNL data workbench server] (que é gravado no arquivo de log do sensor).

Se o Site Test receber uma resposta do servidor da Web, ele procurará no arquivo da fila um pacote do servidor da Web. Se o pacote não for exibido (indicando que o coletor não estava sendo executado para capturar o evento), o Site Test grava uma mensagem de erro no syslog e envia uma mensagem de erro ao Adobe (que também é gravada no arquivo de log do sensor).

Nas solicitações que o Teste do Site envia para o servidor da Web, o Teste do Site define o valor Agente-Usuário como &quot;[!DNL Sensor] Teste.&quot; Se não quiser que essas solicitações apareçam em seu conjunto de dados, adicione o Agente do Usuário &quot;[!DNL Sensor] Teste&quot; ao arquivo [!DNL Baseline Robots List.txt] ou [!DNL Extended Robots List.txt] na pasta [!DNL Lookups] no [!DNL data workbench server].

**Para ativar o Teste de site no transmissor**

1. Localize o arquivo [!DNL txlogd.conf] na máquina em que [!DNL Sensor] está em execução e abra-o em um editor de texto.

1. No arquivo [!DNL txlogd.conf], localize a linha &quot;SiteTest&quot; e configure-a conforme mostrado abaixo. Se o arquivo [!DNL txlogd.conf] não incluir a linha &quot;SiteTest&quot;, basta adicionar a linha ao final do arquivo de configuração.

   SiteTest http, *serverAddress*, *port*, *resource*

   onde *serverAddress* é o nome ou endereço IP do servidor da Web, *port* é a porta de escuta HTTP do servidor e *resource* é o recurso específico que você deseja que o Teste do Site solicite ao testar o servidor. Observe que *resource* pode incluir uma sequência de consulta.

   Exemplo: SiteTest http,localhost,80,/index.jsp

   Para testar vários servidores da Web, basta especificar várias linhas do SiteTest .

## Verificando se há um cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Outra maneira de verificar se o coletor está em execução em um servidor da Web é verificar se [!DNL Sensor] está configurando um cookie nas respostas que o servidor da Web está retornando aos clientes. Se o coletor estiver funcionando, o servidor da Web retorna um cookie &quot;v1st&quot;.

É possível renomear o cookie. Se tiver feito isso, você deve procurar pelo nome especificado, não v1st.

Você pode executar essa verificação usando um script automatizado ou um agente de monitoramento. Para obter um exemplo de script ou ajuda adicional com essa tarefa, entre em contato com os Serviços de consultoria da Adobe.
