# **Analyse des données Open Food Facts**

## **Description du projet**
Ce projet examine et analyse les données de la base Open Food Facts, une source ouverte de produits alimentaires du monde entier. L'objectif est de mieux comprendre les informations nutritionnelles, de corriger les données incomplètes, et de trouver des idées utiles pour améliorer les produits et leurs catégories.

---

## **Étapes principales**

### **Étape 1 : Préparation des données**
- **Chargement des données** :
  - Utilisation de pandas pour lire et explorer le jeu de données.
  - Affichage des premières lignes pour comprendre la structure et le contenu.

- **Nettoyage des données** :
  - Détection et gestion des données manquantes.
  - Ajustement des types de données et traitement des colonnes de date.

---

### **Étape 2 : Analyse exploratoire**

#### **Étude des principales colonnes** :
- **Colonnes avec du texte** :
  - Analyse des catégories de produits (`pnns_groups_1`) et des marques (`brands`).
- **Colonnes avec des chiffres** :
  - Étude des quantités d’énergie, de graisses, de sel, etc.

#### **Traitement des données manquantes** :
Trois méthodes principales ont été utilisées pour combler les données manquantes :
1. **Remplir avec zéro** :
   - Appliqué aux fibres (`fiber_100g`) pour les snacks salés (`salty snacks`).
2. **Remplir avec des calculs** :
   - Méthode qui estime les valeurs manquantes en utilisant les relations entre d’autres colonnes comme `energy_100g`, `fat_100g`, et `saturated-fat_100g`.
3. **Remplir avec la médiane par catégorie** :
   - Utilisé pour les colonnes comme `proteins_100g`, `sugars_100g`, et `salt_100g`, en fonction des catégories de produits (`pnns_groups_1`).

#### **Suppression des lignes inutiles** :
- Les produits sans date de création (`created_datetime`) ont été supprimés.

---

### **Étape 3 : Analyses statistiques**

#### **Analyse simple d’une colonne**
- **Objectif** : Étudier chaque colonne séparément pour mieux la comprendre.
- **Points importants** :
  - Certaines données comme `fat_100g`, `sugars_100g`, et `salt_100g` montrent une grande différence entre les produits.
  - Les marques les plus fréquentes sont Carrefour et U.
  - Les catégories les plus nombreuses sont `unknown` et `sugary snacks`.

#### **Analyse entre deux colonnes**
- **Corrélations entre chiffres** :
  - Par exemple, les graisses et l’énergie sont fortement liées.
- **Relations entre catégories** :
  - Les produits très gras ou très salés obtiennent souvent une mauvaise note nutritionnelle (`nutrition_grade_fr`).
- **Visualisations** :
  - Graphiques pour montrer les relations entre les colonnes.

#### **Analyse de plusieurs colonnes en même temps**
- **Objectif** : Réduire les colonnes à quelques axes principaux pour simplifier l’analyse.
- **Étapes** :
  - Normalisation des données et analyse des axes principaux (comme salinité, graisses, et sucres).
- **Visualisations** :
  - Graphiques pour représenter les relations et regrouper les produits similaires.

---

### **Étape 4 : Résultats et conclusions**

- **Ce qu’on a appris** :
  - Les produits avec une mauvaise note nutritionnelle (`d` ou `e`) contiennent souvent beaucoup de sel, de sucre, et de graisses.
  - Les produits bien notés (`a` ou `b`) sont riches en fibres et en céréales.
  - L’énergie des produits est fortement liée à leur contenu en graisses.

- **Recommandations** :
  - Réduire la quantité de sel et de sucre pour améliorer les notes nutritionnelles.


