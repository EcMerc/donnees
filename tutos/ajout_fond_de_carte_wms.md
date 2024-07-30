# Ajouter une couche WMS

## Explications

Les fonds de carte qu'on utilise souvent (ex: SCAN 25, orthophotos) sont le plus souvent utilis�s au format WMS.
Ce format pr�sente des caract�ristiques particuli�res. Il ne s'agit pas de fichiers stock�s dans votre machine, 
mais plut�t d'un moyen d'acc�der � des fichiers qui se trouvent sur un serveur distant, au moyen d'un url et de param�tres de connexion.
A chaque d�placement de la carte dans le projet QGIS, une requ�te est envoy�e au serveur, qui va r�pondre en donnant acc�s aux donn�es dans la r�gion concern�e.
Cette m�thode d'acc�s � la donn�e a l'avantage de ne pas surcharger les machines -  puisque ce sont souvent des donn�es volumineuses -  en chargeant seulement la portion du territoire qui est concern�e par le projet. 

Dans ce tuto, nous allons enregistrer des listes d'adresses de serveurs pour pouvoir y avoir acc�s facilement par la suite. Pour cela, on va utiliser un fichier .xml contenant une liste d'adresse de serveurs, ainsi que les options permettant de s'y connecter. On verra aussi comment ajouter manuellement des WMS issus d'autres sources. 


## Pas � pas

### Ajout du catalogue de WMS

- T�l�charger le catalogue en faisant clic droit "Enregistrer la cible du lien sous" sur le lien suivant:  [service WMS.xml en cliquant sur ce lien](https://raw.githubusercontent.com//PnMercantour/donnees/main/tutos/ressources/service%20WMS.xml)

- D�placer ce fichier dans un dossier o� il sera facile � retrouver.
 
> Exemple: C:\Users\"VotreNom"\Documents\QgisXML
_Remplacer "VotreNom" par le nom d'utilisateur sur votre machine._
- Lancer QGIS
 
- Ouvrir le gestionnaire de sources de donn�es (Onglet "Couche>Gestionnaire de source de donn�es" ou CTRL+L). 
<img src="./img/gestionnaire_sources.png" alt= �� width="50%" height="50%"> 

- Cliquer sur WMS/WMTS dans l'explorateur, s�lectionner "charger des connexions" 

 - S�lectionner le fichier "service WMS.xml" pr�c�demment enregistr�. 
Une fen�tre s'ouvre, clic sur 'Tout S�lectionner' puis 'Importer'

_Cette op�ration a enrichi l'annuaire des couches WMS avec les catalogues IGN les plus souvent utilis�s._ 
_Vous pouvez maintenant ajouter des fonds de carte au format wms en suivant la d�marche d�crite plus bas_

### Ajouter un WMS depuis un nouveau lien
_Vous avez trouv� le lien vers une ressource WMS qui n'est pas dans le catalogue mentionn� plus haut._

- Ouvrir le gestionnaire de sources de donn�es (Onglet "Couche>Gestionnaire de source de donn�es" ou CTRL+L). 
<img src="./img/gestionnaire_sources.png" alt= �� width="50%" height="50%"> 

- Aller dans l'onglet "WMS/WMTS" dans le ruban de gauche.
 
- Cliquer sur "Nouveau"

- Entrer un nom clair permettant d'identifier la ressource ( i.e."IGN - base de donn�es Hydro" )

- Coller le lien de la ressource dans le champs "URL"

- Cliquer sur "OK"



### Charger un fond de carte dans un projet QGIS

- Lancer QGIS
 
- Ouvrir le gestionnaire de sources de donn�es (Onglet "Couche>Gestionnaire de source de donn�es" ou CTRL+L). 

- Cliquer sur l'onglet "WMS" dans la colonne � gauche de la fen�tre.

<img src="./img/gestionnaire_sources.png" alt= �� width="50%" height="50%"> 


## Si vous souhaitez ajouter une ressource se trouvant d�j� dans le catalogue

- Dans le menu d�roulant des couches, choisir la source de donn�es qui vous int�resse (par exemple: "IGN - Licence 7569 - Usages gratuits")
- Cliquer sur connexion
- Les couches li�es � la couche choisie vont appara�tre. Choisir celle qui vous int�resse (ici la carte topographique "SCAN25"):
- Prendre soin de bien remplir les champs "taille de la tuile" avec, par exemple 512 comme valeur.

_Entrer une valeur dans ce champ �vite que QGIS n'essaie de charger des tuiles trop grosses depuis le WMS, ce qui peut ralentir voire compl�tement bloquer l'affichage de votre projet._

<img src="./img/ajout_wms_parametres.png" alt= �� width="90%" height="90%"> 

- Appuyer sur ajouter.
 

