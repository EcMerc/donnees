
Dans le cadre de la bascule des ressources de l'IGN, le SCAN 25 est temporairement accessible selon la d�marche d�crite ci dessous.

<!--  https://geoservices.ign.fr/documentation/services/utilisation-sig/tutoriel-qgis/gpf-wms-wmts-donneesnonlibres --> 

Cette solution est temporaire, et cessera de fonctionner d�s la fin de la bascule des ressources de l'ign sur la g�oplateforme. Quand cela arrivera, le nouveau mode d'acc�s au SAN25 vous sera communiqu�.


# Ajouter le SCAN 25 au catalogue WMS


## Pas � pas

### Ajout de la ressource catalogue de WMS

 
- Ouvrir le gestionnaire de sources de donn�es (Onglet "Couche>Gestionnaire de source de donn�es" ou CTRL+L). 
<img src="./img/gestionnaire_sources.png" alt= �� width="50%" height="50%"> 

- Cliquer sur WMS/WMTS dans l'explorateur, s�lectionner "Nouveau" 

- Dans nom entrer "Scan 25"
- Dans URL copier le lien suivant
> https://data.geopf.fr/private/wmts?SERVICE=WMTS&VERSION=1.0.0&REQUEST=GetCapabilities&apikey=ign_scan_ws

<!--
- Il faut ensuite cliquer sur la petite croix verte dans l'encadr� "Athentification"

<img src="./img/croix_verte_nouveau_wms.png" alt= �� width="50%" height="50%"> 

- Puis entrer les donn�es comme dans l'image ci dessous apr�s avoir cliqu� � nouveau sur la petite croix verte: 
	- Nom: Scan25
	- cl� d'en-t�te: apikey
	- Valeur d'en-t�te: ign_scan_ws
<img src="./img/detail_params_scan25.png" alt= �� width="50%" height="50%"> 
--> 
- Cocher la case "Ignorer les URI GetMap/GetTile/GetLegendGraphic signal�s dans les capacit�s"

-  Puis cliquer sur OK. 


- Un nouvel onglet s'ouvre automatiquement vous permettant de choisir entre plusieurs versions du scan 25, choisir celui projet� en Lambert-93 (EPSG:2154)

<img src="./img/selection_scan25_wms.png" alt= �� width="50%" height="50%"> 

- Cliquer sur "Ajouter" en bas � droite pour ajouter cette couche WMS au projet actuel.

- Cette couche est maintenant disponible pour �tre charg�e dans tous vos projets.




### Charger un fond de carte dans un projet QGIS

- Lancer QGIS
 
- Ouvrir le gestionnaire de sources de donn�es (Onglet "Couche>Gestionnaire de source de donn�es" ou CTRL+L). 

- Cliquer sur l'onglet "WMS" dans la colonne � gauche de la fen�tre.

<img src="./img/gestionnaire_sources.png" alt= �� width="50%" height="50%"> 

- Cliquer sur la ressource d'int�r�t dans le menu d�roulant (ici "SCAN 25") puis sur "Charger"
- Cliquer sur la couche qui s'affiche dans le menu central
- Entrer des tailles de tuile (recommand�: "256" et "256".) Le syst�me de coordonn�es n'est pas toujours modifiable.

<img src="./img/ajout_wms_parametres.png" alt= �� width="50%" height="50%"> 

- puis sur "Ajouter"


