---
description: Identificar os requisitos mínimos e as recomendações para o Data Workbench (anteriormente [!DNL Insight]) componentes do servidor antes de planejar e implementar seu sistema.
title: Requisitos de sistema do servidor
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# Requisitos de sistema do servidor{#server-system-requirements}

{{eol}}

Identifique os requisitos mínimos e recomendações para os componentes do servidor do Data Workbench antes de planejar e implementar seu sistema.

## Requisitos da DPU{#dpu-requirements}

A DPU (Data Processing Unit) do servidor é o principal componente de processamento de dados do Data Workbench. Ele escuta conexões de rede do Data Workbench, lê dados de fonte bruta da unidade de servidor de arquivos (FSU) e usa recursos de computação e armazenamento substanciais.

### Capacidade licenciada {#section-71850e13783443798b3df9eb22cc63dc}

Consulte a Descrição dos serviços na *Adobe [!DNL Data Workbench (Insight)] Contrato de Serviço* para obter informações sobre a capacidade da licença.

>[!NOTE]
>
>Para *Proteção do Ponto Final do Centro de Sistemas da MS* em servidores Windows 2012, esses executáveis precisam ser adicionados ao ***Processos excluídos:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]
>


### Recommendations e requisitos do sistema DPU {#section-ae30555959bf4a309c76d0fd597b5162}

O Adobe fornece recomendações relacionadas a um design de Data Workbench que atende às necessidades de sua empresa. No entanto, as diretrizes a seguir são úteis ao selecionar o sistema operacional (SO) e o hardware, pois a natureza otimizada do software DPU coloca requisitos específicos na plataforma do SO/hardware.

Se um único conjunto de dados for limitado pela capacidade ou velocidade de uma única DPU, você poderá agrupá-los. Por exemplo, suponha que você tenha três cópias licenciadas do software DPU que são usadas em conjunto para executar mais rapidamente um conjunto de dados maior. Como os dados são divididos igualmente entre as máquinas, a capacidade licenciada do conjunto de dados é multiplicada por três. Além disso, a velocidade de processamento por linha torna-se três vezes mais rápida que uma única DPU.

Para obter o melhor desempenho do seu investimento na DPU, o Adobe recomenda os seguintes componentes de alto desempenho descritos na tabela a seguir:

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
   <td colname="col3"> Recomenda-se a geração mais recente de processadores de 4 núcleos da Intel ou AMD. Para um desempenho ideal, 8 núcleos; para uma compensação entre velocidade e custo, recomendam-se quatro núcleos. </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>8 GB </p> </td>
   <td colname="col3"> <p>12 GB </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Armazenamento de dados de trabalho </p> </td>
   <td colname="col2"> <p>1 TB+ de armazenamento temporário lógico total. </p> <p>Acesso de baixa latência ao subsistema do disco </p> </td>
   <td colname="col3"> <p>Para Adobe de armazenamento temporário, recomenda: </p>
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283">
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 a 8) * (750 GB ou superior) HDDs SATA (eixo de 3,5") </li>
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 a 10) * (300 GB ou superior) HDDs SATA (eixo de 2,5") </li>
    </ul> <p>Eles devem ser configurados em uma matriz JBOD. Como alternativa, quando a capacidade bruta do disco excede 2 TB, é possível usar uma matriz de volumes RAID1 de 2 discos. Por exemplo, configure seis discos como um par RAID 1 de 3*(2*750 GB). </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Armazenamento de dados do sistema </p> </td>
   <td colname="col2"> <p>Além disso, o Adobe requer armazenamento de alta disponibilidade de um tamanho modesto (20 GB) para SO, software DPU e outros softwares do sistema. </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Hardware de cluster </p> </td>
   <td colname="col2"> <p>Consulte recomendações. </p> </td>
   <td colname="col3"> <p>Use um conjunto homogêneo de servidores. Em um cluster DPU, o servidor mais lento reduz o desempenho de todo o conjunto de dados. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Cluster do desempenho da rede </td>
   <td colname="col2"> Uma conexão Ethernet Gigabit comutada ou superior. </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

### Subsistemas de disco alternativos {#section-6f984eabe8074759aa9deaf17e3a68b7}

Ao considerar subsistemas de disco alternativos para armazenamento temporário, considere os seguintes fatores e diretrizes:

* A DPU é excepcionalmente exigente de um sistema de disco de alto desempenho, portanto, configurar um subsistema de disco inadequado pode causar gargalos de desempenho.
* O software DPU faz sua própria distribuição de dados orientada ao desempenho em um conjunto de discos JBOD. Não use RAID para aumentar a velocidade.
* A Adobe recomenda que a DPU tenha mais de 400 MB/s de largura de banda sustentada agregada para os discos.
* Os tamanhos médios de leitura são muito altos (2MB+). Por esse motivo, os discos SAS de 15.000 ou 10.000 têm geralmente um desempenho um pouco melhor (ou pior) do que os discos SATA, com um custo e uma redução significativa da capacidade.
* Evite usar uma arquitetura SAN. A experiência mostra que o custo para obter um desempenho de SAN nos níveis necessários é geralmente extremo.
* O subsistema de disco local é usado como espaço de rascunho — nenhum dado é perdido permanentemente de uma falha de HDD, portanto, considere evitar sistemas caros, mais lentos e de alta disponibilidade.

### Considerações de velocidade {#section-01330be232894e08a526d8d82b7c4eb2}

O Adobe não pode fornecer uma garantia ou representação sobre a velocidade em que os dados são processados por uma Data Workbench configurada, pois uma variedade de fatores afetam a velocidade de processamento dos dados, incluindo, entre outros, os seguintes:

* Número de linhas de dados
* Número de dimensões (colunas) de dados
* Número e complexidade de etapas de processamento personalizadas
* Utilização de clustering
* Velocidade do hardware

## Requisitos da unidade do servidor de arquivos{#file-server-unit-requirements}

A FSU (File Serving Unit) do servidor é o principal componente de armazenamento e gerenciamento de dados do Data Workbench. A FSU atua como um servidor de arquivos para dados de fonte bruta na DPU e, quando apropriado, coordena o clustering de DPUs. Cada FSU é licenciada para fornecer dados de origem até cinco (5) DPUs.

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Componentes FSU </th>
   <th colname="col2" class="entry"> Recomendações </th>
   <th colname="col3" class="entry"> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Sistema operacional, CPU, RAM </p> </td>
   <td colname="col2"> <p>Esses requisitos são os mesmos do DPU. No entanto, para o FSU, o Adobe recomenda usar os requisitos mínimos em vez de seguir as recomendações. </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Sistema de disco </p> <p>A FSU requer armazenamento redundante altamente disponível para grandes volumes de dados. O Adobe trabalhará com você para determinar suas necessidades exatas. </p> </td>
   <td colname="col1"> <p>O Adobe recomenda: </p>
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539">
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 ou mais) * (750 GB ou superior) HDDs SATA em uma configuração RAID 5/6. </li>
     <li id="li_3F84F63F9541476987015C27FDE8251B">Conexão SAN de alto desempenho com suporte a largura de banda sustentada de 100 MB/s+. </li>
    </ul> <p>Como a FSU detém os dados de fonte bruta, qualquer perda seria irrecuperável e o Adobe sugere fazer backup desses dados regularmente. </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Desempenho da rede </p> </td>
   <td colname="col2"> <p>O Adobe requer conexões Ethernet comutadas gigabit entre FSUs e DPUs que trabalham juntas. </p> </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

## Requisitos do sensor{#sensor-requirements}

O Sensor de Data Workbench coleta dados de evento da Web, do aplicativo e dos servidores de coleta de dados a serem transmitidos para qualquer servidor. [!DNL Sensor’s] A instrumentação garante uma medição consistente e precisa dos eventos que ocorrem em seu canal de Internet. [!DNL Sensor] O suporta muitas combinações de software de servidor Web e sistema operacional.

### Sistema do sensor Recommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

A tabela a seguir descreve as recomendações do sistema para [!DNL Sensor]:

<table id="table_A132E06D6B8146C1B199B82464EA0898">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Recursos </th>
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
   <td colname="col2"> <p>32 MB de RAM devem estar disponíveis para <span class="wintitle"> Sensor </span> no computador HTTP ou outro servidor que seja o host. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Desempenho da rede </p> </td>
   <td colname="col2"> <p>1 Mbps ou maior conexão de rede com um servidor repetidor ou <span class="keyword"> servidor do Data Workbench </span>. <span class="wintitle"> Sensor </span> O geralmente consome muito menos largura de banda do que um (1) Mbps. Seus consultores de Adobe ajudarão você a estimar a quantidade real de largura de banda que seria necessária de rotina. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Portas de rede e firewalls </p> </td>
   <td colname="col2"> <p> <span class="wintitle"> Sensor </span> conecta-se ao <span class="keyword"> servidor do Data Workbench </span> usando HTTPS (normalmente a porta 443, embora isso seja configurável) ou HTTP (normalmente a porta 80, embora isso seja configurável). </p> <p>A porta apropriada em qualquer firewall que esteja entre um <span class="wintitle"> Sensor </span> e o target <span class="keyword"> servidor do Data Workbench </span> ou o servidor repetidor deve ser aberto somente entre os respectivos <span class="wintitle"> Sensor </span> computador de hospedagem e o <span class="keyword"> servidor do Data Workbench </span> ou servidor repetidor antes de iniciar o <span class="wintitle"> Sensor </span> processo de instalação. <span class="wintitle"> Sensor </span> faz uma conexão HTTPS ou HTTP unidirecional com um <span class="keyword"> servidor do Data Workbench </span> ou servidor repetidor. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Sistemas de gerenciamento de rede </p> </td>
   <td colname="col2"> <p>Os sistemas de gerenciamento de rede existentes devem monitorar a integridade do hardware do computador subjacente (por exemplo, espaço em disco, serviço de rede) e a conectividade de rede, bem como o registro de eventos do Windows ou o syslog do UNIX. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Sincronização de Tempo do Servidor </p> </td>
   <td colname="col2"> <p>Certifique-se de que a hora do sistema do computador seja continuamente sincronizada em todos os computadores que hospedam uma <span class="wintitle"> Sensor </span>. Os aplicativos do servidor Web e os computadores monitorados por <span class="wintitle"> Sensor </span> deve ter horários do sistema sincronizados para que os dados do evento coletados deles sejam precisos. Consulte a documentação do seu sistema operacional para ver as etapas de sincronização contínua dos horários do sistema com o NTP ou outro recurso de sincronização de tempo. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Uso de nome DNS </p> </td>
   <td colname="col2"> <p>Adobe recomenda que <span class="wintitle"> Sensores </span> use um nome DNS (em vez de um endereço IP) para resolver o endereço de rede de um <span class="keyword"> servidor do Data Workbench </span> ou servidor repetidor. Quando uma <span class="wintitle"> Sensor </span> O usa um nome DNS, o DNS do servidor Web host ou o arquivo de hosts local precisa ser configurado para resolver o nome da variável <span class="keyword"> servidor do Data Workbench </span> ou servidor repetidor. </p> </td>
  </tr>
 </tbody>
</table>

### Software de servidor de suporte {#section-d6071706539f49d9a861d87b98e6f382}

A tabela a seguir lista as combinações mais comuns que [!DNL Sensor] suporta:

<table id="table_99EA23BBC1A148B49643F4B5E4341C08">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Software de servidor da Web </th>
   <th colname="col2" class="entry"> Sistema operacional </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Apache Server / IBM HTTP Server 2.2 </p> </td>
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

Para outras combinações de servidor e sistema operacional, consulte o Adobe em relação à disponibilidade. Nem todos os recursos da [!DNL Sensor] estão disponíveis com todas as combinações de servidor da web/aplicativo e sistema operacional. Para obter mais informações sobre [!DNL Sensor] , entre em contato com o Suporte Adobe.

## Requisitos do servidor de relatórios{#report-server-requirements}

O servidor de relatório do Data Workbench é o componente que permite a saída de relatórios agendados. Os relatórios enviados podem estar na forma de imagens .PNG ou planilhas .XLS colocadas em um sistema de arquivos ou como emails. Seus requisitos de hardware são idênticos ao [Cliente do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=pt-BR).

Existem os seguintes requisitos para [!DNL report server]:

* Acesso ao sistema de arquivos para saída de dados (compartilhamento de rede ou unidade local).
* Acesso ao servidor SMTP configurado.
* Microsoft Excel 2003 ou superior instalado em [!DNL report] servidor. Consulte [Considerações para a automação do Office no lado do servidor](https://support.microsoft.com/kb/257757) para obter mais informações.

## Gerenciamento de rede{#network-management}

O Adobe recomenda que os sistemas de gerenciamento de rede existentes monitorem o hardware e a rede em que a plataforma do Data Workbench depende.

Além disso, o Adobe recomenda o monitoramento dos registros de eventos do Windows das FSUs e DPUs, que são gravados em quando ocorre um erro.

>[!NOTE]
>
>Todos os arquivos de log de hospedagem do sistema de armazenamento em rede precisam fornecer pelo menos 10 MB por DPU de largura de banda sustentada.

## Disponibilidade de dados{#data-availability}

É uma prática normal e necessária para uma DPU de servidor processar e reprocessar dados em um conjunto de dados novo ou atualizado.

Isso pode ocorrer devido a alterações na configuração, alterações na fonte de dados, alterações de hardware, configuração inadequada, falha de hardware, falha de software, falha de energia e assim por diante. Quando esse processamento ou reprocessamento ocorre, todos os dados do conjunto de dados e do sistema precisam estar imediatamente disponíveis para os componentes DPU e FSU. O não cumprimento deste requisito pode levar a uma paralisação significativa e desnecessária do sistema.

## Problemas de rede de DPU e FSU{#dpu-and-fsu-network-issues}

Considerações a ter em mente ao trabalhar com redes DPU e FSU.

* Para distribuição de arquivos de log em rede, qualquer arquivo de log de hospedagem do sistema de armazenamento em rede precisa fornecer pelo menos 10 MB por DPU de largura de banda sustentada.
* DPU, FSU e Data Workbench intercomunicam bidirecionalmente via HTTP ou HTTPS na porta 80 ou 443 (por padrão; as portas podem ser configuradas como alternativa).
* Data Workbench [!DNL Sensor(s)] deve ser capaz de se conectar (unidirecional) aos servidores.
* Para permitir que a DPU envie mensagens de alerta via SMTP, ela deve ser capaz de entrar em contato com o servidor SMTP configurado.
* O Adobe recomenda que FSUs e DPUs recebam nomes de rede como FSU01.CLIENT.COM para evitar a reconfiguração se o caso de uma alteração de endereço IP for alterado.
