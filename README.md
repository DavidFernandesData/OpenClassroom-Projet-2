Projet SQL — Dictionnaire de données, Schéma, Chargement & Requêtes




Contexte — Projet OpenClassrooms. L’objectif est de comprendre des jeux de données (contrats clients & référentiel géographique), bâtir un dictionnaire de données, concevoir un schéma relationnel, charger les données dans un SGBD, puis rédiger et documenter des requêtes SQL.

🧭 Résumé exécutif

Étape 1 — Dictionnaire de données : cartographier toutes les colonnes (source, type, contrainte, description).

Étape 2 — Schéma relationnel : normaliser, définir PK/FK/contraintes, générer le DDL (CREATE TABLE …).

Étape 3 — Mise en base : choisir SQLite/MySQL/PostgreSQL, créer les tables, charger les CSV, vérifier les volumes.

Étape 4 — Analyses 1→3 : premières requêtes SQL + copies d’écran + explication du raisonnement.

Étape 5 — Analyses 4→12 : requêtes complémentaires (top surfaces, moyennes, classements, agrégations régionales, etc.).

Étape 6 — Présentation : support (~10 slides) synthétisant méthodologie & résultats.

📦 Livrables attendus

docs/dictionnaire_donnees.xlsx — Dictionnaire complet des colonnes.

schema/schema_relationnel.jpg — Schéma relationnel (export image).

schema/ddl_create_tables.sql — DDL pour créer les tables.

db/screenshots/ — Captures prouvant la création des tables et le nombre de lignes chargées.

analyses/analyses_01_03.docx — Requêtes 1–3 + résultats (captures) + explications.

analyses/analyses_04_12.docx — Requêtes 4–12 + résultats (captures) + interprétation.

slides/presentation_projet.pptx — Support final (≤ 10 slides, ≤ 7 éléments/slide).

🔍 Données & dictionnaire

Fichiers :

contrats_clients.csv (surfaces, cotisation, type/logement, commune, département, dates, etc.)

regions_referentiel.csv (codes & libellés région, extrait data.gouv.fr)

Dictionnaire (une ligne par colonne) : Table | Colonne source | Nom standardisé | Type SQL | Contrainte | Description

Bonnes pratiques :

Types explicites (INTEGER, NUMERIC(p,s), VARCHAR(n), DATE).

Contraintes : NOT NULL, UNIQUE, CHECK, PRIMARY/FOREIGN KEY.

Cohérence des formats (dates DD/MM/YYYY → YYYY-MM-DD, encodage UTF‑8, séparateur ,/;).

🧱 Schéma relationnel & DDL

Réalisation dans SQL Power Architect (ou équivalent) :

Ajouter les colonnes manquantes, ajuster types/tailles, poser PK/FK, règles d’intégrité.

Générer schema/ddl_create_tables.sql (ANSI SQL) et vérifier l’exécution dans le SGBD choisi.

Exemples de tables (indicatif) : regions(reg_code, reg_nom), communes(commune_id, nom, dep_code, reg_code), contrats(… , commune_id).

📊 Analyses SQL

Étape 4 (1→3) : premières requêtes + captures + explication du raisonnement.

Étape 5 (4→12) :

Top 5 surfaces ;

Prix moyen de la cotisation ;

Répartition par catégories de valeur déclarée ;

Comptage des formules integral en Pays de la Loire ;

Contrats (numéro, type, formule) pour maisons, département 71 ;

Surface moyenne à Paris ;

Top 10 départements par cotisation moyenne ;

Communes avec ≥ 150 contrats ;

Contrats par région.

Chaque requête doit inclure : code SQL, capture du résultat et interprétation courte.
🔐 Données & conformité

Respect de la RGPD : anonymiser/pseudonymiser si nécessaire.

Éviter de commiter des données sensibles ou volumineuses (utiliser Git LFS si besoin).

📚 Ressources

Cours : Requêtez une base de données avec SQL (OpenClassrooms).

Outil : SQL Power Architect (installation & démo).

Bonnes pratiques : normalisation (1FN/2FN/3FN), clés et intégrité référentielle.

👤 licence


Licence : CC BY-NC-SA 4.0
