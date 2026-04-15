# Projet: Analyse des ventes d'une librairie en ligne

## Introduction
Ce projet vise à explorer et analyser les données de ventes d'une librairie en ligne. L'objectif est de comprendre les tendances de ventes, les profils clients, et les corrélations entre différentes variables afin d'identifier des opportunités d'amélioration et de prise de décision.

## Jeux de données
Le projet utilise trois jeux de données:
- 'customers.csv': Contient les informations sur les clients (ID, sexe, année de naissance).
- 'products.csv': Contient les informations sur les produits (ID, prix, catégorie).
- 'Transactions.csv': Contient les détails de chaque transaction (ID produit, date, ID session, ID client).

## Nettoyage et préparation des données
Des étapes de nettoyage et de préparation ont été effectuées pour assurer la qualité des données:
- **'customers.csv'**: Vérification des identifiants uniques et du formatage. Ajout d'une colonne 'age'.
- **'Transactions.csv'**: Suppression des lignes avec des identifiants dupliqués ou nuls. Conversion de la colonne 'date' au format datetime. Ajout de colonnes 'day', 'year', 'month' pour l'analyse temporelle.
- **'products.csv'**: Vérification des identifiants uniques et des valeurs nulles. Renommage de la colonne 'categ' en 'category' et conversion en type catégoriel.
- **Fusion des jeux de données**: Les trois DataFrames ont été fusionnés en un seul DataFrame ('customers_transactions_products_df') pour faciliter l'analyse.

## Analyse du chiffre d'affaires

### Chiffre d'affaires total
Le chiffre d'affaires total généré est de **12 009 918,53 €**.

### Évolution du chiffre d'affaires dans le temps
L'analyse de l'évolution du chiffre d'affaires par mois et par année a montré une diminution significative des ventes, particulièrement en 2023. Une décomposition saisonnière a révélé une tendance à la baisse constante et une forte saisonnalité annuelle.

### Chiffre d'affaires par catégorie
Le chiffre d'affaires a été analysé par catégorie de produits, révélant la contribution de chaque catégorie aux ventes globales et son évolution au fil du temps. La catégorie 2, par exemple, a montré une chute importante des ventes en 2023.

### Métriques clés par mois et par an
Plusieurs métriques ont été calculées et agrégées par mois et par année pour un suivi détaillé:
- Nombre de clients acquis
- Nombre de transactions
- Nombre de produits vendus
- Prix unitaire moyen vendu
- Ventes par client
- Chiffre d'affaires par client

## Meilleures et pires ventes

Les 10 meilleures et les 10 pires références en termes de chiffre d'affaires ont été identifiées. La répartition du chiffre d'affaires par catégorie a également été visualisée, montrant la contribution de chaque catégorie au total des ventes.

## Profils clients

### Répartition de la clientèle
- **Répartition par genre**: Les clients sont répartis de manière presque égale entre les hommes et les femmes.
- **Répartition par âge**: La distribution des âges des clients a été analysée.

### Courbe de Lorenz et identification des clients B2B/B2C
L'analyse de la courbe de Lorenz a permis de mettre en évidence la concentration du chiffre d'affaires. Il a été constaté que **80% du chiffre d'affaires est généré par environ 50,35% de la clientèle totale**.

Sur la base de cette analyse, les clients ont été segmentés en deux catégories:
- **Professionnels (B2B)**: Les clients qui génèrent les revenus les plus importants.
- **Particuliers (B2C)**: Les autres clients.

L'évolution du nombre de clients par type (B2B/B2C) a été étudiée, ainsi que la répartition du chiffre d'affaires par catégorie pour les clients professionnels.

## Corrélations

Des tests statistiques ont été effectués pour identifier les corrélations entre différentes variables, en utilisant un seuil de signification (alpha) de 0.05.

### Genre et catégorie
- **Hypothèse**: Le genre et la catégorie de produits sont dépendants.
- **Résultat**: L'hypothèse nulle d'indépendance a été rejetée (p-value < alpha), indiquant une dépendance entre le genre et la catégorie des produits achetés.

### Âge et montant total des achats
- **Hypothèse**: Il existe une corrélation entre l'âge et le montant total des achats.
- **Résultat**: Une corrélation négative significative a été trouvée (Coefficient de Pearson: -0.83, p-value < alpha), indiquant que le montant total des achats diminue avec l'âge.

### Âge et fréquence d'achats
- **Hypothèse**: Il existe une corrélation entre l'âge et la fréquence d'achat.
- **Résultat**: Une corrélation négative significative a été trouvée (Coefficient de Pearson: -0.58, p-value < alpha), indiquant que la fréquence d'achats diminue avec l'âge.

### Âge et achats moyens
- **Hypothèse**: Il existe une corrélation entre l'âge et les achats moyens.
- **Résultat**: Une corrélation négative significative a été trouvée (Coefficient de Pearson: -0.54, p-value < alpha), suggérant que le montant moyen par achat diminue avec l'âge.

### Âge et catégorie
- **Hypothèse**: Il existe au moins une variation d'âge entre les catégories.
- **Résultat**: Les tests ANOVA et Kruskal (p-value < alpha) ont rejeté l'hypothèse nulle, confirmant qu'il existe des différences significatives dans la distribution des âges entre les différentes catégories de produits. La catégorie 2, en particulier, semble être principalement achetée par des personnes plus jeunes (20-35 ans).

## Technologies utilisées
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Statsmodels
- SciPy

## Installation des librairies
Lancer dans le terminal de commande 'pip install -r requirements.txt' pour installer toutes les librairies requis pour le projet.
