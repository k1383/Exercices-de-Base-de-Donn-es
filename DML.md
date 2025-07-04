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

## Section 2: Insertion de Données (INSERT)

La commande `INSERT` permet d'ajouter de nouvelles lignes (enregistrements) dans une table. Il est crucial de s'assurer que les données insérées respectent les contraintes définies sur la table.

### Exercice 2.1: Insertion de Nouvelles Données

**Objectif:** Insérer de nouveaux enregistrements dans différentes tables.

**Instructions:**

1- Insérez un nouveau produit dans `projet_ecommerce.produits` (nom: 'Clavier Mécanique', prix: 89.99, stock: 15).

``     INSERT INTO produits (nom_produit, prix, stock) VALUES ('Clavier Mécanique', 89.99, 15);     ``

2- Insérez un nouvel article dans `blog_personnel.articles` (titre: 'Apprendre le DML', contenu: '...', auteur: 'Jean', date_publication: '2025-06-29').

``     INSERT INTO articles (titre, contenu, auteur, date_publication) VALUES ('Apprendre le DML', '...', 'Jean', '2025-06-29');     ``

3- Insérez un nouveau fournisseur dans `gestion_stock.fournisseurs` (nom: 'Global Supplies', adresse: '123 Rue de la Logistique').

``     INSERT INTO fournisseurs (nom_fournisseur, adresse) VALUES ( 'Global Supplies', '123 Rue de la Logistique');     ``

4- Insérez un nouveau client dans `crm_clients.clients` (nom: 'Bernard', prenom: 'Sophie', email: 'sophie.bernard@example.com', date_inscription: '2025-06-28').

``     INSERT INTO clients (nom, prenom, email, date_inscription) VALUES ('Bernard', 'Sophie', 'sophie.bernard@example.com', '2025-06-28');     ``

5- Insérez un nouvel utilisateur dans `forum_discussion.utilisateurs` (pseudo: 'ForumUser', email: 'forum.user@example.com').

``     INSERT INTO utilisateurs (pseudo, email) VALUES ('ForumUser', 'forum.user@example.com');     ``

6- Insérez un nouveau profil dans `reseau_social.profils` (nom_utilisateur: 'Voyageur', bio: 'Passionné de voyages.').

``     INSERT INTO profils (nom_utilisateur, bio) VALUES ('Voyageur', 'Passionné de voyages.');     ``

7- Insérez une nouvelle réservation dans `systeme_reservation.reservations` (nom_client: 'Famille Dubois', date_reservation: '2025-08-10', nombre_personnes: 4).

/

8- Insérez une nouvelle catégorie dans `catalogue_produits.categories` (nom_categorie: 'Vêtements').

``     INSERT INTO categories (nom_categorie) VALUES ('Vêtements');     ``

9- Insérez un nouveau projet dans `suivi_projets.projets` (nom_projet: 'Refonte Site Web', date_debut: '2025-07-01', statut: 'À faire').

``     INSERT INTO projets (nom_projet, date_debut, statut) VALUES ('Refonte Site Web', '2025-07-01', 'À faire');     ``

10- Insérez une nouvelle action dans `portefeuille_actions.actions` (symbole: 'AMZN', nom_entreprise: '[Amazon.com](http://amazon.com/) Inc.', prix_actuel: 180.50).

``     INSERT INTO actions (symbole, nom_entreprise, prix_actuel) VALUES ('AMZN', 'Amazon.comInc', 180.50);     ``

## Section 3: Modification de Données (UPDATE)

La commande `UPDATE` permet de modifier les valeurs des colonnes pour des enregistrements existants. La clause `WHERE` est essentielle pour cibler les enregistrements à modifier et éviter les mises à jour massives non intentionnelles.

### Exercice 3.1: Mise à Jour de Données

**Objectif:** Modifier des enregistrements spécifiques dans différentes tables.

**Instructions:**

1- Mettez à jour le `prix` du produit 'Clavier Mécanique' à 95.00 dans `projet_ecommerce.produits`.

``     UPDATE produits SET prix = 95.00 WHERE id_produits = 11;     ``

2- Changez l'`auteur` de l'article 'Apprendre le DML' à 'Marie' dans `blog_personnel.articles`.

``     UPDATE articles SET auteur = 'Marie' WHERE id_articles = 31;     ``

3- Mettez à jour l'`adresse` du fournisseur 'Global Supplies' à '456 Avenue Industrielle' dans `gestion_stock.fournisseurs`.

``     UPDATE fournisseurs SET adresse = '456 Avenue Industrielle' WHERE id_fournisseur = 11;     ``

4- Changez l'`email` du client 'Sophie Bernard' à 's.bernard@newmail.com' dans `crm_clients.clients`.

``     UPDATE clients SET email = 's.bernard@newmail.com' WHERE id_client = 3;     ``

5- Mettez à jour le `pseudo` de l'utilisateur 'ForumUser' à 'NewForumUser' dans `forum_discussion.utilisateurs`.

``     UPDATE utilisateurs SET pseudo = 'NewForumUser' WHERE id_utilisateur = 8;     `` 

6- Ajoutez une `bio` au profil 'Voyageur': 'Passionné de voyages et de photographie.' dans `reseau_social.profils`.

``     UPDATE profils SET bio = 'Passionné de voyages et de photographie.' WHERE id_profil = 8;     ``

7- Mettez à jour le `nombre_personnes` de la réservation de 'Famille Dubois' à 5 dans `systeme_reservation.reservations`.

/

8 Renommez la catégorie 'Vêtements' en 'Mode et Accessoires' dans `catalogue_produits.categories`.

``     UPDATE categories SET nom_categorie = 'Mode et Accessoires' WHERE id_categorie = 8;     ``

9- Changez le `statut` du projet 'Refonte Site Web' à 'En cours' dans `suivi_projets.projets`.

``     UPDATE projets SET statut = 'En cours' WHERE id_projet = 8;     ``

10- Mettez à jour le `prix_actuel` de l'action 'AMZN' à 182.75 et son `volume_echange` à 150000 dans `portefeuille_actions.actions`.

``     UPDATE actions SET prix_actuel = 182.75, volume_echange = 1500000 WHERE id_action = 11;     ``


## Section 4: Suppression de Données (DELETE)

La commande `DELETE` permet de supprimer des lignes (enregistrements) d'une table. Comme pour `UPDATE`, la clause `WHERE` est vitale pour éviter de supprimer toutes les données de la table par erreur.

### Exercice 4.1: Suppression de Données

**Objectif:** Supprimer des enregistrements spécifiques de différentes tables.

**Instructions:**

1- Supprimez le produit 'Clavier Mécanique' de `projet_ecommerce.produits`.

``     DELETE FROM produits WHERE nom_produit = 'Clavier Mécanique';     `` 

2- Supprimez l'article dont le `titre` est 'Apprendre le DML' de `blog_personnel.articles`.

``     DELETE FROM articles WHERE titre =  'Apprendre le DML';     ``

3- Supprimez le fournisseur 'Global Supplies' de `gestion_stock.fournisseurs`.

``     DELETE FROM fournisseurs WHERE nom_fournisseur =  'Global Supplies';     ``

4 Supprimez le client dont l'`email` est 's.bernard@newmail.com' de `crm_clients.clients`.

``     DELETE FROM clients WHERE email =  's.bernard@newmail.com';     ``

5- Supprimez l'utilisateur dont le `pseudo` est 'NewForumUser' de `forum_discussion.utilisateurs`.

``     DELETE FROM utilisateurs WHERE pseudo = 'NewForumUser';     ``

6- Supprimez le profil 'Voyageur' de `reseau_social.profils`.

``     DELETE FROM profils WHERE nom_utilisateur =  'Voyageur';     ``

7- Supprimez la réservation de 'Famille Dubois' de `systeme_reservation.reservations`.

/

8- Supprimez la catégorie 'Mode et Accessoires' de `catalogue_produits.categories`.

``     DELETE FROM categories WHERE nom_categorie = 'Mode et Accessoires';     ``

9- Supprimez le projet 'Refonte Site Web' de `suivi_projets.projets`.

``     DELETE FROM projets WHERE nom_projet = 'Refonte Site Web';     ``

10- Supprimez l'action 'AMZN' de `portefeuille_actions.actions`.

``     DELETE FROM actions WHERE symbole = 'AMZN';     ``