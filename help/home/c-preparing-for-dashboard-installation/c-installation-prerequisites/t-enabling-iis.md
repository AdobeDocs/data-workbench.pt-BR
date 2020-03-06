---
description: A primeira etapa é habilitar a função IIS no servidor de painel.
solution: Analytics
title: Habilitar IIS
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Habilitar IIS{#enabling-iis}

A primeira etapa é habilitar a função IIS no servidor de painel.

1. Em **[!UICONTROL Administrative Tools]**, abra o **[!UICONTROL Server Manager]**.
1. Clique com o botão direito do mouse no item de menu Funções na parte esquerda da **[!UICONTROL Server Manager]** janela.
1. Selecionar **[!UICONTROL Add Roles]**.
1. Selecione **[!UICONTROL Web Server (IIS)]** e continue com o **[!UICONTROL Add Roles Wizard]**. Certifique-se de que os seguintes serviços de função estejam ativados:

   | Recursos HTTP comuns |
   |---|
   | Conteúdo estático |
   | Documento padrão |
   | Navegação no diretório |
   | Erros de HTTP |
   | Redirecionamento HTTP |

   | Desenvolvimento de aplicativos |
   |---|
   | ASP.NET |
   | Extensibilidade .NET |
   | Extensões ISAPI |
   | Filtros ISAPI |

   | Saúde e diagnóstico |
   |---|
   | Registro HTTP |
   | Ferramentas de registro |
   | Monitor de solicitação |
   | Rastreamento |
   | Registro personalizado |

   | Segurança |
   |---|
   | Autenticação básica |
   | Autenticação do Windows |
   | Autenticação de URL |
   | Filtragem de solicitação |
   | Restrições de IP e domínio |

   | Ferramentas de gerenciamento |
   |---|
   | Console de gerenciamento do IIS |
   | Script e ferramentas de gerenciamento do IIS |
   | Serviço de gerenciamento |

1. Siga o Assistente para concluir a instalação.
