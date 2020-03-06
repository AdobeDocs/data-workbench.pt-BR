---
description: Após a instalação, o certificado digital emitido pela Adobe atua como uma chave que permite executar o Servidor de relatórios.
solution: Analytics
title: Revalidação do certificado digital
topic: Data workbench
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Revalidação do certificado digital{#re-validating-the-digital-certificate}

Após a instalação, o certificado digital emitido pela Adobe atua como uma chave que permite executar o Servidor de relatórios.

**Frequência recomendada:** Conforme necessário

Para funcionar corretamente, um certificado digital deve estar atualizado.

Para se manter atualizado, seu certificado digital deve ser revalidado regularmente (geralmente, a cada 30 dias, mas isso pode variar dependendo do seu acordo com a Adobe). Se o computador tiver acesso à Internet, o processo de revalidação será completamente transparente. [!DNL Report Server] conecta-se automaticamente ao Adobe License Server e valida novamente o certificado quando necessário. Se sua máquina não tiver acesso à Internet, você deverá baixar um certificado novo e validado do Adobe License Server e instalá-lo em sua máquina usando as etapas fornecidas em [Download e instalação do certificado](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)digital.
