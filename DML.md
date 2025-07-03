# Exercices de Base de Données - DML (Data Manipulation Language)

Ce module d'exercices est dédié à la maîtrise du Langage de Manipulation de Données (DML) en SQL. Le DML vous permet d'interagir avec les données stockées dans votre base de données : les lire, les ajouter, les modifier et les supprimer. Chaque section contient de multiples variations d'exercices pour vous permettre de pratiquer chaque concept au moins 10 fois, renforçant ainsi votre compréhension et votre aisance.

**Prérequis:** Pour réaliser ces exercices, vous devez avoir créé les bases de données et les tables mentionnées dans les exercices DDL. Il est également recommandé d'insérer un jeu de données conséquent dans ces tables pour avoir de quoi manipuler.

## Section 1: Sélection de Données (SELECT)

La commande `SELECT` est la plus utilisée en SQL. Elle permet de récupérer des informations depuis une ou plusieurs tables. Cette section couvre les bases de la sélection, le filtrage avec `WHERE`, le tri avec `ORDER BY` et la limitation des résultats avec `LIMIT`.

### Exercice 1.1: Sélection Simple (Toutes Colonnes et Colonnes Spécifiques)

**Objectif:** Récupérer toutes les colonnes ou des colonnes spécifiques de différentes tables.

**Instructions:**

1- Sélectionnez toutes les données de la table `produits` dans la base de données `projet_ecommerce`.

``     SELECT * FROM `produits`;     ``

2- Sélectionnez le `titre` et l'`auteur` de tous les `articles` dans `blog_personnel`.

``     SELECT titre, auteur FROM `articles`;     ``

3- Sélectionnez toutes les données de la table `fournisseurs` dans `gestion_stock`.

``     SELECT * FROM `fournisseurs`;     ``

4- Sélectionnez le `nom` et le `prenom` de tous les `clients` dans `crm_clients`.

``     SELECT nom, prenom FROM `clients`;     ``

5- Sélectionnez toutes les données de la table `utilisateurs` dans `forum_discussion`.

``     SELECT * FROM `utilisateurs`;     ``

6- Sélectionnez le `nom_utilisateur` et la `date_creation` de tous les `profils` dans `reseau_social`.

``     SELECT nom_utilisateur, date_creation FROM profils;     ``

7- Sélectionnez toutes les données de la table `reservations` dans `systeme_reservation`.

/

8- Sélectionnez le `nom_categorie` de toutes les `categories` dans `catalogue_produits`.

``     SELECT nom_categorie FROM categories;     ``

9- Sélectionnez le `nom_projet` et le `statut` de tous les `projets` dans `suivi_projets`.

``     SELECT nom_projet, statut FROM projets;     ``

10- Sélectionnez le `symbole` et le `prix_actuel` de toutes les `actions` dans `portefeuille_actions`.

``     SELECT symbole, prix_actuel FROM actions;     ``

### Exercice 1.2: Filtrage avec WHERE (Opérateurs de Comparaison et Logiques)

**Objectif:** Utiliser la clause `WHERE` avec des opérateurs de comparaison (`=`, `>`, `<`, `>=`, `<=`, `!=` ou `<>`) et des opérateurs logiques (`AND`, `OR`, `NOT`) pour filtrer les résultats.

**Instructions:**

1- Sélectionnez les produits dont le `prix` est supérieur à 50.00 dans `projet_ecommerce.produits`.

``     SELECT prix FROM produits WHERE prix > 50.00;     ``

2- Sélectionnez les articles publiés après le '2024-01-01' dans `blog_personnel.articles`.

``     SELECT titre FROM articles WHERE date_publication > '24-01-01';     ``

3- Sélectionnez les fournisseurs dont l'`adresse` contient 'Paris' dans `gestion_stock.fournisseurs`.

``     SELECT nom_fournisseur FROM fournisseurs WHERE adresse LIKE '%Paris';     ``

4- Sélectionnez les clients dont le `nom` est 'Dupont' ET le `prenom` est 'Alice' dans `crm_clients.clients`.

``     SELECT nom, prenom FROM clients WHERE nom = 'Dupont' AND prenom = 'Alice';     ``

5- Sélectionnez les utilisateurs inscrits avant le '2023-06-30' OU dont le `pseudo` est 'Admin' dans `forum_discussion.utilisateurs`.

``     SELECT pseudo FROM utilisateurs WHERE (date_inscription = '2023-06-30' OR pseudo = 'Admin');     ``

6- Sélectionnez les profils dont la `bio` n'est PAS NULL dans `reseau_social.profils`.

``     SELECT nom_utilisateur FROM profils WHERE bio IS NULL;     ``

7- Sélectionnez les réservations pour '2025-07-01' avec plus de 2 `nombre_personnes` dans `systeme_reservation.reservations`.

/

8- Sélectionnez les catégories dont le `nom_categorie` est 'Électronique' ou 'Informatique' dans `catalogue_produits.categories`.

``     SELECT nom_categorie FROM categories WHERE nom_categorie = 'Électronique' OR nom_categorie ='Informatique';      ``

9- Sélectionnez les projets dont le `statut` est 'En cours' ET la `date_fin_prevue` est avant '2025-12-31' dans `suivi_projets.projets`.

``     SELECT nom_projet FROM projets WHERE statut = 'En cours' AND date_fin_prevue < '2025-12-31';     ``

10- Sélectionnez les actions dont le `prix_actuel` est inférieur à 100.00 ET le `volume_echange` est supérieur à 100000 dans `portefeuille_actions.actions`.

``     SELECT 	nom_entreprise FROM actions WHERE prix_actuel  < 100.00 AND volume_echange > 100000;     ``

### Exercice 1.3: Filtrage Avancé (IN, BETWEEN, LIKE)

**Objectif:** Utiliser les opérateurs `IN`, `BETWEEN`, et `LIKE` pour des filtres plus spécifiques.

**Instructions:**

1- Sélectionnez les produits dont le `id_produit` est 1, 3 ou 5 dans `projet_ecommerce.produits`.

``     SELECT nom_produit FROM produits WHERE id_produits IN ('1', '3', '5');     ``

2- Sélectionnez les articles dont le `titre` commence par 'SQL' dans `blog_personnel.articles`.

``     SELECT titre FROM articles WHERE titre LIKE 'SQL%';     ``

3- Sélectionnez les fournisseurs dont le `nom_fournisseur` contient 'Tech' dans `gestion_stock.fournisseurs`.

``     SELECT nom_fournisseur FROM fournisseurs WHERE nom_fournisseur LIKE '%Tech%';      ``

4- Sélectionnez les clients dont la `date_inscription` est entre '2023-01-01' et '2023-12-31' dans `crm_clients.clients`.

``     SELECT nom, prenom, date_inscription FROM clients WHERE date_inscription BETWEEN  '2023-01-01' AND '2023-12-31';      ``

5- Sélectionnez les utilisateurs dont le `pseudo` se termine par 'er' dans `forum_discussion.utilisateurs`.

``     SELECT pseudo FROM utilisateurs WHERE pseudo LIKE '%er';      ``

6- Sélectionnez les profils dont le `nom_utilisateur` contient 'john' ou 'jane' dans `reseau_social.profils`.

``     SELECT nom_utilisateur FROM profils WHERE nom_utilisateur LIKE '%john%' OR '%jane%';     ``

7- Sélectionnez les réservations dont le `nombre_personnes` est entre 3 et 5 (inclus) dans `systeme_reservation.reservations`.

/

8- Sélectionnez les catégories dont le `nom_categorie` est 'Livres', 'Musique' ou 'Films' dans `catalogue_produits.categories`.

``     SELECT nom_categorie FROM categories WHERE nom_categorie IN ('Livres', 'Musique', 'Films');     ``

9- Sélectionnez les projets dont le `nom_projet` contient 'Phase 1' dans `suivi_projets.projets`.

``     SELECT nom_projet FROM projets WHERE nom_projet LIKE '%Phase 1%';     ``

10- Sélectionnez les actions dont le `symbole` est 'GOOG', 'MSFT' ou 'AAPL' dans `portefeuille_actions.actions`.

``     SELECT symbole FROM actions WHERE symbole IN ('GOOD', 'MSFT', 'AAPL');     ``

### Exercice 1.4: Tri des Résultats (ORDER BY) et Limitation (LIMIT)

**Objectif:** Trier les résultats de vos requêtes en ordre croissant ou décroissant sur une ou plusieurs colonnes, et limiter le nombre de lignes retournées.

**Instructions:**

1- Sélectionnez tous les produits et triez-les par `prix` par ordre croissant dans `projet_ecommerce.produits`.

``     SELECT prix FROM `produits` ORDER BY prix ASC;     ``

2- Sélectionnez les 5 articles les plus récents dans `blog_personnel.articles` (triez par `date_publication` décroissant et limitez).

``     SELECT titre, date_publication FROM `articles` ORDER BY date_publication DESC LIMIT 5;     ``

3- Sélectionnez les fournisseurs par `nom_fournisseur` par ordre alphabétique décroissant dans `gestion_stock.fournisseurs`.

``     SELECT nom_fournisseur FROM `fournisseurs` ORDER BY nom_fournisseur DESC;     ``

4- Sélectionnez les 10 premiers clients inscrits dans `crm_clients.clients` (triez par `date_inscription` croissant et limitez).

``     SELECT nom, prenom, date_inscription FROM `clients` ORDER BY date_inscription DESC;     ``

5- Sélectionnez les utilisateurs par `date_inscription` par ordre décroissant, puis par `pseudo` par ordre croissant dans `forum_discussion.utilisateurs`.

``     SELECT pseudo, date_inscription FROM `utilisateurs`ORDER BY date_inscription ASC, pseudo DESC;     ``

6- Sélectionnez les 3 profils les plus anciens dans `reseau_social.profils`.

``     SELECT nom_utilisateur, date_creation FROM `profils` ORDER BY date_creation ASC LIMIT 3;     ``

7- Sélectionnez les réservations par `date_reservation` par ordre croissant, puis par `nombre_personnes` par ordre décroissant dans `systeme_reservation.reservations`.

/

8- Sélectionnez les catégories par `nom_categorie` par ordre alphabétique croissant dans `catalogue_produits.categories`.

``     SELECT nom_categorie FROM `categories` ORDER BY nom_categorie ASC;     ``

9- Sélectionnez les 7 projets dont le `statut` est 'Terminé', triés par `date_fin_prevue` décroissant dans `suivi_projets.projets`.

``     SELECT nom_projet, statut FROM `projets` WHERE statut = 'Terminé' ORDER BY date_fin_prevue ASC LIMIT 7;     ``

10- Sélectionnez les 5 actions les plus chères dans `portefeuille_actions.actions`.

``     SELECT nom_entreprise, prix_actuel FROM `actions` ORDER BY prix_actuel DESC LIMIT 5;      ``