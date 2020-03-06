---
description: Informações sobre permissões de arquivo UNIX do sensor, como o módulo coletor, o processo do transmissor, o arquivo de configuração e muito mais.
title: Permissões de arquivo UNIX do sensor
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Permissões de arquivo UNIX do sensor{#sensor-unix-file-permissions}

Informações sobre permissões de arquivo UNIX do sensor, como o módulo coletor, o processo do transmissor, o arquivo de configuração e muito mais.

## O módulo do coletor {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualidade </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome do arquivo </p> </td> 
   <td colname="col2"> <p>mod_visual_sciences.so (nos servidores da Web Apache e IBM HTTP) </p> <p>libvisual_sciences.so e J2EECollector.jar (nos servidores de aplicativos J2EE) </p> <p>aol_visual_sciences.so (em servidores da Web AOL) </p> <p>saf_visual_sciences.so (em servidores Web Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permissões padrão </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP e Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx —x —x (servidores Web J2EE, AOL e Sun Java) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lido por </p> </td> 
   <td colname="col2"> <p>O servidor da Web, que às vezes é executado como usuário raiz, mas com mais frequência é executado em uma conta de usuário específica </p> <p>Se o servidor da Web for executado em uma conta não raiz, as permissões nesse arquivo deverão permitir que essa conta a leia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Funciona como </p> </td> 
   <td colname="col2"> <p>Um processo filho no servidor da Web </p> <p>Processos filho são executados em uma conta de usuário especificada na configuração do servidor da Web. Em muitos servidores, esta é uma conta especial com privilégios muito limitados chamada "ninguém". mas nem todos os servidores da Web usam essa conta. Verifique o arquivo de configuração do servidor da Web para determinar qual conta de usuário está definida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Leituras de </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>O arquivo diskQueue </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grava em </td> 
   <td colname="col2"> O arquivo diskQueue </td> 
  </tr> 
 </tbody> 
</table>

## O processo do transmissor {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualidade </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome do arquivo </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permissões padrão </p> </td> 
   <td colname="col2"> <p>rw- r— r— (IBM HTTP, AOL e servidores Web Sun Java) </p> <p>rw- rw- r— (servidores Web Apache e servidores de aplicativos J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lido por </td> 
   <td colname="col2"> O programa transmissor </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escrito por </td> 
   <td colname="col2"> -- </td> 
  </tr> 
 </tbody> 
</table>

## O arquivo de configuração {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualidade </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome do arquivo </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permissões padrão </p> </td> 
   <td colname="col2"> <p>rw- r— r— (IBM HTTP, AOL e servidores Web Sun Java) </p> <p>rw- rw- r— (servidores Web Apache e servidores de aplicativos J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lido por </td> 
   <td colname="col2"> <p>O módulo do coletor </p> <p>O programa transmissor </p> <p>O administrador responsável pela instalação, configuração e manutenção do sensor </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escrito por </td> 
   <td colname="col2"> O administrador responsável pela instalação, configuração e manutenção do sensor </td> 
  </tr> 
 </tbody> 
</table>

## O arquivo da autoridade de certificação {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualidade </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome do arquivo </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permissões padrão </p> </td> 
   <td colname="col2"> <p>rw- r— r— (IBM HTTP, AOL e servidores Web Sun Java) </p> <p>rw- rw- r— (servidores Web Apache e servidores de aplicativos J2EE) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lido por </td> 
   <td colname="col2"> O programa transmissor </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Escrito por </td> 
   <td colname="col2"> -- </td> 
  </tr> 
 </tbody> 
</table>

## A fila de discos {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Qualidade </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome do arquivo </td> 
   <td colname="col2"> Definido pelo usuário </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Permissões padrão </td> 
   <td colname="col2"> rw- rw- rw- (Todos os tipos de servidor) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lido por </p> </td> 
   <td colname="col2"> <p>O módulo do coletor </p> <p>O programa transmissor </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escrito por </p> </td> 
   <td colname="col2"> <p>O módulo do coletor </p> <p>O programa transmissor </p> </td> 
  </tr> 
 </tbody> 
</table>

