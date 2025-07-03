# Exercices de Base de Données - DDL (Data Definition Language)

Ce module d'exercices est dédié à la maîtrise du Langage de Définition de Données (DDL) en SQL. Le DDL vous permet de créer, modifier et supprimer la structure de votre base de données. Chaque section contient de multiples variations d'exercices pour vous permettre de pratiquer chaque concept au moins 10 fois, renforçant ainsi votre compréhension et votre aisance.

## Section 1: Création de Bases de Données et Gestion des Utilisateurs

Cette section couvre les opérations fondamentales de création de bases de données et de gestion des utilisateurs, incluant l'attribution de privilèges. Ces compétences sont essentielles pour configurer des environnements de développement et de production sécurisés.

### Exercice 1.1: Création de Bases de Données

**Objectif:** Créer de nouvelles bases de données en utilisant des commandes SQL.

**Instructions:**

1- Créez une base de données nommée ``projet_ecommerce``.

`` CREATE DATABASE IF NOT EXISTS `projet_ecommerce`;
USE `projet_ecommerce`; ``

2- Créez une base de données nommée ``blog_personnel``.

`` CREATE DATABASE IF NOT EXISTS `blog_personnel`;
USE `blog_personnel`; ``

3- Créez une base de données nommée ``gestion_stock``.

`` CREATE DATABASE IF NOT EXISTS `gestion_stock`;
USE `gestion_stock`; ``

4- Créez une base de données nommée ``crm_clients``.

`` CREATE DATABASE IF NOT EXISTS `crm_clients`;
USE `crm_clients`; ``

5- Créez une base de données nommée ``forum_discussion``.

`` CREATE DATABASE IF NOT EXISTS `forum_discussion`;
USE `forum_discussion`; ``

6- Créez une base de données nommée ``reseau_social``.

`` CREATE DATABASE IF NOT EXISTS `reseau_social`;
USE `reseau_social`; ``

7- Créez une base de données nommée ``systeme_reservation``.

`` CREATE DATABASE IF NOT EXISTS `systeme_reservation`;
USE `systeme_reservation`; ``

8- Créez une base de données nommée ``catalogue_produits``.

`` CREATE DATABASE IF NOT EXISTS `catalogue_produits`;
USE `catalogue_produits`; ``

9- Créez une base de données nommée ``suivi_projets``.

`` CREATE DATABASE IF NOT EXISTS `suivi_projets`;
USE `suivi_projets`; ``

10- Créez une base de données nommée ``portefeuille_actions``.

`` CREATE DATABASE IF NOT EXISTS `portefeuille_actions`;
USE `portefeuille_actions`; ``

### Exercice 1.2: Création d'Utilisateurs et Attribution de Privilèges

**Objectif:** Créer de nouveaux utilisateurs MySQL et leur attribuer des privilèges spécifiques sur des bases de données.

**Instructions:**

1- Créez un utilisateur `admin_ecommerce` avec le mot de passe `ecom_pass` et donnez-lui tous les privilèges sur `projet_ecommerce`.

2- Créez un utilisateur `blog_writer` avec le mot de passe `blog_pass` et donnez-lui les privilèges `SELECT`, `INSERT`, `UPDATE`, `DELETE` sur `blog_personnel`.

3- Créez un utilisateur `stock_manager` avec le mot de passe `stock_pass` et donnez-lui tous les privilèges sur `gestion_stock`.

4- Créez un utilisateur `crm_viewer` avec le mot de passe `crm_pass` et donnez-lui le privilège `SELECT` sur `crm_clients`.

5- Créez un utilisateur `forum_moderator` avec le mot de passe `forum_pass` et donnez-lui les privilèges `SELECT`, `INSERT`, `UPDATE`, `DELETE` sur `forum_discussion`.

6- Créez un utilisateur `social_user` avec le mot de passe `social_pass` et donnez-lui les privilèges `SELECT`, `INSERT`, `UPDATE` sur `reseau_social`.

7- Créez un utilisateur `res_agent` avec le mot de passe `res_pass` et donnez-lui les privilèges `SELECT`, `INSERT`, `UPDATE` sur `systeme_reservation`.

8- Créez un utilisateur `prod_catalog` avec le mot de passe `prod_pass` et donnez-lui le privilège `SELECT` sur `catalogue_produits`.

9- Créez un utilisateur `project_lead` avec le mot de passe `proj_pass` et donnez-lui tous les privilèges sur `suivi_projets`.

10- Créez un utilisateur `investor` avec le mot de passe `inv_pass` et donnez-lui le privilège `SELECT` sur `portefeuille_actions`.

## Section 2: Création de Tables (CREATE TABLE) et Types de Données

Cette section se concentre sur la définition de la structure des tables, en choisissant les types de données appropriés pour chaque colonne et en appliquant les contraintes de base pour garantir l'intégrité des données.

### Exercice 2.1: Création de Tables avec Types de Données et Contraintes de Base

**Objectif:** Créer diverses tables en utilisant des types de données variés et des contraintes `PRIMARY KEY`, `AUTO_INCREMENT`, `NOT NULL`, `UNIQUE`, `DEFAULT`.

**Instructions:**

1- Dans ``projet_ecommerce``, créez une table ``produits`` avec ``id_produit`` (INT PK AI), ``nom_produit`` (VARCHAR(255) NOT NULL UNIQUE), ``prix`` (DECIMAL(10,2) NOT NULL), ``stock`` (INT DEFAULT 0).

``     CREATE TABLE produits (     ``
``     id_produits INT PRIMARY KEY AUTO_INCREMENT,     ``
``     nom_produit VARCHAR(255) NOT NULL UNIQUE,     ``
``     prix DECIMAL(10,2) NOT NULL,     ``
``     stock INT DEFAULT 0     ``
``     ) ENGINE = INNODB     ``

-2 Dans ``blog_personnel``, créez une table ``articles`` avec ``id_article`` (INT PK AI), ``titre`` (VARCHAR(255) NOT NULL), ``contenu`` (TEXT), ``date_publication`` (DATETIME DEFAULT CURRENT_TIMESTAMP), ``auteur`` (VARCHAR(100) NOT NULL).

``     CREATE TABLE articles (     ``
``     id_articles INT PRIMARY KEY AUTO_INCREMENT,      ``
``     titre VARCHAR(255) NOT NULL,      ``   
``     contenu TEXT,      ``
``     date_publication DATETIME DEFAULT CURRENT_TIMESTAMP,      ``  
``     auteur VARCHAR(100) NOT NULL      ``
``     ) ENGINE = INNODB      ``

- CURRENT_TIMESTAMP renvoie la date et l'heure actuelles dans le fuseau horaire de la session

3- Dans ``gestion_stock``, créez une table ``fournisseurs`` avec ``id_fournisseur`` (INT PK AI), ``nom_fournisseur`` (VARCHAR(255) NOT NULL UNIQUE), ``adresse`` (VARCHAR(255)).

``     CREATE TABLE fournisseurs (     ``
``     id_fournisseur INT PRIMARY KEY AUTO_INCREMENT,     ``
``     nom_fournisseur VARCHAR(255) NOT NULL UNIQUE,     ``
``     adresse VARCHAR(255)     ``
``     ) ENGINE = INNODB     ``

4- Dans ``crm_clients``, créez une table ``clients`` avec ``id_client`` (INT PK AI), ``nom`` (VARCHAR(100) NOT NULL), ``prenom`` (VARCHAR(100) NOT NULL), ``email`` (VARCHAR(255) UNIQUE), ``date_inscription`` (DATE).

``     CREATE TABLE clients (     ``
``     id_client INT PRIMARY KEY AUTO_INCREMENT,     ``
``     nom VARCHAR(100) NOT NULL,     ``
``     prenom VARCHAR(100) NOT NULL,     ``
``     email VARCHAR(255) UNIQUE,     ``
``     date_inscription DATE     ``
``     ) ENGINE = INNODB     ``

5- Dans ``forum_discussion``, créez une table ``utilisateurs`` avec ``id_utilisateur`` (INT PK AI), ``pseudo`` (VARCHAR(50) NOT NULL UNIQUE), ``email`` (VARCHAR(200) NOT NULL UNIQUE), ``date_inscription`` (TIMESTAMP DEFAULT CURRENT_TIMESTAMP).

``     CREATE TABLE utilisateurs (     ``
``     id_utilisateur INT PRIMARY KEY AUTO_INCREMENT,    ``
``     pseudo VARCHAR(50) NOT NULL UNIQUE,    ``
``     email VARCHAR(200) NOT NULL UNIQUE,     ``
``     date_inscription TIMESTAMP DEFAULT CURRENT_TIMESTAMP     ``
``     ) ENGINE = INNODB     ``

6- Dans ``reseau_social``, créez une table ``profils`` avec ``id_profil`` (INT PK AI), ``nom_utilisateur`` (VARCHAR(100) NOT NULL UNIQUE), ``bio`` (TEXT), ``date_creation`` (TIMESTAMP DEFAULT CURRENT_TIMESTAMP).

``     CREATE TABLE profils (     ``  
``     id_profil INT PRIMARY KEY AUTO_INCREMENT,     ``  
``     nom_utilisateur VARCHAR(100) NOT NULL UNIQUE,     ``  
``     bio TEXT,     ``  
``     date_creation TIMESTAMP DEFAULT CURRENT_TIMESTAMP     ``  
``     ) ENGINE = INNODB     ``  

7- Dans ``systeme_reservation``, créez une table ``reservations`` avec ``id_reservation`` (INT PK AI), ``nom_client`` (VARCHAR(100) NOT NULL), ``date_reservation`` (DATE NOT NULL), ``nombre_personnes`` (INT NOT NULL DEFAULT 1).

/

8- Dans `catalogue_produits`, créez une table ``categories`` avec ``id_categorie`` (INT PK AI), ``nom_categorie`` (VARCHAR(100) NOT NULL UNIQUE).

``     CREATE TABLE categories (     `` 
``     id_categorie INT PRIMARY KEY AUTO_INCREMENT,     `` 
``     nom_categorie VARCHAR(100) NOT NULL UNIQUE     `` 
``     ) ENGINE =INNODB     `` 

9- Dans ``suivi_projets``, créez une table ``projets`` avec ``id_projet`` (INT PK AI), ``nom_projet`` (VARCHAR(255) NOT NULL), ``date_debut`` (DATE NOT NULL), ``date_fin_prevue`` (DATE), ``statut`` (VARCHAR(50) ``DEFAULT`` 'En cours').

``     CREATE TABLE projets (     ``
``     id_projet INT PRIMARY KEY AUTO_INCREMENT,     ``
``     nom_projet VARCHAR(255) NOT NULL,     ``
``     date_debut DATE NOT NULL,     ``
``     date_fin_prevue DATE,     ``
``     statut VARCHAR(50) DEFAULT 'En cours'     ``
``     ) ENGINE = INNODB     ``

10- Dans ``portefeuille_actions``, créez une table ``actions`` avec ``id_action`` (INT PK AI), ``symbole`` (VARCHAR(10) NOT NULL UNIQUE), ``nom_entreprise`` (VARCHAR(255) NOT NULL), ``prix_actuel`` (DECIMAL(10,2)).

``     CREATE TABLE actions (     `` 
``     id_action INT PRIMARY KEY AUTO_INCREMENT,     `` 
``     symbole VARCHAR(10) NOT NULL UNIQUE,     `` 
``     nom_entreprise VARCHAR(255) NOT NULL,     `` 
``     prix_actuel DECIMAL(10,2)     `` 
``     ) ENGINE = INNODB     `` 

## Section 3: Modification de la Structure des Tables (ALTER TABLE)

Cette section vous fera pratiquer l'utilisation de la commande `ALTER TABLE` pour modifier la structure des tables existantes, y compris l'ajout, la suppression et la modification de colonnes, ainsi que la gestion des contraintes.

### Exercice 3.1: Ajout et Suppression de Colonnes

**Objectif:** Ajouter et supprimer des colonnes dans des tables existantes.

**Instructions:**

1- Dans ``projet_ecommerce.produits``, ajoutez une colonne ``description`` de type TEXT.

``     ALTER TABLE produits ADD COLUMN description TEXT;     ``

2- Dans ``blog_personnel.articles``, ajoutez une colonne ``categorie`` de type VARCHAR(50).

``     ALTER TABLE articles ADD COLUMN categorie VARCHAR(50);     ``

3- Dans ``gestion_stock.fournisseurs``, ajoutez une colonne ``telephone`` de type VARCHAR(20).

``     ALTER TABLE fournisseurs ADD COLUMN telephone VARCHAR(20);     ``

4- Dans ``crm_clients.clients``, ajoutez une colonne ``ville`` de type VARCHAR(100).

``     ALTER TABLE clients ADD COLUMN ville VARCHAR(100);     ``

5- Dans ``forum_discussion``.utilisateurs, ajoutez une colonne ``derniere_connexion`` de type DATETIME.

``     ALTER TABLE utilisateurs ADD COLUMN derniere_connexion DATETIME;     ``

6- Dans ``reseau_social.profils``, ajoutez une colonne ``date_naissance`` de type DATE.

``     ALTER TABLE profils ADD COLUMN date_naissance DATE;     ``

7- Dans ``systeme_reservation.reservations``, ajoutez une colonne ``commentaire`` de type TEXT.

/

8- Dans ``catalogue_produits.categories``, ajoutez une colonne ``description_categorie`` de type TEXT.

``     ALTER TABLE categories ADD COLUMN description_categorie TEXT;     ``

9- Dans`` suivi_projets.projets``, ajoutez une colonne ``budget`` de type DECIMAL(15,2).

``     ALTER TABLE projets ADD COLUMN budget DECIMAL(15,2);     ``

10- Dans ``portefeuille_actions.actions``, ajoutez une colonne ``volume_echange`` de type BIGINT.

``     ALTER TABLE actions ADD COLUMN volume_echange BIGINT;     ``

### Exercice 3.2: Modification de Colonnes

**Objectif:** Modifier le type de données ou les contraintes de colonnes existantes.

**Instructions:**

1- Dans ``projet_ecommerce.produits``, modifiez la colonne ``prix`` pour qu'elle accepte 4 décimales (DECIMAL(10,4)).

``     ALTER TABLE produits MODIFY COLUMN prix DECIMAL(10.4);     ``

2- Dans ``blog_personnel.articles``, modifiez la colonne ``auteur`` pour qu'elle soit NOT NULL (si ce n'est pas déjà le cas).

/

-3 Dans ``gestion_stock.fournisseurs``, modifiez la colonne ``adresse`` pour qu'elle soit VARCHAR(500).

``     ALTER TABLE fournisseurs MODIFY COLUMN adresse VARCHAR(500);     ``

4- Dans ``crm_clients.clients``, modifiez la colonne ``email`` pour qu'elle soit NOT NULL.

/

5- Dans ``forum_discussion.utilisateurs``, modifiez la colonne ``pseudo`` pour qu'elle soit VARCHAR(100).

``     ALTER TABLE utilisateurs MODIFY COLUMN pseudo VARCHAR(100);     ``

6- Dans ``reseau_social.profils``, modifiez la colonne ``bio`` pour qu'elle soit VARCHAR(1000).

``     ALTER TABLE profils MODIFY COLUMN bio VARCHAR(1000);     ``

7- Dans ``systeme_reservation.reservations``, modifiez la colonne ``nombre_personnes`` pour qu'elle ait une valeur par défaut de 2.

/ 

8- Dans ``catalogue_produits.categories``, modifiez la colonne ``nom_categorie`` pour qu'elle soit VARCHAR(200).

``     ALTER TABLE categories MODIFY COLUMN nom_categorie VARCHAR(200);     ``

9- Dans ``suivi_projets.projets``, modifiez la colonne ``statut`` pour qu'elle ait une valeur par défaut de 'À faire'.

/

10- Dans ``portefeuille_actions.actions``, modifiez la colonne ``prix_actuel`` pour qu'elle soit DECIMAL(12,4).

``     ALTER TABLE actions MODIFY COLUMN prix_actuel DECIMAL(12,4);     ``

### Exercice 3.3: Ajout et Suppression de Contraintes (PK, FK)

**Objectif:** Gérer les contraintes de clé primaire et étrangère sur des tables existantes.
ON DELETE SET NULL 
ON UPDATE CASCADE;
**Instructions:**

1- Dans ``projet_ecommerce``, créez une table ``commandes`` avec ``id_commande`` (PK AI), date_commande (DATETIME DEFAULT CURRENT_TIMESTAMP), ``fk_id_client`` (INT). Ajoutez ensuite la contrainte de clé étrangère ``fk_id_client`` vers une table ``clients`` (que vous devrez créer si elle n'existe pas).

- Création de la table clients dans la BDD ``projet_ecommerce``

``     CREATE TABLE clients (     ``
``     id_client INT PRIMARY KEY AUTO_INCREMENT,     ``
``     nom VARCHAR(100) NOT NULL,     ``
``     prenom VARCHAR(100) NOT NULL,     ``
``     email VARCHAR(255) UNIQUE,     ``
``     date_inscription DATE     ``
``     ) ENGINE = INNODB     ``

- Création de la table ``commandes``

``     CREATE TABLE commandes (     ``  
``     id_commande INT PRIMARY KEY AUTO_INCREMENT,     ``  
``     date_commande DATETIME DEFAULT CURRENT_TIMESTAMP,     ``  
``     fk_id_client INT,     ``  
``     CONSTRAINT fk_id_client     ``  
``     FOREIGN KEY (fk_id_client)     ``   
``     REFERENCES clients(id_client)     ``  
``     ON DELETE SET NULL     ``  
``     ON UPDATE CASCADE     ``  
``     ) ENGINE = INNODB     ``  

2- Dans ``blog_personnel``, créez une table ``commentaires`` avec ``id_commentaire`` (PK AI), ``texte_commentaire`` (TEXT), ``fk_id_article`` (INT), ``fk_id_utilisateur`` (INT). Ajoutez les FKs vers ``articles`` et ``utilisateurs`` (à créer si besoin).

- Création de la table ``utilisateurs``

``     CREATE TABLE utilisateurs (     ``
``     id_utilisateur INT PRIMARY KEY AUTO_INCREMENT,    ``
``     pseudo VARCHAR(50) NOT NULL UNIQUE,    ``
``     email VARCHAR(200) NOT NULL UNIQUE,     ``
``     date_inscription TIMESTAMP DEFAULT CURRENT_TIMESTAMP     ``
``     ) ENGINE = INNODB     ``

- Création de la table ``commentaires``

``     CREATE TABLE commentaires (     ``  
``     id_commentaires INT PRIMARY KEY AUTO_INCREMENT,     `` 
``     texte_commentaire TEXT,     `` 
``     fk_id_article INT,     `` 
``     fk_id_utilisateur INT,     `` 
``     CONSTRAINT fk_id_article     ``
``     FOREIGN KEY (fk_id_article)     `` 
``     REFERENCES articles(id_article),     `` 
``     FOREIGN KEY (fk_id_utilisateur)     `` 
``     REFERENCES utilisateurs(id_utilisateur)     `` 
``     ON DELETE SET NULL     `` 
``     ON UPDATE CASCADE     `` 
``     ) ENGINE = INNODB     `` 

3- Dans ``gestion_stock``, créez une table ``produits_stock`` avec ``id_produit_stock`` (PK AI), ``nom`` (VARCHAR(255)), ``fk_id_fournisseur`` (INT). Ajoutez la FK vers fournisseurs.

``     CREATE TABLE produits_stock (     `` 
``     id_produit_stock INT PRIMARY KEY AUTO_INCREMENT,     `` 
``     nom VARCHAR(255),     `` 
``     fk_id_fournisseur INT,     `` 
``     	CONSTRAINT fk_id_fournisseur     ``
``     FOREIGN KEY (fk_id_fournisseur)     `` 
``     REFERENCES fournisseurs (id_fournisseur)     `` 
``     ON DELETE SET NULL     `` 
``     ON UPDATE CASCADE     `` 
``     ) ENGINE = INNODB     `` 

4- Dans ``crm_clients``, créez une table ``interactions`` avec ``id_interaction`` (PK AI), ``type_interaction`` (VARCHAR(50)), ``date_interaction`` (DATETIME), ``fk_id_client`` (INT). Ajoutez la FK vers ``clients``.

``     CREATE TABLE interactions (     ``  
``     id_interaction INT PRIMARY KEY AUTO_INCREMENT,    ``  
``     type_interaction VARCHAR(50),    ``  
``     date_interaction DATETIME,    ``                   
``     fk_id_client INT,    `` 
``     CONSTRAINT fk_id_client     `` 
``     FOREIGN KEY (fk_id_client)    ``  
``     REFERENCES clients (id_client)    ``  
``     ON DELETE SET NULL    ``  
``     ON UPDATE CASCADE    ``  
``     ) ENGINE = INNODB    ``  

5- Dans ``forum_discussion``, créez une table ``messages`` avec ``id_message`` (PK AI), ``contenu`` (TEXT), ``fk_id_utilisateur`` (INT), ``fk_id_sujet`` (INT). Ajoutez les FKs vers ``utilisateurs`` et ``sujets`` (à créer si besoin).

- Création de la table ``sujets``

``     CREATE TABLE sujets (     ``
``     id_sujet INT PRIMARY KEY AUTO_INCREMENT     ``
``     ) ENGINE = INNODB     ``

- Création de la table ``messages``

``     CREATE TABLE messages (      ``
``     id_message INT PRIMARY KEY AUTO_INCREMENT,      ``
``     contenu TEXT,      ``
``     fk_id_utilisateur INT,      ``
``     fk_id_sujet INT,      ``
``     CONSTRAINT fk_id_utilisateur     ``
``     FOREIGN KEY (fk_id_utilisateur)      ``
``     REFERENCES utilisateurs (id_utilisateur),      ``
``     FOREIGN KEY (fk_id_sujet)      ``
``     REFERENCES sujets (id_sujet)      ``
``     ON DELETE SET NULL      ``
``     ON UPDATE CASCADE      ``
``     ) ENGINE = INNODB     ``

6- Dans ``reseau_social``, créez une table ``posts`` avec ``id_post`` (PK AI), ``texte_post`` (TEXT), ``fk_id_profil`` (INT). Ajoutez la FK vers ``profils``.

``     CREATE TABLE posts (     `` 
``     id_post INT PRIMARY KEY AUTO_INCREMENT,     `` 
``     texte_post TEXT,     `` 
``     fk_id_profil INT,     `` 
``     CONSTRAINT fk_id_profil     ``
``     FOREIGN KEY (fk_id_profil)     `` 
``     REFERENCES profils (id_profil)     `` 
``     ON DELETE SET NULL     `` 
``     ON UPDATE CASCADE     `` 
``     ) ENGINE = INNODB     `` 

7- Dans ``systeme_reservation``, créez une table ``chambres`` avec ``id_chambre`` (PK AI), numero_chambre (VARCHAR(10) UNIQUE), capacite (INT). Ajoutez une colonne ``fk_id_chambre`` à reservations et la FK vers ``chambres``.

/

8- Dans ``catalogue_produits``, créez une table ``produits_cat`` avec ``id_produit_cat`` (PK AI), ``nom`` (VARCHAR(255)), `fk_id_categorie` (INT). Ajoutez la FK vers ``categories``.`

``     CREATE TABLE produits_cat (     `` 
``     id_produits_cat INT PRIMARY KEY AUTO_INCREMENT,     `` 
``     nom VARCHAR(255),     `` 
``     fk_id_categorie INT,     `` 
``     CONSTRAINT fk_id_categorie     ``
``     FOREIGN KEY (fk_id_categorie)     `` 
``     REFERENCES categories (id_categorie)     `` 
``     ON DELETE SET NULL     `` 
``     ON UPDATE CASCADE     `` 
``     ) ENGINE = INNODB     `` 

9- Dans ``suivi_projets``, créez une table ``taches`` avec ``id_tache`` (PK AI), ``description`` (TEXT), ``fk_id_projet`` (INT). Ajoutez la FK vers ``projets``.

``     CREATE TABLE taches (     ``
``     id_tache INT PRIMARY KEY AUTO_INCREMENT,     ``
``     description TEXT,     ``
``     fk_id_projet INT,     ``
``     CONSTRAINT fk_id_projet     ``
``     FOREIGN KEY (fk_id_projet)     ``
``     REFERENCES projets (id_projet)     ``
``     ON DELETE SET NULL     ``
``     ON UPDATE CASCADE     ``
``     ) ENGINE = INNODB     ``

10- Dans ``portefeuille_actions``, créez une table ``transactions`` avec ``id_transaction`` (PK AI), ``type`` (VARCHAR(10)), ``quantite`` (INT), ``fk_id_action`` (INT). Ajoutez la FK vers ``actions``.

``     CREATE TABLE transactions (      `` 
``     id_transaction INT PRIMARY KEY AUTO_INCREMENT,     `` 
``     type VARCHAR(10),     `` 
``     quantite INt,     `` 
``     fk_id_action INT,     ``
``      CONSTRAINT fk_id_action     `` 
``     FOREIGN KEY (fk_id_action)     `` 
``     REFERENCES actions (id_action)     `` 
``     ON DELETE SET NULL     `` 
``     ON UPDATE CASCADE     `` 
``     ) ENGINE = INNODB    `` 

### Exercice 3.4: Suppression de Contraintes

**Objectif:** Supprimer des contraintes de clé primaire et étrangère.

**Instructions:**

1- Dans ``projet_ecommerce.commandes``, supprimez la clé étrangère ``fk_id_client``.

``     ALTER TABLE commandes DROP CONSTRAINT fk_id_client;     ``

2- Dans `blog_personnel.commentaires`, supprimez la clé étrangère `fk_id_article`.

``     ALTER TABLE commentaires DROP CONSTRAINT fk_id_article;      ``

3- Dans `gestion_stock.produits_stock`, supprimez la clé étrangère `fk_id_fournisseur`.

``     ALTER TABLE  produits_stock DROP CONSTRAINT fk_id_fournisseur;     ``

4- Dans `crm_clients.interactions`, supprimez la clé étrangère `fk_id_client`.

``     ALTER TABLE  interactions DROP CONSTRAINT fk_id_client;     ``

5- Dans `forum_discussion.messages`, supprimez la clé étrangère `fk_id_utilisateur`.

``     ALTER TABLE  messages DROP CONSTRAINT fk_id_utilisateur;     ``

6- Dans `reseau_social.posts`, supprimez la clé étrangère `fk_id_profil`.

``     ALTER TABLE  posts DROP CONSTRAINT fk_id_profil;     ``

7- Dans `systeme_reservation.reservations`, supprimez la clé étrangère `fk_id_chambre`.

/

8- Dans `catalogue_produits.produits_cat`, supprimez la clé étrangère `fk_id_categorie`.

``     ALTER TABLE produits_cat DROP CONSTRAINT fk_id_categorie;     ``

9- Dans `suivi_projets.taches`, supprimez la clé étrangère `fk_id_projet`.

``     ALTER TABLE taches DROP CONSTRAINT fk_id_projet;     ``

10- Dans `portefeuille_actions.transactions`, supprimez la clé étrangère `fk_id_action`.

``     ALTER TABLE transactions DROP CONSTRAINT fk_id_action;     ``

## Section 4: Suppression et Vidage de Tables (DROP TABLE, TRUNCATE TABLE)

Cette section vous fera pratiquer la suppression complète de tables et le vidage de toutes les données d'une table, en soulignant l'importance de la prudence avec ces commandes irréversibles.

### Exercice 4.1: Suppression de Tables (DROP TABLE)

**Objectif:** Supprimer des tables entières de la base de données.

**Instructions:**

1- Supprimez la table `produits` de `projet_ecommerce`.

``     DROP TABLE produits;     ``

2- Supprimez la table `articles` de `blog_personnel`.

``     DROP TABLE articles;     ``

3- Supprimez la table `fournisseurs` de `gestion_stock`.

``     DROP TABLE fournisseurs;     ``

4- Supprimez la table `clients` de `crm_clients`.

``    DROP TABLE clients;     ``

5- Supprimez la table `utilisateurs` de `forum_discussion`.

``     DROP TABLE utilisateurs;     ``

6- Supprimez la table `profils` de `reseau_social`.

``     DROP TABLE profils;     ``

7- Supprimez la table `reservations` de `systeme_reservation`.

/

8- Supprimez la table `categories` de `catalogue_produits`.

``     DROP TABLE categories;     ``

9- Supprimez la table `projets` de `suivi_projets`.

``     DROP TABLE projets;     ``

10- Supprimez la table `actions` de `portefeuille_actions`.

``     DROP TABLE actions;     ``

### Exercice 4.2: Vidage de Tables (TRUNCATE TABLE)

**Objectif:** Vider toutes les données d'une table tout en conservant sa structure.

**Instructions:**

1- Videz la table `commandes` de `projet_ecommerce`.

``     TRUNCATE TABLE commandes;     ``

2- Videz la table `commentaires` de `blog_personnel`.

``     TRUNCATE TABLE commentaires;     ``

3- Videz la table `produits_stock` de `gestion_stock`.

``     TRUNCATE TABLE produits_stock;     ``

4- Videz la table `interactions` de `crm_clients`.

``     TRUNCATE TABLE interactions;     ``

5- Videz la table `messages` de `forum_discussion`.

``      TRUNCATE TABLE messages;      ``

6- Videz la table `posts` de `reseau_social`.

``      TRUNCATE TABLE posts;      ``

7- Videz la table `chambres` de `systeme_reservation`.

/

8- Videz la table `produits_cat` de `catalogue_produits`.

``      TRUNCATE TABLE produits_cat;      ``

9- Videz la table `taches` de `suivi_projets`.

``     TRUNCATE TABLE taches;     ``

10- Videz la table `transactions` de `portefeuille_actions`.

``     TRUNCATE TABLE transactions;     ``

## Section 5: Gestion des Index (CREATE INDEX, DROP INDEX)

Cette section vous permettra de pratiquer la création et la suppression d'index pour optimiser les performances des requêtes, en comprenant leur impact sur la vitesse de lecture et d'écriture.

### Exercice 5.1: Création d'Index

**Objectif:** Créer des index sur des colonnes spécifiques pour accélérer les recherches.

**Instructions:**

1- Dans `projet_ecommerce.produits`, créez un index sur la colonne `nom_produit`.

``     CREATE UNIQUE INDEX `index_nom` ON `produits` (`nom_produit`);     ``

2- Dans `blog_personnel.articles`, créez un index sur la colonne `date_publication`.

``     CREATE UNIQUE INDEX `index_nom` ON `articles` (`date_publication`);     ``

3- Dans `gestion_stock.fournisseurs`, créez un index sur la colonne `nom_fournisseur`.

4- Dans `crm_clients.clients`, créez un index sur la colonne `email`.

5- Dans `forum_discussion.utilisateurs`, créez un index sur la colonne `pseudo`.

6- Dans `reseau_social.profils`, créez un index sur la colonne `nom_utilisateur`.

7- Dans `systeme_reservation.reservations`, créez un index sur la colonne `date_reservation`.

8- Dans `catalogue_produits.categories`, créez un index sur la colonne `nom_categorie`.

9- Dans `suivi_projets.projets`, créez un index sur la colonne `statut`.

10- Dans `portefeuille_actions.actions`, créez un index sur la colonne `symbole`.

### Exercice 5.2: Suppression d'Index

**Objectif:** Supprimer des index existants.

**Instructions:**

1- Supprimez l'index sur `nom_produit` de `projet_ecommerce.produits`.

2 Supprimez l'index sur `date_publication` de `blog_personnel.articles`.

3- Supprimez l'index sur `nom_fournisseur` de `gestion_stock.fournisseurs`.

4- Supprimez l'index sur `email` de `crm_clients.clients`.

5- Supprimez l'index sur `pseudo` de `forum_discussion.utilisateurs`.

6- Supprimez l'index sur `nom_utilisateur` de `reseau_social.profils`.

7- Supprimez l'index sur `date_reservation` de `systeme_reservation.reservations`.

8- Supprimez l'index sur `nom_categorie` de `catalogue_produits.categories`.

9- Supprimez l'index sur `statut` de `suivi_projets.projets`.

10- Supprimez l'index sur `symbole` de `portefeuille_actions.actions`.