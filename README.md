# esphome-solaire
Mon projet solaire

<b>espbms.yaml</b> : Test� sur deux BMS JK-B2A16S (200A)
le RS485 utilis� c�t� JK n'est pas celui utilis� pour la connection en parall�le des BMS (un master, un slave) mais le RS485 � c�t� de la connection CAN (vers l'onduleur)

<b>espdeye.yaml</b> : Test� sur un Deye SUN-8K-SG05-LP1-EU SM2
Sur cet onduleur, ne pas utiliser les fils 1/2 du RJ45 "BMS" (marque RS485/CAN), mais le connecteur RJ45 marqu� modbus

A venir : schema �lectronique et mat�riel utilis�.

Carte utilis�e pour le Deye : https://github.com/slipx06/sunsynk-power-flow-card
