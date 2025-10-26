<h1>Mon installation</h1>
<H2>Attention</H2>
Je ne suis pas éléctricien, ni professionnel du solaire. Ce projet est réalisé pour mon usage personnel et ne doit pas être reproduit sans l'avis d'un professionnel qualifié. Toute installation électrique comporte des risques d'électrocution, d'incendie, et de dommages matériels ou corporels. Assurez-vous de respecter les normes locales en vigueur et de consulter un professionnel avant toute intervention.
<br/>
<ul>
<li>Puissance PV installée: <b>10.7 kWc</b> répartis sur 2 strings de 6 panneaux à l'EST et 1 string de 6 panneaux au SUD
<li>Capacité batterie: <b>2x16 kWh</b> (2x JK-B2A16S 48V 200A en parallèle), 2x16 batteries LiFePo4 de 314 Wh
<li>Onduleur hybride: <b>Deye SUN-8K-SG05-LP1-EU SM2</b> 8kW en autoconsommation sans injection réseau
</ul>
<br/>
<h2>Principe de fonctionnement</h2>
L'objectif de base est une autoconsommation maximale de la production photovoltaïque, avec un stockage dans les batteries pour une utilisation en soirée et la nuit. Le système doit également permettre de limiter la puissance prélevée sur le réseau.
Pas de micro-onduleurs, tout est centralisé via l'onduleur hybride Deye.
<br>La puissance PV installée est légèrement sur-dimensionnée par rapport à la consommation habituelle de la maison pour améliorer la rentabilité l'hiver.
<br>Le système pouvant fonctionner hors grid en cas de coupure EDF, une mise à la terre du neutre automatique est réalisée (via la sortie ATS du Deye).
<br>La sortie GEN du Deye est configurée en "smart load". Elle s'active selon un paramétrage du Deye (95% batterie + production solaire >=1000W) afin de déclancher automatiquement le Cumulus d'eau chaude. La surproduction permet donc de chauffer l'eau.
<br>En cas de surplus de production, si la batterie est pleine, si le cumulus est off, le Deye baisse automatiquement la puissance PC afin de ne rien injecter sur le réseau ENEDIS.
<H2>Schema unifilaire</H2>
Le schéma a été réalisé avec le logiciel <a href="https://qelectrotech.org/download.php">QElectroTech</a>
<img src="../images/SchemaUnifilaire.JPG" alt="Schema" width="500">
<br/>
La version .qet est disponible dans le dépôt github.