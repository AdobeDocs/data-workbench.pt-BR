---
description: Um guia rápido para configurar uma API de consulta.
title: Configuração da API do Query
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
exl-id: 8b9dace8-4dad-434c-aec3-2f6ca872a5f6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# Configuração da API do Query{#query-api-setup}

{{eol}}

Um guia rápido para configurar uma API de consulta.

Siga as etapas abaixo para configurar a API de consulta:

1. Aquisição de certificados da API de consulta

   Enviar um email para a equipe de operações técnicas do Adobe Email - `Dataworkbench@adobe.com`.

   Forneça o nome CN que deseja usar para a API de consulta (forneça um nome genérico como `<Client>` Consultar API).

   >[!NOTE]
   >
   >As Tech Ops gerarão o certificado e o carregarão em um URL. Informe os consultores da Adobe após receber a notificação da Tech Ops sobre a geração bem-sucedida do ticket, para que o ticket seja enviado a você por eles de volta.

1. Download e extração do estunnel da API. Receba o arquivo api-stunnel do seu consultor.

   Certifique-se de que o Perl esteja instalado no computador.

   Na pasta extraída (o caminho da pasta onde você copia o arquivo), copie o certificado da API de consulta dentro do *duende* pasta.

1. Configurar o Stunnel.conf

   Deve haver um arquivo chamado *stunnel.conf* dentro do *Stunnel* pasta (onde você copiou o certificado).

   Edite o arquivo no Bloco de notas.

   ![](assets/dwb_impl_API1.png)

   Altere os parâmetros da seguinte maneira: ![](assets/dwb_impl_API2.png)

   Dois parâmetros precisam ser alterados neste arquivo.

   * *Cert* = O nome no certificado. Neste exemplo, é Aadhithiya Ramani QAPI Client.pem.
   * *Connect* =O nome do servidor para a DPU principal.

1. Copiando o *Query.pm*.

   O *Query.pm* O arquivo estará disponível na Pasta da API do Insight.

   Copie o *Query.pm* e cole-o na pasta Biblioteca de Perl (normalmente será *C:\Perl64\lib *, mas verifique onde a Perl está instalada em sua máquina).

1. Modifique o *api-http.pl* arquivo

   O arquivo api-http.pl estará disponível na pasta api-stunnel.

   Somente um parâmetro a ser modificado

   *Meu $perfil* = O nome do perfil para o qual você está configurando a API de consulta.

1. Instale a API do Query.

   Abra o prompt de comando do sistema como &quot;Administrador&quot; e navegue até o diretório onde você extraiu o *duende* como mostrado: ![](assets/dwb_impl_API3.png)

   Execute o seguinte comando *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   Depois de executar o comando, uma janela aparecerá declarando que a variável *duende* está instalado.

   >[!NOTE]
   >
   >Depois de executar o comando, uma janela aparecerá declarando que a variável *duende* está instalado.

1. Teste da configuração do stunnel da API de consulta

   A etapa final desse processo será testar a configuração da API de consulta. No prompt de comando usado para instalar o diretório api-stunnel. ![](assets/dwb_impl_API5.png)

   Execute o script Perl disponível nessa pasta usando o seguinte comando* perl api-http.pl*. ![](assets/dwb_impl_API6.png)

   Após executar o script, os resultados devem ser semelhantes à captura de tela abaixo (a data e o valor no resultado variam de acordo com a hora e outros parâmetros no perfil em que você configurou a API de consulta (na etapa 6). ![](assets/dwb_impl_API7.png)
