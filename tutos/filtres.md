# Les Filtres dans QGIS

## Explication
Les filtres sont des outils permettant de limiter le nombre d'entit�s charg�e dans QGIS selon des crit�res li�es � la table d'attribut. 
Ils pr�sentent l'avantage d'�tre appliqu�s au niveau du serveur, et donc limitent la charge mise sur votre machine.



## Pas � pas

Dans certain projets, ou au moment de charger certaines couches, vous pouvez voir cette ic�ne: 


<img src="./img/filtre_couche.png" alt= �� width="50%" height="50%"> 

Elle signifique que la couche associ�e est filtre. 

En cliquant dessus, le constructeur d'expression de filtrage apparait. 
Effacer l'expression puis cliquer sur "OK" revient � enlever le filtre.



Vous pouvez aussi modifier le filtre.
L'expression consiste en une condition, il s'agit de v�rifier qu'un ou plusieurs champs de chaque entit� correspond aux crit�res choisis. 

La fa�on la plus simple, et la plus s�re, est de proc�der en cliquant successivement sur les champs et les op�rateurs choisis. 
(Il est possible d'�crire en toute lettre la requ�te, mais c'est s'exposer � plus de risques de faute de frappe ou de syntaxe, la moindre erreur rendant impossible l'ex�cution de la requ�te)

Il faut noter que les noms de champs sont � �crire entre " et les chaines de caract�res entre '

par exemple, si dans une couche de d�partements on ne veut que le d�partement des Alpes-Maritimes il faudrait �crire:

> "nom" = 'Alpes-Maritimes'


Il est possible d'�crire des requ�tes plus ou moins complexes en combinant les conditions.
Par exemple si on veut toutes les observations datant au moins de 2022, ainsi que toutes celles du cd_ref: 4257 (quelle que soit la date d'observation).

> "date_min">2022 OR "cd_ref"=4257






