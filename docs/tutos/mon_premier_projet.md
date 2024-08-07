# Mon Premier projet

_Vous avez re�u des la confirmation du SI que vous �tes autoris� � utiliser la [base de donn�es](./README.md#base-de-donnees 
"Au sens large, une base de donn�e permet de stocker et de manipuler des donn�es par des moyens informatiques.")
du parc ? Voil� comment faire !_


_Ce tutoriel contient les �tapes pour la consultation d'un [projet QGIS](./README.md#projet "Un projet QGIS contient un ensemble de couches,
les informations permettant de les repr�senter, ainsi que l'ensemble des param�tres conditionnant la r�alisation de g�otraitements.") existant, 
ainsi que les possibles op�rations � r�aliser pour en faciliter la visualisation._

> Sc�nario: On vous a demand� d'�tablir pour certaines zones la pr�sence ou l'absence d'une esp�ce v�g�tale donn�e. 

> Pour cela, vous devez consulter un [projet QGIS](./README.md#projet "projet QGIS contient un ensemble de couches,
les informations permettant de les repr�senter, ainsi que l'ensemble des param�tres conditionnant la r�alisation de g�otraitements."), 
entrer vos relev�s terrains en modifiant une couche existante.


## Acc�s � la [base de donn�es](./README.md#base-de-donnees)
_Cette partie reprend le processus d�crit dans [ce tutoriel](./installation_certificats_base_de_donnees.md)._
### 1. V�rifier que vous avez bien acc�s � la base de donn�es par QGIS. 


Pour cela vous pouvez ouvrir QGIS et charger le projet depuis la base de donn�es. 

![](./img/charger_projet.png)

Si les [couches](./README.md#couche "Dans un projet QGIS, une couche est une repr�sentation de donn�es spatialis�e") s'affichent bien, vous pouvez passez au paragraphe 2 "Charger les connexions wms". 
Sinon, continuer au paragraphe suivant.

#### Installation des certificats pour l'acc�s � la base de donn�es _(si n�cessaire)_
_Pour v�rifier si vous avez d�j� param�tr� la connexion � la base de donn�es, ouvrir QGIS puis lancer le gestionnaire_
 _de sources de donn�es (Onglet "Couche>Gestionnaire de source de donn�es" ou Ctrl+L). Cliquer sur l'onglet PostgreSQL._
 _Si le menu d�roulant est vide ou ne contient pas "Service projets", continuer cette partie du tutoriel, sinon passer � la partie suivante_


- T�l�charger le fichier zip qui vous a �t� envoy� par le SI ( qui a le format "pr�nom.nom@mercantour-parcnational.fr.zip" ) 

- Naviguer jusqu'au dossier AppData.

Il se trouve typiquement dans un chemin ressemblant �:
```
C:\Users\ *[nomdelasession]* \AppData\Roaming
```
Le fa�on la plus simple de l'atteindre consiste � appuyer sur  _touche windows + R_, 
puis � entrer la commande "%AppData%" dans l'invit� de commande (la touche windows se trouve entre Ctrl et Alt). 

(Ce r�pertoire est masqu� par d�faut, il est aussi possible de naviguer jusqu'� lui, en autorisant
l'affichage des fichiers cach�s dans les options)

- Cr�er un dossier "postgresql" dans le dossier ..\AppData\Roaming s'il n'existe pas

- Copier dans ce dossier tous les fichiers du zip, y compris - et surtout - le fichier masqu� .pg_service.conf
(les remplacer s'ils existent d�j�)

#### Chargement des param�tres pour acc�der � la base de donn�es

- Ouvrir QGIS

- Ouvrir le gestionnaire de sources de donn�es (Onglet "Couche>Gestionnaire de source de donn�es" ou Ctrl+L) 

- Cliquer sur PostgreSQL dans la barre de gauche

![](./img/gestionnaire_sources_pg.png)


#### _Si vous ne voyez pas "service projets"_
- T�l�charger le fichier suivant, en faisant "clic droit>T�l�charger la cible du lien sous " sur le lien suivant: [service postgresql.xml en cliquant sur ce lien](https://github.com/PnMercantour/donnees/blob/main/tutos/ressources/services%20postgresql.xml).

- Dans le gestionnaire de sources de QGIS, cliquer sur "charger" et retrouver le fichier "service projets.xml" que vous venez de copier


- V�rifier que la connexion "Service projets" est disponible, et se connecter



_La liste des [tables et sch�mas](./README.md#sch�ma "Dans une base de donn�es relationnelle, un sch�ma regroupe diff�rents objets dont des tables, vues et fonctions.") 
accessibles devraient appara�tre._



_NB: Il est aussi possible d'acc�der aux couches de la base de donn�es par l'onglet "Base de donn�es> Gestionnaire BD" de la barre de menus. 
Le Gestionnaire BD et le gestionnaire de sources de donn�es sont � privil�gier pour ajouter des donn�es dans votre projet QGIS. 
Les autres fa�ons d'ajouter des couches peuvent cr�er des probl�mes en appliquant des param�tres d'import par d�faut_

_Cette �tape visait � v�rifier et mettre en place la connexion � la base de donn�es. Maintenant nous allons mettre en place les connexions aux wms qui permettent_
_de charger des fonds de carte._

### 2. Charger les connexions wms

#### Service WMS (fonds de carte) _(si n�cessaire)_

_Pour v�rifier si vous avez d�j� charg� le catalogue de ressources WMS, ouvrir QGIS puis lancer le gestionnaire_
 _de sources de donn�es (Onglet "Couche>Gestionnaire de source de donn�es" ou Ctrl+L). Cliquer sur l'onglet WMS/WMTS._
 _Si le menu d�roulant est vide, continuer cette partie du tutoriel, sinon passer � la partie suivante_

-  T�l�charger le fichier suivant, en faisant "clic droit>T�l�charger la cible du lien sous " sur le lien suivant: [service WMS.xml en cliquant sur ce lien](https://github.com/PnMercantour/donnees/blob/main/tutos/ressources/service%20WMS.xml), puis sur l'ic�ne permettant le t�l�chargement.

D�placer ce fichier dans un dossier o� il sera facile � retrouver.
 
> Exemple: C:\Users\"VotreNom"\Documents\QgisXML
_Remplacer "VotreNom" par le nom d'utilisateur sur votre machine._

Une fois QGIS lanc�, vous pouvez ouvrir le gestionnaire de sources de donn�es (Onglet "Couche>Gestionnaire de source de donn�es" ou Ctrl+L).

![](./img/gestionnaire_sources.png)


- clic droit sur WMS/WMTS dans l'explorateur, s�lectionner "charger des connexions" 

 - S�lectionner le fichier "service WMS.xml" pr�c�demment enregistr�. 
Une fen�tre s'ouvre, clic sur 'Tout S�lectionner' puis 'Importer'




### 3. Charger le projet d'int�r�t

R�cup�rer le projet en cliquant sur "Projet > Ouvrir Depuis > Postgresql" dans la barre de menu

![](./img/charger_projet.png)

<!--
#### Remplacer des couches manquantes

_Un projet QGIS ne contient pas les donn�es, juste les liens y menant. Il est donc normal qu'en ouvrant un projet sans disposer
de toutes les donn�es li�es, des erreurs s'affichent._

Dans ce cas, si les donn�es sont accessibles, il est facile de remplacer le chemin d'acc�s pour r�parer le projet.

Pour ce faire, vous pouvez t�l�charger les donn�es manquantes ici en faisant clic droit - Enregistrer la cible du lien sous:

- [Presence � completer](./ressources/couche_test_a_remplir.gpkg)
- [Observations](./ressources/pts_random_tinee.gpkg)

vous pourrez ensuite
--> 


## Visualisation des donn�es du projet
_Vous avez bien r�ussi � charger le projet "MonPremierProjet" et en voyez le contenu. Nous allons maintenant passer en revue 
les moyens de naviguer dans le projet et observer les donn�es._



1. Afficher/masquer des couches

_Dans QGIS, la position de la plupart des �l�ments sont personnalisables, et il arrive qu'on les modifie par accident. 
Si �a arrive, cas on pourra les retrouver dans l'onglet "Vue", et v�rifier que le panneau ou la barre d'outils concern�e est bien visible._


![](./img/vue_panneaux_barres.png)

A gauche de chaque couche se trouve une petite boite qui peut �tre coch�e ou d�coch�e. 
Cette boite permet d'afficher ou de masquer chaque couche, ou �l�ment de symbologie d'une couche.


2. Les propri�t�s

Double cliquer sur une couche, ou faire "clic droit > Propri�t�s" en affiche les propri�t�s. 

_**Le d�tail de la table attributaire n'est pas visible dans les propri�t�s.**_

L� vous avez acc�s � une s�rie d'onglet donnant des informations sur la couche en question. 
L'onglet "Information" est particuli�rement important pour:
- v�rifier la source des donn�es (si vous travaillez sur des donn�es stock�es sur votre machine, le chemin d�taill� vers le fichier apparaitra, 
si vous travaillez sur le serveur ce seront les param�tres de connexion qui seront visibles).
- v�rifier le type de donn�es ( raster/vecteur, type de g�om�trie) et la projection
- v�rifier le d�compte d'entit� (il s'agit du d�compte apr�s application du filtre)

_NB: Souvent, en rencontrant un probl�me avec une couche, il est important d'aller en v�rifier les propri�t�s pour s'assurer qu'il s'agit bien du type de g�om�trie attendu, que l'on travaille bien sur le bon fichier..._

3. Les filtres

Vous pouvez remarquer un symbole : ![](./img/symbole_filtre.png) 
 � droite de certaines couches:


![](./img/filtres_dans_fenetre.png)



Il signifie que la couche en question est filtr�e. Les filtres sont des outils tr�s puissants, notamment pour limiter la charge sur vos ordinateurs. 
Ils sont appliqu�s au niveau du serveur, et permettent de ne charger que les entit�s d'une couche que vous aurez choisies par une expression. 

Par exemple, en cliquant sur le symbole filtre de "Vallees" ou en faisant clic droit > Filtre sur cette couche vous voyez l'expression suivante :
```sql
"id_type" = 3
```

qui signifie: 
```
"Ne charge que les entit�s pour lesquelles la colonne "id_type" a la valeur 3."
```



_Certaines couches du serveur sont charg�es par d�faut avec des filtres. Il est tout � fait possible de les modifier pour acc�der � d'autres donn�es, 
ou de restreindre encore le filtre propos� le temps de la consultation du projet. Dans ce cas, veillez cependant � ne pas enregistrer vos modifications sur un projet partag�._

_N�anmoins, vous �tes encourag�s � apprendre � les utiliser. Les filtres emploient une syntaxe SQL et un [tutoriel](./lienavenir "Lien � venir") d�di� sera cr��._


4. La table attributaire

Les couches au format [vecteur](./README.md#vecteur "En g�omatique, un vecteur est l'un des deux modes principaux de repr�sentation des donn�es spatiales. 
") contiennent une [table attributaire](./README#table-attributaire "La table attributaire contient l'ensemble des donn�es, spatiales ou non, li�es � une couche vecteur.
"), donnant des informations sur les donn�es qu'elles contiennent. 
Vous pouvez visualiser cette table en cliquant droit sur la couche puis sur "Ouvrir la table d'attributs".

![](./img/ouvrir_latable_attribut.png)


Il existe deux fa�ons de repr�senter la table attributaire. Une vue "Table" et une vue "Formulaire". On peut basculer de l'une � 
l'autre en cliquant sur l'icone correspondante en bas � droite de la fen�tre. 


![](./img/tableattributaire.png)
![](./img/tableattributaire_form.png)

_A gauche, la table attributaire en format table. A droite,en format formulaire. Le mode table permet de visualiser d'un coup d'oeil l'ensemble des entit�s et attributs simultan�ment.
Le mode formulaire permet de visualiser les entit�s une � une, la liste des entit�s apparaissant sur la gauche._


Si votre version de QGIS a bien �t� param�tr�e, en bas � gauche de la table attributaire devrait apparaitre un bouton-d�roulant: "Ne montrer que les entit�s visibles sur la carte".
Cette option peut �tre modifi�e de fa�on � toujours montrer toutes les entit�s, cependant ce mode d'affichage peut faire planter QGIS sur les couches contenant un grand nombre d'entit�s. 

Le mode d'affichage par d�faut est modifiable dans les param�tres de QGIS: 

Pr�f�rences>Options>Sources de donn�es - "Comportement des tables d'attributs"



## Editer une couche

_On se concentrera sur les couches au format [vecteur](./README.md#vecteur ). Toutes les couches pr�sentes dans le projet tuto sont dans ce format. 
Il existe des m�thodes pour modifier les [rasters](./README.md#raster ), mais nous ne les aborderons pas ici._

_L'�dition d'une couche contenue dans la base de donn�es est possible seulement si des droits particuliers vous ont �t� accord�s. La plupart des couches sont uniquement consultables._

### Enregistrer une couche localement


Editer une couche QGIS modifie le fichier de source des donn�es. Il est donc important de rester prudent et de conserver une copie des donn�es d'origine quand c'est possible. 
Pour cela faire clic droit sur la couche
> Exporter > Sauvegarder les entit�s sous
Puis en cliquant sur les "..." naviguer sur l'emplacement de votre machine ou vous souhaitez enregistrer la couche.

Une fois la nouvelle couche enregistr�e, elle devrait apparaitre dans le projet. Vous pourrez v�rifier qu'il s'agit bien d'une copie locale 
en v�rifiant son emplacement dans ses propri�t�s (clic droit> Propri�t�s onglet Information)

### Mode Edition

Pour r�aliser des modifications ou cr�er une nouvelle entit�, il faut d'abord activer le mode Edition pour la couche d'int�r�t. Cela peut se faire de plusieurs fa�ons: 

| ![](./img/mode_edition.png)
Dans la barre d'outils QGIS 

![](./img/modeedition_parcouche.png )   

En passant par un clic droit sur la couche

![](./img/mode_tableattributaire.png)

depuis la fen�tre de la table attributaire

Dans tous les cas, cliquer sur le petit crayon activera le mode �dition pour la couche s�lectionn�e. On pourra alors y apporter des modifications de diff�rentes fa�ons.
Ces modifications ne seront toutefois enregistr�es et effectives qu'� la sortie du mode �dition (en cliquant � nouveau sur le crayon). Si le logiciel crash, ou qu'on ne confirme 
pas les changements � la sortie du mode �dition, les changements seront perdus et les donn�es d'origine seront conserv�es. 

1. Modification de la table attributaire

Une fois en mode Edition, on peut modifier directement la table attributaire � la fa�on d'un tableur. 


2. Cr�ation d'entit�s/Modification de g�om�trie

En mode �dition, on peut aussi �diter directement la g�om�trie d'une entit�, ou en cr�er de nouvelles. 

![](./img/outil_sommet.png)
L'outil sommet permet de modifier la g�om�trie de points/lignes/polygones existants


![](./img/ajouter_entite.png)
Ajouter une entit� permet de cr�er de nouvelles entit�s


La cr�ation d'une nouvelle entit� se fait par une succession de clics gauches, et est finalis�e par un clic droit.
A la finalisation de chaque entit�, une fen�tre s'ouvre proposant d'entrer les attributs connus. 

![](./img/nouvelle_entite.png)

Un "id" ou "fid" correspondant � l'identifiant unique de chaque entit� peut �tre g�n�r� automatiquement. 
Il n'est pas n�cessaire d'entrer les autres attributs pour que la nouvelle enttit� soit sauvegard�e. 


Il est souvent pratique d'afficher des barres d'outils suppl�mentaires (et parfois d'en cacher pour clarifier le menu).
Pour cela, il faut faire clic droit � n'importe quel endroit de la barre d'outils,
ou aller dans Vue > Barres d'outils

Deux outils peuvent �tre particuli�rement pratique pour la num�risation: 

- "Accrochage" qui permet de rendre "magn�tique" le clic, et de superposer parfaitement des points et
- "Num�risation avanc�e" qui permet � des outils de modifications de g�om�tries en mode �dition.

(les autres barres d'outils peuvent contenir des outils pratiques. N'h�sitez pas � les explorer!)


<!--
### Autoriser le chargement des projets

![](./img/editerconnexion_chargerprojets.png) -->

## Changer le mode de repr�sentation d'une couche

Dans couche on appelle le mode de repr�sentation des donn�es d'une couche la "symbologie" (exemple: des aplats de couleurs, cercles noirs pour des points, lignes vertes etc...)
Elle peut �tre modifi�e de fa�on pr�cise pour chaque couche en passant par les propri�t�s d'une couche, � l'onglet symbologie.

Les outils de symbologie dans QGIS sont tr�s puissants, et permettent de repr�senter les informations d'une couche de fa�on synth�tique.
On d�crit ici les modes de repr�sentation les plus commun�ment utilis�s:
- Symbole unique

Mode de repr�sentation le plus simple. On d�finit un symbole qui sera appliqu� de mani�re uniforme � toutes les entit�s, sans prendre en compte leurs attributs

- Cat�goris�

Permet de repr�senter des diff�rences qualitatives entre les entit�s. C'est-�-dire qu'un de leurs attributs permet de les diff�rencier.
> Par exemple: pour des polygones repr�sentant l'occupation des sols, le nom de ces cat�gories (for�t, culture, b�ti etc...).

- Gradu�

Permet de repr�senter des diff�rences quantitatives entre des entit�s.
> Par exemple: pour des points repr�sentant des villes, on peut faire varier leur taille pour repr�senter leur population. 


_Dans ce tutoriel nous n'irons pas plus loin sur la symbologie, mais un autre tutoriel lui sera d�di�e. Nous vous invitons � faire des essais, tout en prenant soin 
de ne pas �craser la symbologie d'un projet partag�._

## Les outils QGIS

_QGIS peut �tre utilis� comme un outil d'analyse particuli�rement puissants._

En plus des fonctionnalit�s d�j� �voqu�es, QGIS contient un grand nombre d'outils qui permettent des analyses plus ou moins complexes. 
La plupart des outils sont disponibles dans les menus "Vecteur" et "Raster" de la barre de menu (mais pas tous!). Dans ces onglets, seule une 
s�lection des outils est affich�e, organis�s par cat�gorie. 

Pour voir l'int�gralit� des outils disponibles, il faut activer le panneau "Boite � outils de traitement", 

soit dans le menu "Vue > Panneaux"

soit en faisant clic droit sur la barre de menus.


Nous ne rentrerons pas ici dans le d�tail de ces outils, mais ce sont eux qui permettent de r�aliser les op�rations les plus complexes de QGIS. 


## Exporter une carte au format image

_Attention, de nombreux projets du Parc contiennent des donn�es qui peuvent �tre sensibles. Avant de publier ou mettre en circulation des exports de donn�es, veiller � s'assurer 
de leur sensibilit� aupr�s du charg� de mission en lien avec elles._

1. Export simple

Il est possible de r�aliser des exports directement depuis le menu de QGIS. A l'onglet Projet > Importer/exporter > Exporter au format Image
Cette fa�on de faire ne permet que d'exporter le contenu du canevas

![](./img/export_format_image.png)

Cet outil fait apparaitre un menu permettant de choisir l'emprise de l'export: 

![](./img/menu_export.png)

On peut ainsi facilement exporter au format image la vue de la carte visible � l'�cran. 


2. Mises en page

QGIS permet de r�aliser des mises en pages de cartes plus complexes. Pour les r�aliser, il faut passer par l'outil de mise en page de QGIS.

![](./img/mise_en_page.png)

Si une mise en page a d�j� �t� cr��e pour le projet en question, vous la trouverez ou bien dans le menu "Projet > Mise en page" ou bien
dans le Gestionnaire de mises en page.

Il est aussi possible de cr�er une nouvelle mise en page. 

Dans tous les cas, � l'ouverture d'une mise en page, une nouvelle fen�tre s'ouvre. 





## Sauvegarder un projet localement et le partager

1. Enregistrer le projet en local au format qgs/qgz

_Un projet sous ces formats sera plus l�ger, mais ne contient pas les donn�es. Seulement le chemin o� trouver les fichiers servant � produire les couches._

Vous pouvez � tout moment "enregistrer sous" un projet qui est enregistr� sur le serveur. 
Cela en cr�e une copie qui ne sera plus accessible � personne d'autre que vous, 
mais vous pourrez ensuite le modifier sans risque de perdre le travail de vos coll�gues.

Un projet enregistr� sous ce format ne contient que les chemins menants aux couches ainsi que la d�finition
de style des couches. Si il d�pendait d'une base de donn�es s�curis�e et qu'il est d�plac� sur un ordinateur 
ne disposant pas de cet acc�s, la couche sera inaccessible et ne s'affichera pas. 

De m�me, si le projet d'origine faisait r�f�rence � des fichiers locaux, alors le projet copi� sur une autre 
machine devra pouvoir retrouver les m�mes fichiers en suivant exactement les m�mes chemins. 

2. Enregistrer le projet au format gpkg

_Sous ce format le projet peut contenir l'ensemble des donn�es, et des informations sur le style permettant de produire les couches. Il est part cons�quent bien plus lourd, mais peut �tre facilement �chang�. La d�marche pour le construire est toutefois plus complexe._

0. Le format gpkg

Le format geopackage (gpkg) est un format relativement r�cent qui a l'avantage de pouvoir contenir plusieurs sources de donn�es spatialis�es vecteur et raster, tout en conservant l'int�grit� de leurs tables attributaires.
Il peut aussi stocker des projets et fichiers de styles. Il r�unit ainsi en un seul fichier ce qui traditionnellement demande l'utilisation de formats peu pratiques (shapefile), et �vite les probl�mes de pr�servation des chemins relatifs des projets au format qgs/qgz. 

Le format gpkg fonctionne sur le mod�le de la base de donn�es, les outils pour l'ouvrir et le modifier sont donc li�s au menus de bases de donn�es dans QGIS. 

1. Sauvegarder un projet au format geopackage

Afin de pouvoir enregistrer le projet et l'ensemble des couches le composant dans un geopackage, il faut d'abord cr�er un geopackage vierge. 
On pourra le faire � l'onglet Couche:
> Couche > Cr�er une couche > Nouvelle couche Geopackage ...


![](./img/creer_gpkg.png)

2. Connexion au gpkg

QGIS n'est pas par d�faut "conscient" du geopackage nouvellement cr��. Il faut d�finir la connexion � ce fichier. 
Pour cela on peut passer par le gestionnaire de base de donn�es (Ctrl + 3) 
> Base de donn�es > Gestionnaire de base de donn�es

et cliquer droit sur "Geopackage>Nouvelle connexion..." dans le menu de gauche.
On pourra alors naviguer jusqu'au fichier geopackage nouvellement cr��. 

3. Enregistrement du projet

Enfin, on pourra simplement aller �:
> Projet > Enregistrer le projet sous.... > Geopackage

Et lui donner un nom (car on peut m�me enregistrer plusieurs projets dans un geopackage).

4. Ouvrir un projet dans un geopackage

Pour ouvrir le projet ainsi enregistr�, il suffit d'aller � 

> Projet > Ouvrir depuis .. > Geopackage

_Si vous recevez un geopackage, il vous faudra possiblement d'abord vous connecter au geopackage en passant le "Gestionnaire de base de donn�es" avant de pouvoir l'ouvrir._


