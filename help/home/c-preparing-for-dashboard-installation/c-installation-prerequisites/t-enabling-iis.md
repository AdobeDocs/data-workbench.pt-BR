---
description: A primeira etapa é habilitar a função do IIS no servidor do painel.
title: Habilitar IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# Habilitar IIS{#enabling-iis}

A primeira etapa é habilitar a função do IIS no servidor do painel.

1. Em **[!UICONTROL Administrative Tools]**, abra o **[!UICONTROL Server Manager]**.
1. Clique com o botão direito do mouse no item de menu Funções na parte esquerda da janela **[!UICONTROL Server Manager]**.
1. Selecionar **[!UICONTROL Add Roles]**.
1. Selecione **[!UICONTROL Web Server (IIS)]** e continue com **[!UICONTROL Add Roles Wizard]**. Certifique-se de que os seguintes Serviços de função estejam habilitados:

   | Recursos HTTP comuns |
   |---|
   | Conteúdo estático |
   | Documento padrão |
   | Navegação de diretórios |
   | Erros HTTP |
   | Redirecionamento HTTP |

   | Desenvolvimento de aplicativos |
   |---|
   | ASP.NET |
   | Extensibilidade do .NET |
   | Extensões ISAPI |
   | Filtros ISAPI |

   | Saúde e diagnóstico |
   |---|
   | Registro HTTP |
   | Ferramentas de registro |
   | Monitor de Solicitação |
   | Rastreamento |
   | Registro personalizado |

   | Segurança |
   |---|
   | Autenticação básica |
   | Autenticação do Windows |
   | Autenticação de URL |
   | Solicitar Filtragem |
   | Restrições de IP e domínio |

   | Ferramentas de gerenciamento |
   |---|
   | Console de Gerenciamento do IIS |
   | Script e ferramentas de gerenciamento do IIS |
   | Serviço de gerenciamento |

1. Siga o Assistente para concluir a instalação.
