# Le projet QGIS

Ce tutorial explique l'utilisation du projet Qgis destin� � organiser la surveillance pendant le passage du Tour de France au col de la Bonette.

## o� trouver le projet

Une fois QGIS ouvert, vous pourrez trouver ce projet de la m�me fa�on que pour les autres projets stock�s sur la base de donn�es du Parc.

- Dans la barre de menu en haut � gauche Cliquer sur 
- "Projet > Ouvrir depuis > PostgreSQL" 

<img src="./img/charger_projet.png" alt= �� width="50%" height="50%"> 


Puis dans le menu d�roulant bien choisir la connexion"Service projets", puis le sch�ma "tourdefrance",
le projet "stationnement_bonnette" devrait s'afficher automatiquement.
<img src="./img/charger_projet_postgresql_schema.png" alt= �� width="50%" height="50%"> 




## Edition

Dans ce projet, seules 3 couches sont � �diter: 

- surveillance
- bivouac_tourdefrance_aremplir
- parking_tourdefrance_aremplir


Les autres couches charg�es dans ce projet le sont uniquement pour servir de points de rep�re. Vous pouvez � tout moment en d�sactiver l'affichage en cliquant sur l'icone en forme d'oeil � c�t� du nom de la couche. 


Pour �diter ces couches, il faut d'abord cliquer sur la couche, puis entrer en mode �dition:
<img src="./img/mode_edition.png" alt= �� width="50%" height="50%"> 

Ensuite, vous pourrez ajouter une entit�:

- Proche de l'icone de crayon, dans la barre d'outils, se trouve l'ic�ne "Ajouter une entit�"

<img src="./img/edition_ajouter_une_entite.png" alt= �� width="50%" height="50%"> 

- Apr�s avoir cliqu� dessus, votre curseur change. Vous pouvez directement ajouter des points qui formeront un polygone
- Un clic gauche vous permet d'ajouter un point, un clic droit termine la saisie d'une entit� sans en rajouter de nouveau, _donc pour faire un rectangle, il faut 4 clics gauches + 1 clic droit_.
- A chaque fin de saisie, une boite de dialogue s'ouvre, permettant d'entrer manuellement les attributs de l'entit�. 

Vous pouvez aussi modifier directement la table attributaire, en faisant clic droit sur la couche puis "Ouvrir la table d'attributs".
L� vous pourrez directement modifier les cellules vous concernant. 

NB: 
Si vous ne trouvez pas une entit� que vous avez pourtant cr��e, il est possible que la table d'attribut d'une couche ne montre pas toutes les entit�s.
En bas � droite de de la fen�tre de la table d'attributs se trouve une petite ic�ne avec un menu d�roulant "Ne montrer que les entit�s visibles sur la carte", 
vous pouvez choisir � la place l'option "Montrer toutes les entit�s".
Cette option n'est pas activ�e par d�faut pour �viter de planter QGIS au cas o� la table d'attributs serait trop grande pour la m�moire de votre machine. 


Pensez � bien entrer votre nom dans "agent", afin qu'il soit possible de vous contacter en cas d'informations contradictoires. 


Il est pr�f�rable de rajouter des commentaires � une entit� plut�t que de la supprimer en cas de d�saccord. 




## Affichage temporel de la couche surveillance

Par d�faut, la couche surveillance est param�tr�e en affichage temporel. Cela signifie que seules les entit�s correspondant � la date d'affichages apparaitront.

Pour afficher le controleur temporel et choisir la date d'affichage, faire un clic droit sur la barre d'outils, et s�lectionner "Panneau - Controleur Temporel"
<img src="./img/panneaux_barreoutils.png" alt= �� width="50%" height="50%"> 


la plage d'animation par d�faut est d�finie entre le 01-07-2024 et le 05-08-2024, chaque jour �tant affich� successivement.






