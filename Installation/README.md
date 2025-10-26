<h1>Mon installation</h1>
<H2>Attention</H2>
Je ne suis pas �l�ctricien, ni professionnel du solaire. Ce projet est r�alis� pour mon usage personnel et ne doit pas �tre reproduit sans l'avis d'un professionnel qualifi�. Toute installation �lectrique comporte des risques d'�lectrocution, d'incendie, et de dommages mat�riels ou corporels. Assurez-vous de respecter les normes locales en vigueur et de consulter un professionnel avant toute intervention.
<br/>
<ul>
<li>Puissance PV install�e: <b>10.7 kWc</b> r�partis sur 2 strings de 6 panneaux � l'EST et 1 string de 6 panneaux au SUD
<li>Capacit� batterie: <b>2x16 kWh</b> (2x JK-B2A16S 48V 200A en parall�le), 2x16 batteries LiFePo4 de 314 Wh
<li>Onduleur hybride: <b>Deye SUN-8K-SG05-LP1-EU SM2</b> 8kW en autoconsommation sans injection r�seau
</ul>
<br/>
<h2>Principe de fonctionnement</h2>
L'objectif de base est une autoconsommation maximale de la production photovolta�que, avec un stockage dans les batteries pour une utilisation en soir�e et la nuit. Le syst�me doit �galement permettre de limiter la puissance pr�lev�e sur le r�seau.
Pas de micro-onduleurs, tout est centralis� via l'onduleur hybride Deye.
<br>La puissance PV install�e est l�g�rement sur-dimensionn�e par rapport � la consommation habituelle de la maison pour am�liorer la rentabilit� l'hiver.
<br>Le syst�me pouvant fonctionner hors grid en cas de coupure EDF, une mise � la terre du neutre automatique est r�alis�e (via la sortie ATS du Deye).
<br>La sortie GEN du Deye est configur�e en "smart load". Elle s'active selon un param�trage du Deye (95% batterie + production solaire >=1000W) afin de d�clancher automatiquement le Cumulus d'eau chaude. La surproduction permet donc de chauffer l'eau.
<br>En cas de surplus de production, si la batterie est pleine, si le cumulus est off, le Deye baisse automatiquement la puissance PC afin de ne rien injecter sur le r�seau ENEDIS.
<H2>Schema unifilaire</H2>
Le sch�ma a �t� r�alis� avec le logiciel <a href="https://qelectrotech.org/download.php">QElectroTech</a>
<img src="../images/SchemaUnifilaire.JPG" alt="Schema" width="500">
<br/>
La version .qet est disponible dans le d�p�t github.