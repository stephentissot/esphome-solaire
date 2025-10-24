# esphome-solaire
Mon projet solaire

<b>espbms.yaml</b> : Test� sur deux BMS JK-B2A16S (200A)
le RS485 utilis� c�t� JK n'est pas celui utilis� pour la connection en parall�le des BMS (un master, un slave) mais le RS485 � c�t� de la connection CAN (vers l'onduleur)

<b>espdeye.yaml</b> : Test� sur un Deye SUN-8K-SG05-LP1-EU SM2
Sur cet onduleur, ne pas utiliser les fils 1/2 du RJ45 "BMS" (marque RS485/CAN), mais le connecteur RJ45 marqu� modbus

Carte Home Assistant utilis�e pour le Deye : https://github.com/slipx06/sunsynk-power-flow-card

<H3>Mat�riel utilis�</H3>


<b>ESP32</b> : j'ai choisi un wt32_ETH01 car il int�gre un module Ethernet (LAN8720) et un module WiFi. Dans le fichier espdeye.yaml, c'est l'ethernet qui est utilis�.
<br/>
<img src="images/wt32_pinout_large.png" alt="WT32_ETH01" width="300">
<br/><br/>
Trouv� sur Amazon pour 27� (les deux) : https://amzn.eu/d/4BWDEwn
<br/>
<b>Adaptateur RS485 -> TTL</b> : Utiliser un module avec contr�le automatique de flux.<br/>
<img src="images/RS485toUart.jpg" alt="Rs485ToUart" width="300">
<br/>
Trouv� sur Amazon pour 7� (les 5) : https://amzn.eu/d/4MC09HF
<br/><br/>
<b>Ecran Oled 0.96" I2C</b> (optionnel) : pour afficher les donn�es localement sur l'ESP32.<br/>
<img src="images/oled.jpg" alt="OLED" width="300">
<br/>Trouv� sur Amazon pour 17� (les 6) : https://amzn.eu/d/6elGV45

<br/>
<h3>Sch�ma de c�blage</h3>


<img src="images/schema.jpg" alt="Schema" width="600">

<H4>ESP Deye</H4>

Sur ce schema, le RS485 du module ESPDeye est connect� � l'onduleur Deye SUN-8K-SG05-LP1-EU SM2 via le connecteur RJ45 marqu� RS485/BMS utilis� pour relier l'onduleur au BMS. Mais sur le Deye SUN-8K-SG05-LP1-EU SM2, cela ne marche pas, il faut utiliser le connecteur RJ45 marqu� modbus (fils 1/2). 
Donc pour ce mod�le, 2 RJ45 sortent du Deye (BMS et Modbus) et donc l'ESPDeye n'a pas � "splitter" le signal tel que sur le schema (1-2-3 vers RS485 ESPDeye, 4-5-6-7-8 vers BMS).
<br/>
<br/>
Dans mon cas, j'ai connect� la masse (3) du Deye � la masse (GND) du convertisseur RS485/TTL pour �viter des probl�mes de communication. Mais j'ai lu que dans certain cas, il �tait n�cessaire de ne pas la connecter.
<br/>
<img src="images/deye.jpg" alt="Schema" width="300">
<br/>
<i>SUN-8K_SG05LP1-EU-SM2</i>
<br/>
<br/>
<ul>
<li>BMS 485/CAN : connexion vers port CAN du BMS master</li>
<li>MODBUS : connexion ESPDeye</li>
</ul>

<H4>ESP BMS</H4>
Le plus simple pour remonter les informations des BMS dans Home Assistant est d'utiliser BatMan et une connexion bluetooth. Dans mon cas, le mini PC executant HA se situe dans une armoire � c�t� des batteries, et dispose d'une antenne bluetooth puissante.
L'installation est alors simple, sans aucun montage �lectronique.<br/>
Mais cette configuration impose que les BMS soient connect�s en bluetooth � HA en permanence, et donc qu'une connexion via l'application JK du t�l�phone n'est plus possible (sauf � arr�ter Batmon).
<br/>
J'ai donc d�cid� de connecter les BMS via RS485 � un ESP32 (wt32_ETH01) qui remonte les informations vers HA via ethernet.
Ayant 2 batteries, donc 2 BMS, un master et un slave, j'ai essay� de n'utiliser qu'un seule module RS485/TTL connect� sur un connecteur modbus "parall�le" (qui permet au BMS master de dialoguer avec le slave).
<br/>Mais cela n'a pas fonctionn�, il faudrait en effet que ESPBMS soit master pour r�cuperer les donn�es des 2 BMS, or il ne peut y avoir qu'un seul master. J'ai vu quelques projets essayant de "sniffer" le trafic pour r�cup�rer les donn�es des 2 BMS, mais c'�tait un peu bricolage (et �a n'a pas fonctionn�).
<br/>
J'ai donc utilis� 2 modules RS485/TTL, un pour chaque BMS.
<br/><br/>

<img src="images/jkbms.jpg" alt="Schema" width="300">
<br/>
<i>JK-B2A16S</i>
<br/>
<br/>
<ul>
<li>RS485-1 : connexion ESPBMS</li>
<li>CAN : connexion Deye</li>
<li>RS485-2 et RS4852 : bus modbus pour communication entre BMS master/slave
</ul>

:
