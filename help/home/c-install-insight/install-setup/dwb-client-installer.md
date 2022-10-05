---
description: O Data Workbench fornece um assistente de configuração para instalar o aplicativo da estação de trabalho (cliente).
title: Assistente de configuração da estação de trabalho
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
exl-id: bfd9f2ad-282a-4be8-9f66-53e045648ef1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 1%

---

# Assistente de configuração da estação de trabalho{#workstation-setup-wizard}

{{eol}}

O Data Workbench fornece um assistente de configuração para instalar o aplicativo da estação de trabalho (cliente).

## Instalação da estação de trabalho usando o Assistente de configuração {#section-58da9bb6196c46eab3b54146913fdcb8}

Inicie o executável do assistente de instalação e percorra cada etapa para instalar o programa cliente da estação de trabalho. Após a instalação da estação de trabalho, você pode se conectar a servidores e perfis.

1. Clique duas vezes no executável do instalador da estação de trabalho.
1. Clique em **Sim** para permitir que o programa instale no Windows.
1. Selecione um **Idioma** para o assistente de configuração.

   O assistente abrirá:

   ![](assets/6_4_workstation_wizard.png)

1. Clique em **Próximo** no **Bem-vindo ao Assistente de Configuração do Data Workbench** caixa de diálogo.

1. Selecione para instalar um **Nova instalação** ou **Atualizar ou reparar** uma instalação existente.

   **Nova instalação** substitui todos os arquivos instalados anteriormente.

   **Atualizar** atualiza sua estação de trabalho para a versão mais recente ou permite reparar uma instalação existente. O Data Workbench comparará o instalado **Insight.exe** e execute o Assistente de configuração da estação de trabalho se uma versão mais recente do cliente estiver disponível.

1. Selecione o local de instalação:

   **Típica** O instala em uma pasta e um local padrão.

   * Por padrão, os arquivos de programas são salvos em:

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * Os arquivos de dados (perfis, certificados, logs de rastreamento e arquivos de usuário) são salvos por padrão em:

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >Um genérico ***Insight.cfg*** O arquivo sem detalhes do servidor será instalado inicialmente. É recomendável usar o ***Insight.cfg*** e personalize-o em vez de mover um arquivo de uma instalação anterior. Como o caminho para instalar a estação de trabalho foi alterado, a adição de fontes, a remoção do *Pasta do usuário*, e a remoção de *TraceFileComponent * é recomendada.

1. (opcional) Selecione **Personalizado** para escolher o pacote de idiomas e o local do programa e dos arquivos de dados.
1. Selecione o local para **atalhos no menu Iniciar**.

   ![](assets/6_4_workstation_wizard_folder.png)

   Clique em **Não criar uma pasta do menu Iniciar** para não instalar um atalho no Menu Iniciar do Windows.

1. Clique em **Avançar.** Um resumo dos caminhos e idiomas de localização de arquivo selecionados será exibido. Clique em **Instalar.**

1. Localize a variável **Certificado Data Workbench**.

   Se o assistente de configuração não conseguir localizar o certificado do Data Workbench durante a instalação, ele abrirá uma caixa de diálogo para navegar até o local do certificado (uma **.pem** arquivo localizado por padrão no cliente **Certificados** ou clique em **Ignorar** para localizar o certificado após a instalação.

   Clique em **Instalar** depois de localizar o certificado.

1. Após concluir o assistente de configuração e instalar o Data Workbench, clique em **Concluir** para concluir a configuração.

   >[!NOTE]
   >
   >O local de log padrão do Assistente de configuração da estação de trabalho em  `C:\Users\<userName>\AppData\Local\Temp`.

   Selecione o **Iniciar aplicativo** caixa de seleção para abrir o workbench após a configuração.

1. **Configurar conexões** para servidores em **[!DNL Insight.cfg]** arquivo.

   Após a instalação da estação de trabalho, o espaço de trabalho Enhanced Workstation Configuration Experience será aberto com informações adicionais sobre [inserir informações de conexão do servidor](/help/home/c-get-started/c-insght-config-param.md) no *Insight.cfg* e uma opção para selecionar um perfil no menu suspenso. Você também pode visualizar o status da conexão com seus servidores.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Pastas de instalação {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

A estrutura da pasta de Data Workbench tem dois locais de instalação:

* **Arquivos de programa** O **Insight.exe** e suporte a arquivos do cliente (**Insight.ini**) agora estão localizadas por padrão em

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* O **Appdata** pasta.

   **Insight.cfg**, perfis, certificados, logs de rastreamento e arquivos de usuário agora estão localizados por padrão em

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Você pode definir o caminho para a variável **Appdata** na pasta `Insight.ini` arquivo:

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Desinstalação da estação de trabalho {#section-5ce2e233fe4348469ef1b3c451dd5b70}

O Data Workbench agora inclui um executável para desinstalar a estação de trabalho (localizada por padrão em **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Inicie e siga as etapas para remover os arquivos da estação de trabalho do Data Workbench do seu disco rígido.

>[!NOTE]
>
>Você pode iniciar o **unins000.exe** executável da pasta, usando o **Desinstalar Data Workbench** atalho do Menu Iniciar ou do **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
