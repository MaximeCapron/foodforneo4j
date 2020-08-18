# foodforneo4j

## Commandes – Création de la BDD


Pour reconstituer la BDD, copier-coller tout ce qui suit dans une fenêtre Neo4j.


"""
// Supprimer tout ce qui préexiste pour avoir une feuille propre

MATCH (n)
DETACH DELETE n ;


// Importer les noeuds 

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/MaximeCapron/foodforneo4j/master/Humains.csv' AS row FIELDTERMINATOR ';'
MERGE (p:Person {id: row.index})
ON CREATE SET p.nom = row.Nom, p.position_A = row.Position_A, p.position_B = row.Position_B, p.position_C = row.Position_C, p.position_D = row.Position_D, p.position_E = row.Position_E;


LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/MaximeCapron/foodforneo4j/master/Entreprises.csv' AS row FIELDTERMINATOR ';'
MERGE (c:Company {id: row.index})
ON CREATE SET c.titre = row.Titre;


// Importer les relations

LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/MaximeCapron/foodforneo4j/master/Relations1.csv' AS rel FIELDTERMINATOR ';'
MATCH (p1 {id: rel.index})
MATCH (p2 {id: rel.index_relation})
MERGE (p1)-[r:CONNAISSANCE]->(p2)
ON CREATE SET r.contexte = rel.contexte;


LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/MaximeCapron/foodforneo4j/master/Relations2.csv' AS rel FIELDTERMINATOR ';'
MATCH (p1 {id: rel.index})
MATCH (p2 {id: rel.index_relation})
MERGE (p1)-[r:SUPERIEUR]->(p2) ;


LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/MaximeCapron/foodforneo4j/master/Relations3.csv' AS rel FIELDTERMINATOR ';'
MATCH (c1 {id: rel.index})
MATCH (c2 {id: rel.index_relation})
MERGE (c1)-[r:FILIALE]->(c2) ;


LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/MaximeCapron/foodforneo4j/master/Relations4.csv' AS rel FIELDTERMINATOR ';'
MATCH (p {id: rel.index})
MATCH (c {id: rel.index_relation})
MERGE (p)-[r:EMPLOYE_DANS]->(c)
ON CREATE SET r.position = rel.position
"""


