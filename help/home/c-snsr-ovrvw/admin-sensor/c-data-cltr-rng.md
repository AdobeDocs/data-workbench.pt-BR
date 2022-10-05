---
description: Verifique se o coletor está sendo executado usando métodos diferentes.
title: Confirmar se o coletor de dados está em execução
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
exl-id: 1235d741-1ddf-4a65-8377-3d8a9b4ba0d3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 3%

---

# Confirmar se o coletor de dados está em execução{#confirming-that-the-data-collector-is-running}

{{eol}}

Verifique se o coletor está sendo executado usando métodos diferentes.

**Frequência recomendada:** A cada 5-10 minutos

* [Use a funcionalidade de teste de site no transmissor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Verifique se [!DNL Sensor] está configurando um cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Usando o teste do site {#section-a5a697c3252e40f184c0b662926170f2}

Uma maneira de verificar se o coletor está em execução é ativar a função de Teste de Site no transmissor. Quando você ativa o Teste do site, o transmissor envia periodicamente (a cada 60 segundos) uma solicitação do GET ao servidor da Web no qual o coletor está sendo executado. Se o teste do site não receber uma resposta do servidor da Web, ele grava uma mensagem de erro no syslog e envia uma mensagem de erro para o [!DNL data workbench server] (gravado no arquivo de registro do sensor).

Se o Site Test receber uma resposta do servidor da Web, ele procurará no arquivo da fila um pacote do servidor da Web. Se o pacote não for exibido (indicando que o coletor não estava sendo executado para capturar o evento), o Site Test grava uma mensagem de erro no syslog e envia uma mensagem de erro ao Adobe (que também é gravada no arquivo de log do sensor).

Nas solicitações que o Site Test envia para o servidor da Web, o Site Test define o valor User-Agent como &quot; [!DNL Sensor] Teste.&quot; Se você não quiser que essas solicitações apareçam em seu conjunto de dados, adicione o &quot; [!DNL Sensor] Testar&quot; User-Agent na [!DNL Baseline Robots List.txt] ou o [!DNL Extended Robots List.txt] no [!DNL Lookups] na pasta [!DNL data workbench server].

**Para ativar o Teste de site no transmissor**

1. Localize a variável [!DNL txlogd.conf] na máquina em que [!DNL Sensor] O está em execução e o abre em um editor de texto.

1. No [!DNL txlogd.conf] , localize a linha &quot;SiteTest&quot; e configure-a conforme mostrado abaixo. Se o seu [!DNL txlogd.conf] não inclui a linha &quot;SiteTest&quot;, basta adicionar a linha ao final do arquivo de configuração.

   SiteTest http, *serverAddress*, *porta*, *recurso*

   em que *serverAddress* é o nome ou endereço IP do servidor da Web, *porta* é a porta de escuta HTTP do servidor e *recurso* é o recurso específico que você deseja que o Site Test solicite ao testar o servidor. Observe que *recurso* pode incluir uma string de consulta.

   Exemplo: SiteTest http,localhost,80,/index.jsp

   Para testar vários servidores da Web, basta especificar várias linhas do SiteTest .

## Como verificar um cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Outra maneira de verificar se o coletor está sendo executado em um servidor da Web é verificar se [!DNL Sensor] O está configurando um cookie nas respostas que o servidor da Web está retornando aos clientes. Se o coletor estiver funcionando, o servidor da Web retorna um cookie &quot;v1st&quot;.

É possível renomear o cookie. Se tiver feito isso, você deve procurar pelo nome especificado, não v1st.

Você pode executar essa verificação usando um script automatizado ou um agente de monitoramento. Para obter um exemplo de script ou ajuda adicional com essa tarefa, entre em contato com os Serviços de consultoria da Adobe.
