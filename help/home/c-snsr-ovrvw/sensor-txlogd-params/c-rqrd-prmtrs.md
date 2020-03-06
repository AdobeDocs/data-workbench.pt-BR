---
description: Informações sobre os parâmetros txlogd.conf necessários do Sensor.
solution: Insight
title: Parâmetros obrigatórios
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Required Parameters{#required-parameters}

Informações sobre os parâmetros txlogd.conf necessários do Sensor.

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
   <td colname="col2"> <p>Uma string de caracteres que identifica exclusivamente esse <span class="wintitle"> Sensor</span>. </p> <p> <span class="wintitle"> O sensor</span> anexa a SensorID a cada registro de evento que envia para o servidor <span class="keyword"></span>da análise de big data. A SensorID permite que os dados de eventos deste servidor Web sejam diferenciados dos dados de eventos capturados por outros <span class="wintitle"> Sensores</span>. </p> <p>Embora uma SensorID possa consistir em qualquer sequência de caracteres, por convenção, o nome do servidor da Web cujos eventos o <span class="wintitle"> Sensor</span> está capturando é usado. Usar o nome do servidor como SensorID facilita determinar a origem de um evento durante a fase de análise. Ela também garante que a SensorID seja exclusiva na implementação. </p> <p>Exemplo: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>O endereço do servidor <span class="keyword"> da análise de big data para o qual este</span> Sensor <span class="wintitle"></span> envia dados do evento. </p> <p>Observação:  <p>Ao trabalhar em um ambiente clusterizado, <span class="wintitle"> o Sensor</span> deve ser configurado para acessar o servidor <span class="keyword"></span> da análise de big data principal para evitar problemas de sincronização. Na Análise de big data, é possível exibir informações sobre os servidores <span class="keyword"> da análise de big data de processamento no cluster usando o item de menu Servidores relacionados no Gerenciador</span> de <span class="wintitle"></span>servidores. Para obter mais informações sobre o Gerenciador <span class="wintitle"> de</span>Servidores, consulte o Guia <i><span class="keyword"> do sensor</span><span class="wintitle"> da Análise</span></i>de big data. </p> <p>Se o servidor Web puder resolver nomes de servidor por meio do DNS, você poderá especificar o endereço do servidor por nome. Caso contrário, você deve especificar o endereço IP numérico do servidor. </p> <p>Exemplo: <span class="filepath"> ServerAddress 10.1.0.7</span> ou </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Se o <span class="wintitle"> Sensor</span> se comunica com o servidor <span class="keyword"></span> da análise de big data usando HTTP ou HTTPS. Defina como "on" para HTTPS ou "off" para HTTP. </p> <p>Exemplo: <span class="filepath"> SSL em</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>A porta na qual o servidor <span class="keyword"></span> da análise de big data escuta os dados do evento. </p> <p>Exemplo: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Obrigatório somente se o parâmetro SSL estiver definido como "ativado". </p> <p>O nome comum do servidor <span class="keyword"> da análise de big data para o qual este</span> Sensor <span class="wintitle"></span> envia dados do evento. </p> <p>O valor especificado deve corresponder exatamente ao nome comum que aparece no certificado de licença do servidor <span class="keyword"></span> da análise de big data. </p> <p>Exemplo: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Obrigatório somente se o parâmetro SSL estiver definido como "ativado". </p> <p>O diretório no qual o arquivo da autoridade de certificação (<span class="filepath"> trust_ca_cert.pem</span>) está localizado </p> <p>Exemplos: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Não é necessário para instalações de <span class="wintitle"> Sensor</span> em máquinas do Microsoft Windows 2000 ou 2003 Server que executam o Internet Information Service (IIS) versões 5.x ou 6.x. </p> <p>O nome totalmente qualificado do arquivo de fila de discos. </p> <p>Embora você possa atribuir qualquer nome a esse arquivo, por convenção, o arquivo de fila é denominado <span class="filepath"> VisualSensor.dat</span>. </p> <p>Para instalações de <span class="wintitle"> Sensores</span> no Unix, você pode colocar esse arquivo em qualquer lugar. No Windows executando um servidor da Web Java, você deve colocar esse arquivo no mesmo diretório do transmissor. Para todos os outros servidores da Web, esse arquivo deve residir no diretório /var/queue. </p> <p>Exemplo: Arquivo <span class="filepath"> de fila /var/queue/VisualSensor.dat</span> </p> <p> <p>Observação:  Verifique se o dispositivo ao qual você atribui esse arquivo tem espaço livre suficiente para acomodar uma fila do tamanho necessário. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>Um número inteiro que representa o tamanho do arquivo de fila de discos em MB. </p> <p>Para instalações de <span class="wintitle"> Sensor</span> no Microsoft Windows, o próprio arquivo de fila é criado no mesmo diretório do transmissor e é chamado de <span class="filepath"> Diskq2000.log</span>. </p> <p>O exemplo a seguir define o tamanho da fila como 200 MB: </p> <p>QueueSize 200 </p> <p>O exemplo a seguir define o tamanho da fila para 2 GB: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

