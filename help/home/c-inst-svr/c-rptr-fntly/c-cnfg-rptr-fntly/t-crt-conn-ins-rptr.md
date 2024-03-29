---
description: Se firewalls de rede não impedirem acesso ao servidor repetidor a partir de máquinas Insight, você poderá criar uma conexão entre o servidor repetidor e o Insight para gerenciar o servidor repetidor usando o Insight.
title: Criar uma conexão entre o Insight e o Repetidor
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 4%

---

# Criar uma conexão entre o Insight e o Repetidor{#creating-a-connection-between-insight-and-repeater}

{{eol}}

Se firewalls de rede não impedirem acesso ao servidor repetidor a partir de máquinas Insight, você poderá criar uma conexão entre o servidor repetidor e o Insight para gerenciar o servidor repetidor usando o Insight.

**Para criar uma conexão entre [!DNL Insight] e o servidor repetidor**

1. Em [!DNL Insight], no [!DNL Admin] clique no botão **[!UICONTROL Configure Connections to Servers]** para abrir a área de trabalho Configurar conexões com servidores .
1. No [!DNL Insight.cfg] , clique com o botão direito do mouse **[!UICONTROL Servers]** e clique em **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. Para o novo servidor, preencha os seguintes parâmetros:

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parâmetro... </th> 
   <th colname="col2" class="entry"> Especificar... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2">(Opcional) O nome que você deseja <span class="keyword"> Insight</span> para usar para representar o servidor repetidor em sua interface do usuário. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Endereço </td> 
   <td colname="col2"> <p>O nome do host ou endereço IP numérico do seu servidor repetidor. </p> <p>Exemplo: <span class="filepath"> Repeater.mycompany.com</span> ou 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificado de cliente SSL </td> 
   <td colname="col2"> <p>Opcional, a menos que você tenha mais de um certificado. O nome do arquivo que contém o certificado digital para esta cópia de <span class="keyword"> Insight</span>. (Esse é o arquivo que você baixou ao instalar <span class="keyword"> Insight</span>.) </p> <p>Exemplo: <span class="filepath"> Samantha Smith.pem</span></p> <p>Se deixar este parâmetro em branco, <span class="keyword"> Insight</span> O usa qualquer certificado presente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidor SSL </p> <p>Nome comum </p> </td> 
   <td colname="col2">O nome comum atribuído ao servidor repetidor. Esse nome deve corresponder ao nome comum atribuído ao servidor repetidor em seu certificado de licença. Se você tiver acesso ao arquivo de certificado do repetidor (<span class="filepath"> Certificados\server_cert.pem</span>), você pode encontrar o nome comum abrindo o arquivo com um editor de texto, como o Notepad. O nome comum é identificado no campo NC do certificado. </td> 
  </tr> 
 </tbody> 
</table>

1. Salve o arquivo clicando com o botão direito do mouse **[!UICONTROL (modified)]** na parte superior da janela e clicando em **[!UICONTROL Save]**. [!DNL Insight] O tentará se conectar ao servidor repetidor usando as configurações especificadas. Se uma conexão for estabelecida, um ícone verde de servidor aparecerá no [!DNL Servers Manager] interface. Se uma conexão não puder ser estabelecida, um ícone vermelho será exibido.

   Para obter mais informações sobre o [!DNL Servers Manager] consulte o * [!DNL Insight] Guia do usuário*.
