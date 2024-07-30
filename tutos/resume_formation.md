# Objectifs

Ce document r�sume les op�rations r�alis�es pendant la formation QGIS. 
Pour chaque op�ration, vous trouverez un lien vers le tuto concern�. 

## Visualiser des donn�es
- Param�trer l'acc�s � la base de donn�es du parc: [premier_parametrage](./premier_parametrage.md)
- Savoir charger et visualiser des couches depuis la base de donn�es
- Param�trer le catalogue de fonds de carte accessibles au format WMS
- Charger les fonds de carte au format WMS

## Organiser et modifier des donn�es
- Bien comprendre le fonctionnement de QGIS
- Savoir cr�er et modifier un vecteur : g�om�trie/attributs
- Transf�rer des donn�es depuis un relev� OruxMaps vers QGIS et vice-versa
- R�aliser des op�rations �l�mentaires d'analyse spatiale (zone tampon, enveloppe convexe, ...)

## Questions du STRB: 
1. Comment importer des coord. GPX du PC au t�l�phone portable�? -> Oruxmaps To PC
 - Pour pouvoir importer des donn�es saisies dans Oruxmaps sur Ordinateur, il faut savoir les exporter au format KML ou GPX, et savoir o� les retrouver. 
Pour cela, aller dans 
 > Propri�t�s(le petit engrenage) > Traces/Routes .

Vous devriez voir le nom d'un dossier de type :
> /storage/..../oruxmaps/tracklogs/

En branchant votre appareil � un ordinateur, vous pourrez donc retrouver vos traces dans ce dossier

2. Comment exporter les coord. GPX du t�l�phone portable au PC�? 
A l'inverse, pour charger des donn�es vecteur depuis QGIS, vers Oruxmaps, il suffit dans un premier temps de convertir la donn�e Qgis au format KML
en faisant clic-droit sur la couche puis "Enregistrer sous". Vous pourrez ensuite changer le format de fichier vers kml.

Ensuite, il suffit de copier votre fichier dans votre appareil. L�, vous pourrez l'importer gr�ce � l'outil "trace/route" qui 
permet de charger un fichier kml ou gpx.

3. Quelle(s) extension(s) pour les coordonn�es GPS (GPX et/ou kml)�? 
Les fichiers KML sont possiblement plus simples � lire sur QGIS. Mais les deux font l'affaire. 
Toutefois, pour toute manipulation ult�rieure ne d�pendant plus d'Oruxmaps, pr�f�rer le format geopackage.

4. La NS est-elle exploitable (compl�te et compr�hensible)�? 
Je veux bien regarder
5. Comment consolider plusieurs fichiers gpx en une seule couche kml -> 
Dans l'onglet "vecteur" dans la barre de menus de QGIS, et dans la boite � outils, se frouve l'outil "Fusion de couches vecteurs". Celui-ci permet de regrouper 
en un seul fichier, plusieurs sources de donn�es vectorielles, m�me dans des formats diff�rents. 

6. Comment positionner un point th�orique de relev� terrain (ex crotte de loup) 
ou dessiner un itin�raire p�destre sur QGIS pour en extraire une trace ou un point gpx/kml ou une carte jpg d�illustration.

7. Comment int�grer sur une couche QGIS un tableau de valeurs et coordonn�es GPS ? 
En ouvrant le gestionnaire de couche (Ctrl+L) aller dans l'onglet "Comma Separated Values", symbolis� par une grosse virgule.La vous pourrez charger un tableau 
de valeurs � condition qu'il ait �t� pr�alablement mis au format csv. 

8. De la possibilit� d�avoir des doubles �crans et des ordinateurs avec des "grosses" capacit�s de r�activit�, pour un logiciel qui demande beaucoup d'espace disque.
J'aimerais bien, moi aussi. 


## Exercice de synth�se (pour les d�brouillards): 
A partir du projet accessible sur la base de donn�es du parc dans le Sch�ma "formation_qgis",
r�aliser une visualisation des occurences de grenouille rousse (cd_ref=351), dans la vall�e de votre choix.

Puis, mettre en �vidence les zones � moins de 500m d'une observation de grenouille rousse, ainsi que 
la zone au sein de laquelle les observations ont �t� faites. 
