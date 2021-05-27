---
description: Após a instalação, o certificado digital emitido pelo Adobe atua como uma chave que permite executar o Servidor de relatórios.
title: Revalidar o certificado digital
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 13%

---

# Revalidar o certificado digital{#re-validating-the-digital-certificate}

Após a instalação, o certificado digital emitido pelo Adobe atua como uma chave que permite executar o Servidor de relatórios.

**Frequência recomendada:** conforme necessário

Para funcionar adequadamente, um certificado digital deve estar atualizado.

Para permanecer atual, o certificado digital deve ser revalidado regularmente (geralmente, a cada 30 dias, mas isso pode variar dependendo do contrato com o Adobe). Se o computador tiver acesso à Internet, o processo de revalidação será totalmente transparente. [!DNL Report Server] O se conecta automaticamente ao Adobe License Server e valida novamente o certificado quando necessário. Se a máquina não tiver acesso à Internet, baixe um certificado novo e validado do Adobe License Server e instale-o na máquina usando as etapas fornecidas em [Download e instalação do certificado digital](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
