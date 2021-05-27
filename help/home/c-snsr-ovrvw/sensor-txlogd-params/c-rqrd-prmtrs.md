---
description: Informações sobre os parâmetros txlogd.conf do sensor necessários.
title: Parâmetros obrigatórios
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
exl-id: 782e11e9-b11b-4003-9669-f31187208ec3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

---

# Parâmetros obrigatórios{#required-parameters}

Informações sobre os parâmetros txlogd.conf do sensor necessários.

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Neste Parâmetro... </th> 
   <th colname="col2" class="entry"> Especificar... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>Uma string de caracteres que identifica exclusivamente este <span class="wintitle"> Sensor</span>. </p> <p> <span class="wintitle"> </span> Sensoriza a SensorID a cada registro de evento que ela envia para o servidor do  <span class="keyword"> Data Workbench</span>. O SensorID permite que os dados do evento deste servidor da Web sejam distintos dos dados do evento capturados por outros <span class="wintitle"> Sensores</span>. </p> <p>Embora um SensorID possa consistir em qualquer cadeia de caracteres, por convenção, o nome do servidor da Web cujos eventos o <span class="wintitle"> Sensor</span> está capturando é usado. Usar o nome do servidor como SensorID facilita determinar a fonte de um evento durante a fase de análise. Ela também garante que a SensorID seja exclusiva na implementação. </p> <p>Exemplo: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>O endereço do <span class="keyword"> servidor do Data Workbench</span> para o qual este <span class="wintitle"> Sensor</span> envia dados de evento. </p> <p>Observação:  <p>Ao trabalhar em um ambiente em cluster, o <span class="wintitle"> Sensor</span> deve ser configurado para acessar o <span class="keyword"> servidor do Data Workbench principal</span> para evitar problemas de sincronização. No Data Workbench, você pode exibir informações sobre o processamento <span class="keyword"> dos servidores do Data Workbench</span> no cluster usando o item de menu Servidores Relacionados no <span class="wintitle"> Gerenciador de Servidores</span>. Para obter mais informações sobre o <span class="wintitle"> Gerenciador de Servidores</span>, consulte o <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span> Guia</i>. </p> <p>Se o servidor da Web puder resolver nomes de servidor por meio do DNS, você poderá especificar o endereço do servidor por nome. Caso contrário, você deve especificar o endereço IP numérico do servidor. </p> <p>Exemplo: <span class="filepath"> ServerAddress 10.1.0.7</span> ou </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Se o <span class="wintitle"> Sensor</span> se comunica com <span class="keyword"> servidor do Data Workbench</span> usando HTTP ou HTTPS. Defina como "on" para HTTPS ou "off" para HTTP. </p> <p>Exemplo: <span class="filepath"> SSL em</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>A porta na qual o <span class="keyword"> servidor do Data Workbench</span> escuta os dados do evento. </p> <p>Exemplo: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Obrigatório somente se o parâmetro SSL estiver definido como "on". </p> <p>O nome comum do <span class="keyword"> servidor do Data Workbench</span> para o qual este <span class="wintitle"> Sensor</span> envia dados de evento. </p> <p>O valor especificado deve corresponder exatamente ao nome comum que aparece no certificado de licença <span class="keyword"> do servidor do Data Workbench</span>. </p> <p>Exemplo: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Obrigatório somente se o parâmetro SSL estiver definido como "on". </p> <p>O diretório no qual o arquivo da autoridade de certificação (<span class="filepath"> trust_ca_cert.pem</span>) está localizado </p> <p>Exemplos: </p> <p> <span class="filepath"> CertPath /usr/local/visual sensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Não é necessário para instalações do <span class="wintitle"> Sensor</span> no Microsoft Windows 2000 ou 2003 Server computadores que executam o Serviço de Informações da Internet (IIS) versões 5.x ou 6.x. </p> <p>O nome totalmente qualificado do arquivo de fila de discos. </p> <p>Embora você possa atribuir qualquer nome a esse arquivo, por convenção, o arquivo da fila é nomeado <span class="filepath"> VisualSensor.dat</span>. </p> <p>Para instalações de <span class="wintitle"> Sensor</span> no Unix, você pode colocar esse arquivo em qualquer lugar. No Windows que executa um servidor Web Java, você deve colocar esse arquivo no mesmo diretório do transmissor. Para todos os outros servidores da Web, esse arquivo deve residir no diretório /var/queue. </p> <p>Exemplo: <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Observação:  Certifique-se de que o dispositivo ao qual você atribui esse arquivo tenha espaço livre suficiente para acomodar uma fila do tamanho necessário. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Um número inteiro que representa o tamanho do arquivo da fila de discos em MB. </p> <p>Para instalações do <span class="wintitle"> Sensor</span> no Microsoft Windows, o próprio arquivo de fila é criado no mesmo diretório que o transmissor e é nomeado <span class="filepath"> Diskq2000.log</span>. </p> <p>O exemplo a seguir define o tamanho da fila como 200 MB: </p> <p>QueueSize 200 </p> <p>O exemplo a seguir define o tamanho da fila como 2 GB: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>
