---
description: Integre o Data Workbench ao Adobe Target. Exportar segmentos de dados e preencher automaticamente arquivos de exportação.
title: Integração do Data Workbench com o Adobe Target
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Integração do Data Workbench com o Adobe Target

A integração do Adobe Data Workbench com o Adobe Target ficou mais fácil com os recursos do Data Workbench para exportar segmentos de dados e preencher automaticamente arquivos de exportação.

A Adobe Data Workbench oferece integração de ciclo fechado com a Adobe Target para compartilhar dados e gerar relatórios. No Data Workbench, é possível analisar populações para segmentos significativos usando todos os dados disponíveis, incluindo conversões offline por canais como telefone, loja e assim por diante.

Por exemplo, um visitante procura sapatos em seu site, mas não converte. Em vez disso, o visitante baixa um cupom por 20% da próxima compra e, em seguida, compra uma camisa em sua loja. Usando o Data Workbench, você pode coletar os dados e enviar esses dados de perfil para o Target para mostrar que o visitante comprou uma camisa offline. Você pode então direcionar uma campanha oferecendo uma gravata para o visitante, quando normalmente o Target pode tentar comercializar sapatos para o visitante.

## Configurar o Data Workbench com o Adobe Target

1. Clique com o botão direito do mouse no cabeçalho na janela [!UICONTROL Detail Table].

   ![](assets/insight-to-tnt.png)

1. Selecione **[!UICONTROL New Target Export]** e insira o nome de um novo arquivo de exportação no comando **[!UICONTROL Save As]** no menu .

1. Clique em **[!UICONTROL Save Export File]**.

   Uma janela de modelo de exportação será aberta.

   Todas as informações do Adobe Target são preenchidas automaticamente. Ela constrói a lista de parâmetros com base no que você coloca na exportação do segmento. Quando concluído, o Data Workbench enviará os dados para o servidor do Adobe Target.

   **Observação:** o arquivo Modelo deve ser configurado pelo  [!UICONTROL Profile Architect]. Os [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host] e [!UICONTROL Mbox Name] precisam ser inseridos. Se você tiver vários sites, preencha vários modelos e salve-os no servidor. Os modelos do Gerenciador de perfis estão localizados em `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Especifique o parâmetro de consulta [!UICONTROL mboxPC].

   Se o nome do atributo de Data Workbench for diferente de [!UICONTROL mboxPC], você deverá editar o Parâmetro de Consulta apropriado e renomeá-lo para _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   Quando você salva o arquivo de exportação no servidor, a exportação é iniciada. Quando concluído, o aplicativo [!UICONTROL TnTSend.exe] será iniciado e começará a enviar dados para a conta do Target.

## Configuração do Data Workbench para Target

Conclua as seguintes tarefas no Adobe Target:

O Data Workbench está transmitindo perfis de usuário ao Adobe Target. Para configurar a exportação para o Target, você precisa configurar e habilitar sua API e fornecer os parâmetros **[!UICONTROL clientname]** e **[!UICONTROL domain postfix]** para o arquivo de configuração de exportação (`export.cfg`).

Uma nova opção booleana chamada **[!UICONTROL Oneshot]** foi adicionada a arquivos de exportação de segmentos. Essa opção é incluída no arquivo de modelo distribuído com o novo perfil. Se [!UICONTROL Oneshot] estiver definido como _true_, o arquivo `.export` será renomeado para `.export.done-TIMESTAMP` após a conclusão da exportação, garantindo que o segmento nunca será exportado mais de uma vez. Isso é importante ao exportar para o Adobe Target.

**Observação:** uma chamada do Data Workbench para o Adobe Target conta como uma  [!UICONTROL mbox] chamada, exigindo uma chamada para cada perfil enviado. Consequentemente, os custos aumentam se várias chamadas forem necessárias entre as duas soluções.

Uma configuração incompleta produz a seguinte mensagem de erro no log:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Configuração do Adobe Target para Data Workbench

No Adobe Target, nenhuma configuração especial é necessária para um cliente enviar dados de perfil. As informações de perfil de um usuário normalmente são passadas na solicitação regular [!UICONTROL mbox] e os servidores tornarão os parâmetros de perfil disponíveis para uma configuração de campanha direcionada como funcionalidade padrão sem qualquer configuração adicional.

O Adobe Target tem integração do Data Workbench incorporada, que pode ser ativada na página Detalhes do cliente do superusuário. Ativar a opção exibirá segmentos que são compartilhados a partir do Data Workbench no Adobe Target para torná-lo disponível para direcionamento.

## Definir relatórios de log HTTP em ExportIntegration.exe

Reduza os relatórios longos para [!UICONTROL HTTP.log] ao usar [!UICONTROL ExportIntegration.exe] para exportar arquivos de integração do Adobe Target.

Um novo arquivo de configuração [!UICONTROL httpLoggingEI.cfg] (localizado em `server\Admin\Export\httpLoggingEI.cfg`) permite reduzir o log detalhado para o arquivo [!UICONTROL HTTP.log] para ao exportar dados usando [!UICONTROL ExportIntegration.exe]. Isso permite interromper o registro detalhado de solicitação/resposta.

O registro detalhado já está capturado nos arquivos [!UICONTROL TnTSend.log].

__ O Truesets indica o registro detalhado e o log detalhado  __ Falsestops para o  [!UICONTROL HTTP.log] arquivo.

Na configuração Falso , somente uma mensagem de aviso será enviada para o arquivo [!UICONTROL HTTP.log] (Conteúdo de informações não enviado).
