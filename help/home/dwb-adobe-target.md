---
description: Integre o Análise de big data ao Adobe Target. Exporte segmentos de dados e preencha automaticamente os arquivos de exportação.
solution: Analytics
title: Integração do Análise de big data com o Adobe Target
topic: Data workbench
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Integração do Análise de big data com o Adobe Target

A integração do Adobe Data Workbench com o Adobe Target ficou mais fácil com os recursos do Análise de big data para exportar segmentos de dados e preencher automaticamente arquivos de exportação.

O Adobe Data Workbench fornece integração de ciclo fechado com o Adobe Target para compartilhar dados e gerar relatórios. Na Análise de big data, é possível analisar populações de segmentos significativos usando todos os dados disponíveis, incluindo conversões offline por canais como telefone, loja e assim por diante.

Por exemplo, um visitante procura sapatos em seu site, mas não converte. Em vez disso, o visitante baixa um cupom por 20% da próxima compra e compra uma camisa em sua loja. Usando o Análise de big data, você pode coletar esses dados e depois enviar os dados do perfil de volta para o Target para mostrar que o visitante comprou uma camisa offline. Você pode então direcionar uma campanha oferecendo uma gravata para o visitante, quando normalmente o Target pode tentar recomercializar sapatos para esse visitante.

## Configurar o Análise de big data com o Adobe Target

1. Clique com o botão direito do mouse no cabeçalho da [!UICONTROL Detail Table] janela.

   ![](assets/insight-to-tnt.png)

1. Selecione **[!UICONTROL New Target Export]** e digite o nome de um novo arquivo de exportação sob o **[!UICONTROL Save As]** comando no menu.

1. Clique em **[!UICONTROL Save Export File]**.

   Uma janela de modelo de exportação será aberta.

   Todas as informações do Adobe Target são preenchidas automaticamente. Ele constrói a lista de parâmetros com base no que você colocou na exportação do segmento. Quando concluído, o Análise de big data enviará os dados para o servidor do Adobe Target.

   **Observação:** O arquivo Modelo deve ser configurado pelo [!UICONTROL Profile Architect]. É necessário inserir [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host]e [!UICONTROL Mbox Name] . Se você tiver vários sites, preencha vários modelos e salve-os no servidor. Os modelos do Gerenciador de perfis estão localizados em `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Especifique o parâmetro de [!UICONTROL mboxPC] consulta.

   Se o nome do atributo Análise de big data for diferente de [!UICONTROL mboxPC], edite o Parâmetro de consulta apropriado e renomeie-o para _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   Quando você salvar o arquivo de exportação no servidor, a exportação será iniciada. Quando concluído, o [!UICONTROL TnTSend.exe] aplicativo iniciará e começará a enviar dados para a conta do Target.

## Configuração do Análise de big data para o Target

Conclua as seguintes tarefas no Adobe Target:

A análise de big data está transmitindo perfis de usuário para o Adobe Target. Para configurar a exportação para o Target, é necessário configurar e ativar sua API e fornecer os parâmetros **[!UICONTROL clientname]** e **[!UICONTROL domain postfix]** para o arquivo de configuração de exportação (`export.cfg`).

Uma nova opção booleana chamada **[!UICONTROL Oneshot]** foi adicionada aos arquivos de exportação de segmento. Esta opção está incluída no arquivo de modelo distribuído com o novo perfil. Se [!UICONTROL Oneshot] for definido como _true_, o `.export` arquivo será renomeado para `.export.done-TIMESTAMP` depois que a exportação for concluída, garantindo que o segmento nunca será exportado mais de uma vez. Isso é importante ao exportar para o Adobe Target.

**Observação:** Uma chamada do Análise de big data para o Adobe Target conta como uma [!UICONTROL mbox] chamada, exigindo uma chamada para cada perfil enviado. Consequentemente, os custos aumentam se forem necessárias várias chamadas entre as duas soluções.

Uma configuração incompleta produz a seguinte mensagem de erro no registro:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Configuração do Adobe Target para análise de big data

No Adobe Target, nenhuma configuração especial é necessária para que um cliente envie dados de perfil. As informações de perfil para um usuário são normalmente passadas na [!UICONTROL mbox] solicitação regular e os servidores tornarão os parâmetros de perfil disponíveis para uma configuração de campanha direcionada como funcionalidade padrão sem qualquer configuração adicional.

O Adobe Target tem a integração do Análise de big data integrada, que pode ser ativada na página Detalhes do superusuário cliente. Habilitar a opção superará os segmentos compartilhados a partir da Análise de big data no Adobe Target para que fiquem disponíveis para definição de metas.

## Definir relatórios de log HTTP em ExportIntegration.exe

Reduza os relatórios longos para [!UICONTROL HTTP.log] quando usar [!UICONTROL ExportIntegration.exe] para exportar arquivos de integração do Adobe Target.

Um novo arquivo de [!UICONTROL httpLoggingEI.cfg] configuração (localizado em `server\Admin\Export\httpLoggingEI.cfg`) permite reduzir o logon profundo no arquivo para [!UICONTROL HTTP.log] ao exportar dados usando [!UICONTROL ExportIntegration.exe]. Isso permite que você pare o registro detalhado de solicitações/respostas.

O registro em log detalhado já foi capturado em [!UICONTROL TnTSend.log] arquivos.

_True_ define o registro detalhado e _False_ interrompe o registro detalhado no [!UICONTROL HTTP.log] arquivo.

Na configuração Falso, somente uma mensagem de aviso será enviada para o [!UICONTROL HTTP.log] arquivo (conteúdo de informações não enviado).