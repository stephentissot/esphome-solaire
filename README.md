# esphome-solaire
Mon projet solaire

<b>espbms.yaml</b> : Testé sur deux BMS JK-B2A16S (200A)
le RS485 utilisé côté JK n'est pas celui utilisé pour la connection en parallèle des BMS (un master, un slave) mais le RS485 à côté de la connection CAN (vers l'onduleur)

<b>espdeye.yaml</b> : Testé sur un Deye SUN-8K-SG05-LP1-EU SM2
Sur cet onduleur, ne pas utiliser les fils 1/2 du RJ45 "BMS" (marque RS485/CAN), mais le connecteur RJ45 marqué modbus

A venir : schema électronique et matériel utilisé.

Carte utilisée pour le Deye : https://github.com/slipx06/sunsynk-power-flow-card


L'ESP32: j'ai choisi un wt32_ETH01 car il intègre un module Ethernet (LAN8720) et un module WiFi. Dans le fichier espdeye.yaml, c'est l'ethernet qui est utilisé.
<img src="./images/wt32_eth01.jpg" width="300">
	