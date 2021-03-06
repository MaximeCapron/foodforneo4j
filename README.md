# foodforneo4j

## Description 

Ce dossier github contient tout le nécessaire à un projet de création de base de données par graphe. On s'intéresse ici à des données (fictives) représentant des relations entre stakeholders (Orange Business Services et ses clients). Afin d'optimiser les chances de gagner un contrat pour OBS, on utilise les Graph Databases permet de montrer les relations (directes et indirectes) entre les acteurs. Toutes les personnes clefs sont identifiées, engagées au bon niveau, et qualifiées (avocat, neutre, adversaire).

* Le fichier "interactions.ipynb" permet de générer une base de données d'exemple "Stakeholders' map", d'ajouter ou de supprimer des noeuds ou des relations, puis d'investiguer dans la base de données pour créer des rapports sur des dossiers en particulier.


* "Fichiers_csv" contient les fichiers csv nécessaires à la bonne marche du notebook ci-dessus.

* "Neovis_graph" est un dossier qui rassemble du code HTML pour créer des visualisations de graphes. Il y a deux fichiers à l'intérieur : un exemple sur des données n'ayant rien à voir et une tentative de réplication pour les stakeholders' maps (pas terminée).

* Dans "divers", on trouve une capture d'écran de la visualisation neo4j (dont le but est de la répliquer à l'aide de neovis.js), et le jupyter notebook ayant servi à générer les noms de personnes se trouvant dans les fichiers csv. Se trouve aussi "interactions_from_scratch.ipynb" contient la petite présentation faite, en créant un graphe plus petit à partir de rien.



## Organisation des fichiers pour permettre la bonne création de la BDD graphe fictive

On a besoin dans ce github d'un fichier "Humain" et d'un fichier "Entreprises".
    
* Le fichier "Humains" doit débuter par un index, puis on peut introduire les colonnes de son choix.
* Le fichier "Entreprises" doit débuter par un index, puis on peut introduire les colonnes de son choix.

On peut ajouter des relations entre les noeuds, que l'on numérotera ("Relations1", "Relations2", etc.).

* Les fichiers "Relations" doivent commencer par les pointeurs vers les index des deux bouts de la relations, puis on peut introduire les colonnes de son choix. La dernière colonne "nom" comporte le nom de la relation (il doit être similaire sur toute la colonne).

Pour mieux comprendre, référez-vous directement aux exemples qui se trouvent dans le dossier "fichiers-csv".


## Création d'une instance de neo4j (sandbox)

Rejoindre ce site : https://sandbox.neo4j.com/?&program_name=PPC%20GG%2020%20Neo4j%20Sandbox

Eventuellement, s'identifier. Créer ensuite un nouveau projet.

Une fois le projet créé, vous pouvez commencer.
En extraire les détails de connexion (en cliquant sur la petite flèche tout à droite du projet que vous venez de créer) : l'identifiant est en principe "neo4j", vous aurez donc besoin du mot de passe et de l'URL Bolt.

Dans le Jupyter Notebook, rentrer ces trois informations. Vous êtes prêt !

### Remarque

Attention cependant ;) Vous n'avez plus beaucoup de temps ! Une sandbox ne dure originellement que 3 jours, mais peut être étendue une semaine de plus.

Deux options s'offrent à vous pour une organisation plus pérenne :

- Passer à un système cloud pérenne (Neo4j Aura), payant.
- Tout mettre en local dans votre ordinateur (Neo4j Desktop).



