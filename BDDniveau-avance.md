# Exercices de Base de Données - Niveau Avancé

Ce module d'exercices est conçu pour vous faire maîtriser les concepts SQL les plus complexes, essentiels pour l'analyse de données et la gestion de bases de données relationnelles à grande échelle. Vous explorerez les fonctions d'agrégation, les regroupements, les jointures complexes et la gestion des transactions. Chaque section contient de multiples variations d'exercices pour vous permettre de pratiquer chaque concept au moins 10 fois, renforçant ainsi votre compréhension et votre aisance.

**Prérequis:** Pour réaliser ces exercices, vous devez avoir créé les bases de données et les tables mentionnées dans les exercices DDL, et inséré un jeu de données conséquent dans ces tables. Pour les exercices de jointure, assurez-vous que vos tables ont des relations de clés étrangères établies et des données cohérentes.

## Section 1: Fonctions d'Agrégation et Regroupement (GROUP BY, HAVING)

Les fonctions d'agrégation permettent de réaliser des calculs sur des ensembles de lignes, tandis que `GROUP BY` et `HAVING` offrent la possibilité de synthétiser ces données par catégories et de filtrer les groupes résultants.

## Section 1: Fonctions d'Agrégation et Regroupement (GROUP BY, HAVING)

Les fonctions d'agrégation permettent de réaliser des calculs sur des ensembles de lignes, tandis que `GROUP BY` et `HAVING` offrent la possibilité de synthétiser ces données par catégories et de filtrer les groupes résultants.

### Exercice 1.1: Utilisation des Fonctions d'Agrégation (COUNT, SUM, AVG, MAX, MIN)

**Objectif:** Appliquer les fonctions `COUNT`, `SUM`, `AVG`, `MAX`, `MIN` pour obtenir des statistiques sur les données.

**Instructions:**

1 Comptez le nombre total de produits dans `projet_ecommerce.produits`.

``     SELECT COUNT(id_produits) FROM produits;     ``  

2- Calculez le prix moyen de tous les produits dans `projet_ecommerce.produits`.

``     SELECT AVG(prix) FROM produits;     ``

3- Trouvez le prix maximum d'un produit dans `projet_ecommerce.produits`.

``     SELECT Max(prix) FROM produits;     ``

4- Trouvez le prix minimum d'un produit dans `projet_ecommerce.produits`.

``     SELECT Min(prix) FROM produits;     ``
5- Calculez la somme totale du stock de tous les produits dans `projet_ecommerce.produits`.

``     SELECT SUM(stock) FROM produits;      ``

6- Comptez le nombre total d'articles dans `blog_personnel.articles`.

``     SELECT COUNT(id_articles) FROM articles;    ``  

7- Trouvez la date de publication la plus récente dans `blog_personnel.articles`.

``     SELECT MAX(date_publication) FROM articles;     `` 

8- Trouvez la date de publication la plus ancienne dans `blog_personnel.articles`.

``     SELECT MIN(date_publication) FROM articles;     ``

9- Comptez le nombre total de clients dans `crm_clients.clients`.

``     SELECT COUNT(id_client) FROM clients;     ``  

10- Trouvez la date d'inscription la plus récente dans `crm_clients.clients`.

``     SELECT SUM(id_client) FROM clients;     ``