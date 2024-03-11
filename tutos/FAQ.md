# F.A.Q.

_Vous trouverez dans ce fichier une liste de probl�mes et questions fr�quentes avec des solutions simples._

_En cliquant en haut � droite de cette fen�tre vous avez acc�s � la table des mati�res pour chercher directement la question qui vous int�resse_
<img src="./img/table_des_matieres_git_page.png" alt= �� width="50%" height="50%"> 




<!-- ## Recherche de donn�es -->

<!-- ### Je souhaite importer des courbes de niveau dans mon projet Qgis. --> 


## Dans QGIS

### Qgis plante quand j'essaie d'ouvrir la table d'attribut d'une couche
_Il est probable que la table que vous essayer d'ouvrir est trop grande pour �tre g�r�e par Qgis._
_Solution: Limiter le nombre d'entit�s affich� par d�faut dans la table d'attributs_
Dans la barre d'outils cliquer sur :
> Pr�f�rences > Options...
Dans les onglets de gauche, cliquer sur "Sources de donn�es", puis dans "Comportement des tables" choisir "Montr� les entit�s visibles sur la carte".

Dor�navant, la table d'attribut ne montrera que les entit�s visibles sur l'�tendue du canevas visible, en zoomant vous limiterez le nombre d'entit�s � charger dans la table d'attribut et donc
le risque de plantage de Qgis. 

___________________________________
### La table d'attribut d'une couche ne montre pas toutes les entit�s. 

_Si vous �tes s�r que votre couche contient un grand nombre d'entit�s, mais seules quelques unes, voire aucunes
ne sont visibles dans la table d'attribut._
_Solution: Autoriser une couche � afficher toutes ses entit�s dans la table d'attributs._
En bas � droite de de la fen�tre de la table d'attributs se trouve une petite ic�ne avec un menu d�roulant "Ne montrer que les entit�s visibles sur la carte", 
vous pouvez choisir � la place l'option "Montrer toutes les entit�s" si vous savez que la taille de la table d'attributs n'est pas trop grande pour la m�moire de votre machine. 


_Vous pouvez aussi v�rifier le nombre d'entit�s contenu dans une couche en passant par:_
> clic droit sur la couche > Propri�t�s > Information : D�compte d'entit�s_
_Si ce nombre ne correspond pas au nombre d'entit�s dans la table d'attribut vous pouvez appliquer la solution ci-dessous._ 



#### Explication
Qgis est param�tr� par d�faut pour ne montrer que les entit�s de la table d'attribut qui sont visibles sur la carte. 
Cela �vite de faire planter instantan�ment Qgis en essayant de charger une table d'attribut contenant des milliers d'entit�s,
comme il en existe sur le serveur. 

___________________________________

### "Traiter les couches inutilisables" � l'ouverture d'un projet: certaines couches ne s'affichent pas

Un projet Qgis ne stocke pas les donn�es en dur, mais uniquement les chemins vers celles-ci. 
Par cons�quent, si des donn�es ont �t� supprim�es ou d�plac�es, Qgis ne les "trouve plus", et renvoie 
un message d'erreur  � l'ouverture d'un projet utilisant ces donn�es.

<img src="./img/couche_introuvable_explication.png" alt= �� width="50%" height="50%"> 

- S'il s'agissait de donn�es enregistr�es localement sur la machine:
il suffit de s�lectionner la couche manquante dans cette fen�tre,
puis de cliquer sur "Parcourir" et de montrer � Qgis o� se situent les donn�es. Une fois le projet enregistr�, l'erreur ne devrait plus apparaitre. 


 - S'il s'agissait de donn�es enregistr�es sur le serveur:
le plus simple est de cliquer sur "Conserver les couches inutilisables", puis de cliquer droit sur la couche introuvable et de choisir "R�parer la source des donn�es".

<img src="./img/reparer_la_source_des_donnees.png" alt= �� width="50%" height="50%"> 



Une toute petite fen�tre s'affiche, vous pouvez l'aggrandir. En bas vous trouverez PostgreSQL, puis "Service projets" et les sch�mas et tables contenant les donn�es du parc. 

<img src="./img/reparer_source_donnees_postgreSQL.png" alt= �� width="50%" height="50%"> 



En cas de doute, vous pouvez toujours double cliquer sur la couche manquante, et regarder dans ses propri�t�s sa source afin de retrouver le nom du sch�ma et de la table correspondant. 

<img src="./img/nom_schema_table.png" alt= �� width="50%" height="50%"> 



___________________________________

### Message d'erreur " L'entit� ...  a une g�om�trie non valide" pendant un g�otraitement
M�me si elles ne sont pas formul�es, les g�om�tries dans Qgis r�pondent � des r�gles. Une entit� invalide peut tout de m�me �tre affich�e, mais
toute tentative de traitement, ou de jointure avec une autre couche renverra cette erreur. 

_Solution_

- > "R�parer les g�om�tries": dans la bo�te � outil de Qgis se trouve un outil "R�parer les g�om�tries" qui peut tenter de r�parer les erreurs de g�om�tries.

- > Modification manuelle: Si le message d'erreur donne les identifiants des entit�s aux g�om�tries incorrectes, il est possible de les examiner et 
modifier manuellement pour corriger les �ventuelles erreurs. 
___________________________________

### Impossible de charger un projet depuis la base de donn�es PostgreSQL
Il existe plusieurs cas de figures:

- 1. Vous ne disposez pas d'un acc�s � la base de donn�es

_Solution_

> Si vous �tes bien sur votre poste de travail, et c'est la premi�re fois que vous vous connectez � la base de donn�es contacter le SI.


- 2. Vous pouvez charger des couches depuis la base de donn�es en passant par le gestionnaire de sources de donn�es

_Solution_

> Dans le Gestionnaire des sources de donn�es (Onglet "Couche > Gestionnaire des sources de donn�es" ou CTRL + L), s�lectionner l'onglet "PostgreSQL". Puis s�lectionner la connexion "Service projets". Enfin, cliquer sur "Editer". 
Une nouvelle fen�tre s'affiche en bas de laquelle se trouve la case � cocher "Permettre l'enregistrement et le chargement de projets QGIS dans la base de donn�es. "

___________________________________

### Je ne vois plus le panneau couches/explorateur/...
Le plus probable est qu'un panneau ait �t� d�plac�/ferm� dans une mauvaise manipulation. 
Pour le faire r�appara�tre, il suffit de cliquer sur 
> Vue>Panneaux
Puis de cocher les cases d'int�r�t (g�n�ralement: Couches/Bo�tes � Outils de traitements/Style de couche)


___________________________________

### Je ne vois pas les projets, mais seulement les tables de la base de donn�es

 Faire un clic droit sur Postgis/Service Projets dans l'explorateur, cliquer "Editer la connexion" et cocher "Permettre le chargement et l'enregistrement de projets QGIS" puis "OK".
<img src="./img/editerconnexion_chargerprojets.png" alt= �� width="50%" height="50%"> 
	
___________________________________

### Je souhaite enregistrer une couche avec sa symbologie

Les formats traditionnels d'enregistrement ne permettaient pas d'associer les donn�es et leur mode de repr�sentation, mais 
le format GeoPackage si.
Pour cela, il faut passer par l'outil "Empaquetage de couche" de la boite � outils (accessible � l'aide de CTRL+ALT+T) ou dans 
l'onglet "Traitement" de la barre de menu.


___________________________________

## Oruxmaps

### charger une couche dans Oruxmaps

Pour rendre une couche accessible dans Oruxmaps, il est n�cessaire de produire un fichier au format kml de cette couche, puis de la charger dans le t�l�phone. 

- Dans Qgis, charger la couche d'int�r�t. 
- Cliquer droit sur la couche "Exporter> Sauvergarder les entit�s sous....."
- Choisir le format Keyhole Markup Language (KML)
- Parcourir les dossiers en cliquant sur l'ic�ne suivant, et enregistrer le fichier l� o� il sera facile � retrouver.
<img src="./img/parcourir_dossiers_enregistrer.png" alt= �� width="20%" height="20%"> 
- Brancher le portable ou la tablette � l'ordinateur. 
- Copier le fichier KML dans le dossier 
> ...> oruxmaps > overlay
- Ouvrir Oruxmaps, ouvrir les options de cartes, 
<img src="./img/oruxmaps_optiondecouches.png" alt= �� width="20%" height="20%"> 
- Ouvrir "Options des couches" puis "Charger une couche KML"
Vous devriez trouver le fichier kml, et pouvoir le s�lectionner pour le charger. 


### Copier une couche d'Oruxmaps vers un ordinateur


