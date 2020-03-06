---
description: Verifique se o coletor está sendo executado usando métodos diferentes.
solution: Insight
title: Confirmando se o coletor de dados está em execução
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Confirmando se o coletor de dados está em execução{#confirming-that-the-data-collector-is-running}

Verifique se o coletor está sendo executado usando métodos diferentes.

**Frequência recomendada:** A cada 5 a 10 minutos

* [Use a funcionalidade de teste de site no transmissor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2)
* [Verifique se o [!DNL Sensor] está configurando um cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Usando o teste de site {#section-a5a697c3252e40f184c0b662926170f2}

Uma maneira de verificar se o coletor está em execução é ativar a função Site Test no transmissor. Quando você ativa o Site Test, o transmissor envia periodicamente (a cada 60 segundos) uma solicitação GET para o servidor da Web no qual o coletor está sendo executado. Se o Site Test não receber uma resposta do servidor da Web, ele gravará uma mensagem de erro no syslog e enviará uma mensagem de erro para o [!DNL data workbench server] (que é gravada no arquivo de log do sensor).

Se o Site Test receber uma resposta do servidor da Web, ele procurará um pacote do servidor da Web no arquivo de fila. Se o pacote não for exibido (indicando que o coletor não estava sendo executado para capturar o evento), o Site Test gravará uma mensagem de erro no syslog e enviará uma mensagem de erro para a Adobe (que também é gravada no arquivo de log do sensor).

Nas solicitações que o Site Test envia para o servidor da Web, o Site Test define o valor User-Agent como &quot; [!DNL Sensor] Test&quot;. Se você não quiser que essas solicitações apareçam em seu conjunto de dados, adicione o User-Agent &quot; [!DNL Sensor] Testar&quot; ao [!DNL Baseline Robots List.txt] arquivo ou ao [!DNL Extended Robots List.txt] arquivo na [!DNL Lookups] pasta na [!DNL data workbench server].

**Para ativar o Teste de site no transmissor**

1. Localize o [!DNL txlogd.conf] arquivo no computador onde [!DNL Sensor] está sendo executado e abra-o em um editor de texto.

1. No [!DNL txlogd.conf] arquivo, localize a linha &quot;SiteTest&quot; e configure-a como mostrado abaixo. Se o seu [!DNL txlogd.conf] arquivo não incluir a linha &quot;SiteTest&quot;, basta adicionar a linha ao final do arquivo de configuração.

   SiteTest http, *serverAddress*, *porta*, *recurso*

   onde *serverAddress* é o nome ou endereço IP do servidor da Web, *port* é a porta de escuta HTTP do servidor e *resource* é o recurso específico que você deseja que o Site Test solicite ao testar o servidor. Observe que o *recurso* pode incluir uma string de consulta.

   Exemplo: SiteTest http,localhost,80,/index.jsp

   Para testar vários servidores da Web, basta especificar várias linhas do SiteTest.

## Verificando se há um cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Outra maneira de verificar se o coletor está sendo executado em um servidor da Web é verificar se [!DNL Sensor] está configurando um cookie nas respostas que o servidor da Web está retornando para os clientes. Se o coletor estiver funcionando, o servidor da Web retornará um cookie &quot;v1st&quot;.

É possível renomear o cookie. Se você tiver feito isso, deverá procurar pelo nome especificado, não por v1st.

É possível realizar essa verificação usando um script automático ou agente de monitoramento. Para obter uma amostra de script ou ajuda adicional com essa tarefa, entre em contato com os Serviços de consultoria da Adobe.
