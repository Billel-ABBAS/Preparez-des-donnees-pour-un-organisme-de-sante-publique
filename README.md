# Analyse des Données Open Food Facts

## **Introduction**
J'ai exploré les données d'Open Food Facts, une base de données sur les produits alimentaires, pour mieux comprendre la qualité nutritionnelle des produits. Le projet se concentre sur le nettoyage des données, l'analyse des catégories de produits, et l'étude des relations entre différents facteurs nutritionnels.

---

## **Étapes du Projet**

### **1. Nettoyage des Données**
- J'ai supprimé les doublons et les valeurs inutilisables.
- Remplacement des valeurs manquantes avec des méthodes adaptées :
  - Imputation par la médiane.
  - Techniques avancées comme `IterativeImputer` et `KNNImputer`.
- Conversion des dates en un format correct.
- Les données nettoyées ont été sauvegardées dans : `data_open_food_facts_cleaned.csv`.

### **2. Analyse des Données**

#### **A. Analyse des Caractéristiques Individuelles**
- **Statistiques descriptives** : Moyenne, médiane, asymétrie (skewness), aplatissement (kurtosis).
- **Graphiques** :
  - Histogrammes, boxplots et diagrammes en barres.
- **Observations** :
  - Les produits riches en sel, sucre ou matières grasses présentent des valeurs extrêmes.
  - Les catégories `sugary snacks` et `unknown` sont les plus représentées.

#### **B. Comparaison entre Variables**
- **Corrélations** :
  - Forte corrélation entre :
    - Énergie (`energy_100g`) et matières grasses (`fat_100g`) : 0.75.
    - Matières grasses (`fat_100g`) et saturées (`saturated-fat_100g`) : 0.73.
- **Visualisations** :
  - Matrice de corrélation et nuages de points.
- **Relation entre catégories** :
  - Le test Khi-Deux montre une relation significative entre les catégories de produits (`pnns_groups_1`) et leur note nutritionnelle (`nutrition_grade_fr`).

#### **C. Analyse Multi-Variée**
- **ACP (Analyse en Composantes Principales)** :
  - Réduction de dimensions pour comprendre les principaux facteurs influençant les produits.
  - 4 composantes principales expliquent 90% de la variance :
    - PC1 : Produits salés (`salt_100g`).
    - PC2 : Produits gras (`fat_100g` et `saturated-fat_100g`).
    - PC3 : Produits sucrés (`sugars_100g`).
    - PC4 : Produits riches en fibres (`fiber_100g`).

- **Projections des produits** :
  - Les produits mal notés (`d`, `e`) sont associés à des quantités élevées de sel, graisses ou sucres.
  - Les produits bien notés (`a`, `b`) sont riches en fibres et faibles en sel, graisses et sucres.

---

## **Principaux Résultats**
1. Les produits riches en sel, graisses et sucres obtiennent les pires notes nutritionnelles (`d`, `e`).
2. Les fruits, légumes et céréales sont bien notés (`a`, `b`).
3. Certaines catégories comme `sugary snacks` et `fat and sauces` montrent une grande diversité dans leurs profils nutritionnels.




