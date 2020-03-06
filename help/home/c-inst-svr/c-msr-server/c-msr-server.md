---
description: Identifique os requisitos mínimos e recomendações para os componentes do servidor da Análise de big data (anteriormente [!DNL Insight]) antes de planejar e implementar seu sistema.
title: Requisitos do sistema do servidor
uuid: c4487c76-03b9-4755-893b-555d451b1e69
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Requisitos do sistema do servidor{#server-system-requirements}

Identifique os requisitos mínimos e recomendações para os componentes do servidor da Análise de big data antes de planejar e implementar seu sistema.

## Requisitos de DPU{#dpu-requirements}

A DPU (Unidade de processamento de dados) do servidor é o principal componente de processamento de dados da Análise de big data. Ele escuta as conexões de rede do Análise de big data, lê os dados brutos de origem da Unidade de Servidor de Arquivos (FSU) e usa recursos tecnológicos e de armazenamento substanciais.

### Capacidade licenciada {#section-71850e13783443798b3df9eb22cc63dc}

Consulte a Descrição de serviços no *Adobe[!DNL Data Workbench (Insight)]Service Agreement* para obter informações sobre a capacidade da licença.

>[!NOTE]
>
>Para o *MS System Center Endpoint Protection* nos servidores Windows 2012, esses executáveis precisam ser adicionados aos processos ***excluídos:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>



### Recomendações e requisitos do sistema DPU {#section-ae30555959bf4a309c76d0fd597b5162}

A Adobe fornece recomendações relacionadas ao design da Análise de big data que atende às suas necessidades comerciais. No entanto, as diretrizes a seguir são úteis ao selecionar o sistema operacional (SO) e o hardware, pois a natureza otimizada do software da DPU coloca requisitos específicos na plataforma do SO/hardware.

Se um único conjunto de dados for limitado pela capacidade ou velocidade de uma única DPU, é possível agrupá-los. Por exemplo, suponha que você tenha três cópias licenciadas do software DPU que são usadas juntas para executar mais rapidamente um conjunto de dados maior. Como os dados são divididos uniformemente entre as máquinas, a capacidade licenciada do conjunto de dados é multiplicada por três. Além disso, a velocidade de processamento por linha se torna três vezes mais rápida do que uma única DPU.

Para obter o melhor desempenho do seu investimento em DPU, a Adobe recomenda os seguintes componentes de alto desempenho descritos na tabela a seguir:

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Obrigatório </th> 
   <th colname="col3" class="entry"> Recomendado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sistema operacional </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CPU </p> </td> 
   <td colname="col2"> <p>Consulte recomendações. </p> </td> 
   <td colname="col3"> São recomendados os processadores de mais de 4 núcleos da última geração da Intel ou AMD. Para um desempenho ótimo, 8 núcleos; para uma compensação entre velocidade e custo, são recomendados quatro núcleos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Armazenamento de dados de trabalho </p> </td> 
   <td colname="col2"> <p>Mais de 1 TB de armazenamento temporário lógico total. </p> <p>Acesso de baixa latência ao subsistema do disco </p> </td> 
   <td colname="col3"> <p>Para armazenamento temporário, a Adobe recomenda: </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 a 8) * (750 GB ou mais) HDDs SATA (eixo de 3,5") </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 a 10) * (300 GB ou superior) HDDs SATA (eixo de 2,5 pol) </li> 
    </ul> <p>Eles devem ser configurados em uma matriz JBOD. Como alternativa, quando a capacidade bruta do disco exceder 2 TB, é possível usar uma matriz de volumes RAID1 de 2 discos. Por exemplo, configure seis discos como um par RAID 1 de 3*(2*750 GB). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Armazenamento de dados do sistema </p> </td> 
   <td colname="col2"> <p>Além disso, a Adobe exige um armazenamento de alta disponibilidade de tamanho modesto (20 GB) para o SO, software DPU e outros softwares do sistema. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hardware de cluster </p> </td> 
   <td colname="col2"> <p>Consulte recomendações. </p> </td> 
   <td colname="col3"> <p>Use um conjunto homogêneo de servidores. Em um cluster DPU, o servidor mais lento reduz o desempenho de todo o conjunto de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Agrupamento de desempenho de rede </td> 
   <td colname="col2"> Uma conexão Ethernet gigabit comutada ou superior. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### Subsistemas de disco alternativos {#section-6f984eabe8074759aa9deaf17e3a68b7}

Ao considerar subsistemas de disco alternativos para armazenamento temporário, considere os seguintes fatores e diretrizes:

* A DPU é extremamente exigente de um sistema de disco de alto desempenho, portanto, a configuração de um subsistema de disco inadequado pode causar gargalos no desempenho.
* O software DPU faz sua própria divisão de dados orientada ao desempenho em um conjunto de discos JBOD. Não use RAID para aumentar a velocidade.
* A Adobe recomenda que a DPU tenha mais de 400 MB/s de largura de banda sustentada agregada para os discos.
* Os tamanhos médios de leitura são muito altos (2MB+). Por essa razão, os discos SAS de 15.000 ou 10.000 alto desempenho geralmente são um pouco melhores (ou piores) do que os discos SATA, com um custo significativo e uma penalidade de capacidade.
* Evite usar uma arquitetura SAN. A experiência mostra que o custo para fazer uma SAN funcionar nos níveis necessários é geralmente extremo.
* O subsistema de disco local é usado como espaço de trabalho — nenhum dado é perdido permanentemente devido a uma falha de disco rígido, portanto, considere evitar sistemas caros, mais lentos e de alta disponibilidade.

### Considerações sobre velocidade {#section-01330be232894e08a526d8d82b7c4eb2}

A Adobe não pode fornecer uma garantia ou representação sobre a velocidade em que os dados são processados por uma análise de big data configurada, pois vários fatores afetam a velocidade de processamento dos dados, incluindo, entre outros, os seguintes:

* Número de linhas de dados
* Número de dimensões (colunas) dos dados
* Número e complexidade de etapas de processamento personalizadas
* Utilização de agrupamentos
* Velocidade do hardware

## Requisitos da unidade do servidor de arquivos{#file-server-unit-requirements}

A FSU (File Serving Unit) do servidor é o principal componente de gerenciamento e armazenamento de dados da Análise de big data. O FSU atua como um servidor de arquivos para dados de fonte bruta para a DPU e, quando apropriado, coordena o agrupamento de DPUs. Cada FSU é licenciado para fornecer dados de origem para até cinco (5) DPUs.

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componentes FSU </th> 
   <th colname="col2" class="entry"> Recomendações   </th> 
   <th colname="col3" class="entry"> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sistema operacional, CPU, RAM </p> </td> 
   <td colname="col2"> <p>Esses requisitos são os mesmos da DPU. No entanto, para o FSU, a Adobe recomenda usar os requisitos mínimos em vez de seguir as recomendações. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sistema de disco </p> <p>O FSU requer armazenamento redundante e altamente disponível para grandes volumes de dados. A Adobe trabalhará com você para determinar seus requisitos exatos. </p> </td> 
   <td colname="col1"> <p>A Adobe recomenda: </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 ou mais) * (750 GB ou mais) HDDs SATA em uma configuração RAID 5/6. </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">Conexão SAN de alto desempenho com suporte a largura de banda sustentada de 100 MB/s+. </li> 
    </ul> <p>Como o FSU retém os dados de fonte bruta, qualquer perda seria irrecuperável, e a Adobe sugere fazer backup desses dados regularmente. </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desempenho da rede </p> </td> 
   <td colname="col2"> <p>A Adobe exige conexões Ethernet gigabit comutadas entre FSUs e DPUs trabalhando juntas. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## Requisitos do sensor{#sensor-requirements}

O Sensor da Análise de big data coleta dados de eventos da Web, do aplicativo e dos servidores de coleta de dados a serem transmitidos para qualquer servidor. [!DNL Sensor’s] a instrumentação garante uma medição consistentemente precisa dos eventos que ocorrem no seu canal de Internet. [!DNL Sensor] suporta muitas combinações de software de servidor Web e sistema operacional.

### Recomendações do sistema do sensor {#section-0a981c3a47b644c1a1a56974ba033b9c}

A tabela a seguir descreve as recomendações do sistema para [!DNL Sensor]:

<table id="table_A132E06D6B8146C1B199B82464EA0898"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recursos  </th> 
   <th colname="col2" class="entry"> Recomendado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Armazenamento em disco </p> </td> 
   <td colname="col2"> <p>Mínimo de 512 MB. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 MB de RAM devem estar disponíveis para o <span class="wintitle"> Sensor </span> no computador HTTP ou em outro servidor que seja seu host. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desempenho da rede </p> </td> 
   <td colname="col2"> <p>1 Mbps ou mais conexão de rede com um servidor repetidor ou com um servidor <span class="keyword"> análise de big data </span>. <span class="wintitle"> O sensor </span> geralmente consome muito menos largura de banda do que um (1) Mbps. Seus consultores da Adobe o ajudarão a estimar a quantidade real de largura de banda que seria necessária de acordo com a rotina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Portas de rede e firewalls </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> O sensor </span> se conecta ao servidor de análise de big data <span class="keyword"> </span> usando HTTPS (normalmente a porta 443, embora seja configurável) ou HTTP (normalmente a porta 80, embora seja configurável). </p> <p>A porta apropriada em qualquer firewall que resida entre um <span class="wintitle"> Sensor </span> e o servidor de análise de big data de destino <span class="keyword"> ou servidor repetidor deve ser aberta apenas entre o respectivo computador </span> Sensor <span class="wintitle"> que hospeda e o servidor de análise de big data </span> ou servidor repetidor antes de iniciar o processo de <span class="keyword"> instalação do </span> <span class="wintitle"> </span> Sensor. <span class="wintitle"> O sensor </span> faz uma conexão HTTPS ou HTTP unidirecional com um servidor de análise de big data <span class="keyword"> </span> ou servidor repetidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sistemas de gerenciamento de rede </p> </td> 
   <td colname="col2"> <p>Os sistemas de gerenciamento de rede existentes devem monitorar a integridade do hardware do computador subjacente (por exemplo, espaço em disco, serviço de rede) e a conectividade de rede, bem como o log de eventos do Windows ou o syslog do UNIX. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sincronização de tempo do servidor </p> </td> 
   <td colname="col2"> <p>Verifique se a hora do sistema do computador está sincronizada continuamente em todos os computadores que hospedam um <span class="wintitle"> sensor </span>. Os aplicativos e computadores do servidor Web que são monitorados pelo <span class="wintitle"> Sensor </span> devem ter horários sincronizados do sistema para que os dados de eventos coletados deles sejam precisos. Consulte a documentação do seu sistema operacional para obter as etapas para sincronizar os tempos do sistema de forma contínua com o NTP ou outro recurso de sincronização de tempo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uso do nome DNS </p> </td> 
   <td colname="col2"> <p>A Adobe recomenda que <span class="wintitle"> os Sensores </span> usem um nome DNS (em vez de um endereço IP) para resolver o endereço de rede de um servidor de análise de big data ou servidor repetidor <span class="keyword"> </span> . Quando um <span class="wintitle"> Sensor </span> usa um nome DNS, o DNS do servidor da Web host ou o arquivo de hosts local precisa ser configurado para resolver o nome do servidor de análise de big data <span class="keyword"> </span> ou do servidor repetidor. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Software de servidor de suporte {#section-d6071706539f49d9a861d87b98e6f382}

A tabela a seguir lista as combinações mais comuns que [!DNL Sensor] suportam:

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Software de servidor Web </th> 
   <th colname="col2" class="entry"> Sistema operacional </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Apache Server/IBM HTTP Server 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 ou posterior; RedHat Enterprise Linux 6.x ou posterior; Sun Solaris 8.x ou posterior; IBM AIX 5.1x ou posterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apache Server 2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x ou posterior </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 ou posterior </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores de aplicativos Java (Tomcat, JBoss, iPlanet, Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 ou posterior; RedHat Enterprise Linux 6.x ou posterior; Sun Solaris 8.x ou posterior; IBM AIX 5.1x ou posterior. </p> </td> 
  </tr> 
 </tbody> 
</table>

Para obter outras combinações de servidor e sistema operacional, consulte a Adobe em relação à disponibilidade. Nem todos os recursos do [!DNL Sensor] estão disponíveis com todas as combinações de servidor da Web/aplicativo e sistema operacional. Para obter mais informações sobre [!DNL Sensor] versões específicas, entre em contato com o Suporte da Adobe.

## Requisitos do Servidor de Relatório{#report-server-requirements}

O servidor de relatório da análise de big data é o componente que permite a saída de relatórios programados. Os relatórios que são enviados podem estar na forma de imagens .PNG ou planilhas .XLS colocadas em um sistema de arquivos, ou como emails. Seus requisitos de hardware são idênticos ao Cliente [](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html)da Análise de big data.

Existem os seguintes requisitos para [!DNL report server]:

* Acesso ao sistema de arquivos para saída de dados (compartilhamento de rede ou unidade local).
* Acesso ao servidor SMTP configurado.
* Microsoft Excel 2003 ou superior instalado no [!DNL report] servidor. Consulte [Considerações para automação do Office](http://support.microsoft.com/kb/257757) no servidor para obter mais informações.

## Gerenciamento de rede{#network-management}

A Adobe recomenda que os sistemas de gerenciamento de rede existentes monitorem o hardware e a rede em que a plataforma Análise de big data depende.

Além disso, a Adobe recomenda monitorar os registros de eventos do Windows dos FSUs e DPUs, que são gravados quando ocorre um erro.

>[!NOTE]
>
>Todos os arquivos de log de hospedagem do sistema de armazenamento em rede precisam fornecer pelo menos 10 MB por DPU de largura de banda sustentada.

## Disponibilidade de dados{#data-availability}

É uma prática normal e obrigatória para uma DPU de servidor processar e reprocessar dados em um conjunto de dados novo ou atualizado.

Isso pode ocorrer devido a alterações na configuração, alterações na fonte de dados, alterações de hardware, configuração inadequada, falha de hardware, falha de software, falha de energia e assim por diante. Quando esse processamento ou reprocessamento ocorrer, todos os dados do conjunto de dados e do sistema deverão estar imediatamente disponíveis para os componentes DPU e FSU. O não cumprimento deste requisito pode levar a um sistema inativo significativo e desnecessário.

## Problemas de rede DPU e FSU{#dpu-and-fsu-network-issues}

Considerações a ter em mente ao trabalhar com redes DPU e FSU.

* Para a distribuição de arquivos de log em rede, qualquer sistema de armazenamento em rede que hospedar arquivos de log precisa fornecer pelo menos 10 MB por DPU de largura de banda sustentada.
* A DPU, o FSU e a Análise de big data comunicam bidirecionalmente via HTTP ou HTTPS na porta 80 ou 443 (por padrão; as portas podem ser configuradas como alternativa).
* A análise de big data [!DNL Sensor(s)] deve ser capaz de se conectar (unidirecional) aos servidores.
* Para permitir que a DPU envie mensagens de alerta via SMTP, é necessário que ela possa entrar em contato com o servidor SMTP configurado.
* A Adobe recomenda que os FSUs e DPUs recebam nomes de rede, como FSU01.CLIENT.COM, para evitar a reconfiguração se ocorrer uma alteração no endereço IP.