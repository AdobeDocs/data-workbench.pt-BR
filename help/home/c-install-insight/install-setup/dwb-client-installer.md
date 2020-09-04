---
description: A Data Workbench fornece um assistente de configuração para instalar o aplicativo da estação de trabalho (cliente).
title: Assistente de configuração da estação de trabalho
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 1%

---


# Assistente de configuração da estação de trabalho{#workstation-setup-wizard}

A Data Workbench fornece um assistente de configuração para instalar o aplicativo da estação de trabalho (cliente).

## Instalação da estação de trabalho usando o Assistente de configuração {#section-58da9bb6196c46eab3b54146913fdcb8}

Inicie o assistente de instalação executável e percorra cada etapa para instalar o programa do cliente da estação de trabalho. Após a instalação da estação de trabalho, você pode se conectar a servidores e perfis.

1. Duplo clique no executável do instalador da estação de trabalho.
1. Clique em **Sim** para permitir que o programa seja instalado no Windows.
1. Selecione um **idioma** para o assistente de configuração.

   O assistente abrirá:

   ![](assets/6_4_workstation_wizard.png)

1. Clique em **Avançar** na caixa de diálogo **Bem-vindo ao Assistente** de configuração de Data Workbench.

1. Selecione para instalar uma **nova instalação** ou para **atualizar ou reparar** uma instalação existente.

   **A nova instalação** substitui todos os arquivos instalados anteriormente.

   **A atualização** atualiza sua estação de trabalho para a versão mais recente ou permite reparar uma instalação existente. A Data Workbench comparará os arquivos **Insight.exe** instalados e executará o Assistente de configuração da estação de trabalho se uma versão mais recente do cliente estiver disponível.

1. Selecione o local de instalação:

   **Instalações típicas** em uma pasta e um local padrão.

   * Por padrão, os arquivos de programa são salvos em:

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * Por padrão, os arquivos de dados (perfis, certificados, registros de rastreamento e arquivos de usuário) são salvos em:

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >Um arquivo genérico ***Insight.cfg*** sem detalhes do servidor será instalado inicialmente. É recomendável usar o arquivo ***Insight.cfg*** recém-instalado e personalizá-lo, em vez de mover um arquivo de uma instalação anterior. Como o caminho para a instalação da estação de trabalho foi alterado, recomenda-se a adição de fontes, a remoção da Pasta *do* usuário e a remoção de *TraceFileComponent *.

1. (opcional) Selecione **Personalizado** para escolher o pacote de idiomas e o local do programa e dos arquivos de dados.
1. Selecione o local para **os atalhos no Menu** Start.

   ![](assets/6_4_workstation_wizard_folder.png)

   Clique em **Não criar uma pasta** Menu Start para não instalar um atalho no Menu Start do Windows.

1. Clique em **Próximo.** Será exibido um resumo dos caminhos e idiomas de localização do arquivo selecionado. Clique em **Instalar.**

1. Localize o Certificado **de** Data Workbench.

   Se o assistente de configuração não conseguir localizar o certificado de Data Workbench durante a instalação, ele abrirá uma caixa de diálogo para navegar até o local do certificado (um arquivo **.pem** localizado por padrão na pasta **Certificados** do cliente) ou clique em **Ignorar** para localizar o certificado após a instalação.

   Clique em **Instalar** após localizar o certificado.

1. Depois que o assistente de instalação for concluído e a Data Workbench instalada, clique em **Concluir** para concluir a instalação.

   >[!NOTE]
   >
   >O local de log padrão do Assistente para configuração da estação de trabalho em `C:\Users\<userName>\AppData\Local\Temp`.

   Marque a caixa de seleção **Iniciar aplicativo** para abrir a bancada após a configuração.

1. **Configure conexões** com servidores no **[!DNL Insight.cfg]** arquivo.

   Após a instalação da estação de trabalho, a área de trabalho Enhanced Workstation Configuration Experience será aberta com informações adicionais sobre a [inserção de informações](/help/home/c-get-started/c-insght-config-param.md) de conexão do servidor no arquivo *Insight.cfg* e uma opção para selecionar um perfil no menu suspenso. Você também pode visualização o status da conexão com seus servidores.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Pastas de instalação {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

A estrutura da pasta de Data Workbench tem dois locais de instalação:

* **Arquivos** de programa O **Insight.exe** e os arquivos de suporte do cliente (**Insight.ini**) agora estão localizados por padrão em

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* A pasta **Appdata** .

   **Insight.cfg**, perfis, certificados, registros de rastreamento e arquivos de usuário agora estão localizados por padrão em

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Você pode definir o caminho para a pasta **Appdata** no `Insight.ini` arquivo:

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Desinstalação da estação de trabalho {#section-5ce2e233fe4348469ef1b3c451dd5b70}

A Data Workbench agora inclui um executável para desinstalar a estação de trabalho (localizado por padrão em **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Inicie e siga as etapas para remover os arquivos da estação de trabalho de Data Workbench do disco rígido.

>[!NOTE]
>
>Você pode iniciar o executável **unins000.exe** da pasta, usando o atalho **Desinstalar Data Workbench** no Menu do Start ou em **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
