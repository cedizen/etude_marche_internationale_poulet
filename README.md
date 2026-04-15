# Étude de marché internationale pour le poulet biologique

## Présentation du projet

Ce projet vise à identifier les pays les plus pertinents pour commercialiser du poulet biologique à l’échelle internationale.  
L’analyse repose sur des données alimentaires, démographiques et de marché afin d’évaluer la dépendance aux importations, les habitudes de consommation et le potentiel commercial des pays étudiés.

Le projet est composé de **deux notebooks complémentaires** :
- un premier notebook consacré à la **préparation et au nettoyage des données** ;
- un second notebook dédié à **l’analyse exploratoire, à l’ACP, au clustering et à la recommandation finale**.

## Notebook 1 — Préparation des données

Ce premier notebook transforme les données brutes en un jeu de données propre et exploitable pour l’analyse.

### Sources utilisées
- `DisponibiliteAlimentaire_2017.csv` : données de disponibilité alimentaire mondiale en 2017.
- `Population_2000_2018.csv` : données de population par pays entre 2000 et 2018.

### Travaux réalisés
- Chargement et exploration initiale des données.
- Sélection des variables pertinentes.
- Pivot des données de disponibilité alimentaire.
- Renommage des colonnes pour plus de lisibilité.
- Conversion de la population en valeurs absolues.
- Gestion des doublons et des valeurs manquantes.
- Fusion des jeux de données sur `Pays` et `Année`.

### Filtrage et enrichissement
Le jeu de données est ensuite filtré pour ne conserver que la **viande de volailles**.  
Plusieurs indicateurs sont créés, notamment :
- le ratio d’importations ;
- la balance nette d’approvisionnement ;
- le ratio de pertes sur production.

Le fichier final produit par ce notebook est :
- `chicken_country.csv`

## Notebook 2 — Analyse et segmentation

Le second notebook exploite le fichier préparé pour identifier les marchés les plus intéressants.

### Étapes principales
- Standardisation des données avec deux approches : robuste et classique.
- Réduction de dimension via une **ACP**.
- Analyse des corrélations entre les variables d’origine et les composantes principales.
- Segmentation des pays avec **CAH** et **K-Means**.

### Résultats
Les analyses mettent en évidence plusieurs pays fortement dépendants des importations, avec une convergence claire autour de la **Belgique** comme marché particulièrement pertinent.

### Recommandation finale
La Belgique se distingue grâce à :
- sa proximité avec la France ;
- son appartenance à l’Union européenne ;
- sa forte dépendance aux importations de volaille.

## Conclusion

Ce projet propose une démarche complète, de la préparation des données jusqu’à l’identification d’un marché cible.  
La combinaison du nettoyage, de l’ACP et du clustering permet de dégager une recommandation claire et exploitable : **la Belgique apparaît comme la cible la plus pertinente pour la commercialisation de poulet biologique**.
