Analyse des pays cibles pour l’exportation de poulets

Objectif du projet

L’objectif de ce projet est de proposer une analyse des groupements de pays pouvant être ciblés pour l’exportation de poulets, à partir de données internationales en open data.
Cette première étape vise à segmenter les pays selon des critères économiques, politiques, sociaux et agricoles, afin d’identifier des marchés potentiels avant d’approfondir l’étude de marché.

Contexte

Dans un contexte de mondialisation des échanges agroalimentaires, le choix des pays cibles est stratégique.
Ce projet adopte une approche data-driven pour aider à la prise de décision, en combinant :

des données issues de la FAO (Food and Agriculture Organization),

des indicateurs de la Banque mondiale,

et une analyse multivariée (ACP + clustering).

L’ensemble de l’analyse est réalisé en autonomie, tant sur le choix des variables que sur les sources de données et les méthodes utilisées.

Problématique

Quels groupes de pays présentent des caractéristiques favorables à l’exportation de poulets, et comment peut-on les segmenter de manière objective à partir de données internationales ?

Approche méthodologique
1️1) Sélection et enrichissement des données

Point de départ : données FAO (production, consommation, commerce, indicateurs agricoles).

Utilisation de l’analyse PESTEL pour identifier de nouvelles variables pertinentes :

Politique

Économique

Social

Technologique

Environnemental

Légal

Intégration d’au minimum 8 variables issues de différentes dimensions.

Sources de données :

FAO

Banque mondiale

Données mondiales en open data

2) Préparation et nettoyage des données

Harmonisation des pays et des années

Gestion des valeurs manquantes

Normalisation / standardisation des variables

Fusion des différentes sources dans un fichier unique

Sélection d’un échantillon d’au moins :

100 pays

couvrant au minimum 60 % de la population mondiale

3) Exploration des données (EDA)

Réalisée dans un notebook dédié :

Statistiques descriptives

Analyse des distributions

Visualisations (corrélations, comparaisons entre pays)

Premiers insights globaux

4) Analyse multivariée et segmentation

Réalisée dans un notebook séparé :

 - Analyse en Composantes Principales (ACP)

Réduction de dimension

Analyse du cercle des corrélations

Projection des pays dans l’espace factoriel

Interprétation des axes principaux

- Clustering des pays

Classification Ascendante Hiérarchique (CAH)

choix du nombre de clusters

interprétation des groupes

K-means

comparaison avec la CAH

validation des clusters

Les regroupements sont réalisés à partir :

des composantes principales issues de l’ACP ou

des données brutes standardisées.

📊 Résultats attendus

Identification de groupes homogènes de pays

Mise en évidence de profils types (marchés matures, marchés émergents, marchés à risque, etc.)

Base solide pour une future étude de marché approfondie

Aide à la priorisation des pays cibles pour l’exportation

Outils et technologies

Python (pandas, numpy, matplotlib, seaborn, scikit-learn)
(ou R selon l’implémentation)

Jupyter Notebook

ACP & clustering

Git / GitHub

📂 Structure du projet
├── data/
│   ├── raw/              # Données sources (FAO, Banque mondiale…)
│   └── processed/        # Données nettoyées et fusionnées
├── notebooks/
│   ├── 01_exploration.ipynb
│   └── 02_acp_clustering.ipynb
├── visuals/
├── README.md

👤 Auteur

[Cédric BERTHEZENE]
Data Analyst en formation
Intérêt particulier pour l’analyse exploratoire, la segmentation et l’aide à la décision basée sur les données.
