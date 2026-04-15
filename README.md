# Étude de marché internationale : Préparation des données pour le poulet biologique

## Présentation du projet

Ce projet vise à réaliser une étude de marché internationale pour une entreprise souhaitant commercialiser du poulet biologique à l'échelle mondiale. L'objectif global est d'identifier les pays les plus pertinents pour cette commercialisation, en se basant sur une analyse approfondie des habitudes alimentaires, des politiques agricoles et des dynamiques de marché.

## Rôle de ce Notebook

Ce notebook est la **première étape cruciale** du projet. Il se concentre exclusivement sur la **préparation et le nettoyage des données** nécessaires à l'analyse décisionnelle.

## Sources de Données

Les données utilisées dans ce notebook proviennent de deux fichiers CSV principaux :

*   `DisponibiliteAlimentaire_2017.csv`: Contient les informations détaillées sur la disponibilité alimentaire mondiale pour l'année 2017 (production, importations, exportations, pertes, etc., par produit et par pays).
*   `Population_2000_2018.csv`: Fournit les données de population par pays de 2000 à 2018.

## Étapes Clés Réalisées

1.  **Exploration Initiale et Chargement des Données**:
    *   Chargement des fichiers CSV dans des DataFrames Pandas.
    *   Vérification des structures et des types de données (`.info()`, `.head()`).
2.  **Nettoyage et Transformation des Données**:
    *   Sélection des colonnes pertinentes pour chaque DataFrame.
    *   Pivotage du DataFrame `df_dispo_alimentaire` pour organiser les 'Éléments' comme des colonnes, facilitant l'analyse.
    *   Renommage des colonnes pour une meilleure lisibilité (`Zone` en `Pays`, `Valeur` en `Population totale`).
    *   Conversion de la population en valeurs absolues (multiplication par 1000).
    *   Vérification et gestion des doublons.
3.  **Fusion et Consolidation**:
    *   Combinaison des DataFrames `df_population` et `df_dispo_alimentaire_pivot` sur les colonnes `Pays` et `Année` pour créer un jeu de données unifié.
4.  **Filtrage pour le Produit Cible**:
    *   Extraction des données spécifiquement relatives à la **'Viande de Volailles'**.
    *   Sélection des métriques pertinentes pour l'étude de marché.
5.  **Gestion des Valeurs Manquantes**:
    *   Identification des valeurs manquantes (`.isna().sum()`).
    *   Remplacement des valeurs manquantes par `0` pour des variables comme les importations, exportations, production, pertes et traitement, partant de l'hypothèse qu'une absence de donnée signifie une absence d'activité pour éviter de réduire drastiquement l'échantillon de pays.
6.  **Feature Engineering (Création d'Indicateurs)**:
    *   Calcul du **Ratio d'importations** (`Importations / (Importations + Production - Exportations - Pertes)`).
    *   Calcul de la **Balance nette d'approvisionnement** (`Importations - (Exportations - Production)`).
    *   Calcul du **Ratio de pertes sur production** (`Pertes / Production`).
    *   Application de logiques métier pour gérer les divisions par zéro et les valeurs non positives dans les calculs de ratios.
7.  **Validation de la Couverture**:
    *   Vérification que le jeu de données final couvre un nombre suffisant de pays et un pourcentage pertinent de la population mondiale (critères: >100 pays et >60% de la population mondiale).

## Fichier de Sortie

Le résultat de ce notebook est un fichier CSV nommé `chicken_country.csv`, contenant le jeu de données propre, enrichi et prêt à l'emploi pour les analyses ultérieures.

## Prochaine Étape

Ce fichier `chicken_country.csv` sera utilisé dans un second notebook pour réaliser :

*   Une **Analyse en Composantes Principales (ACP)** afin de réduire la dimensionnalité et d'identifier les variables explicatives clés.
*   Une **segmentation des pays via l'algorithme KMeans** pour regrouper les pays ayant des profils similaires et identifier les marchés potentiels.
