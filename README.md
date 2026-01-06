# Projet Machine Learning — Prédiction des prix des maisons à Boston

## Description

Ce projet met en œuvre des **modèles de régression**, dont un **réseau de neurones (MLP)**, pour prédire le prix médian des maisons à Boston à partir de 13 variables socio‑économiques et environnementales. Le travail suit une méthodologie standard de Machine Learning : exploration, prétraitement, baseline, entraînement, évaluation et discussion des limites.

---

## Auteurs

* **Chaymae Yassine**
* **Maroua Sfaoui**
* **Bassma Cheamou El Fihri**
* **Rania Bennani**

---

## Structure du projet

```
projet-boston/
│
├── Boston_Housing_NeuralNetwork.ipynb   # Notebook principal (Colab)
├── README.md                            # Documentation du projet
└── images/                              # Graphiques générés (EDA)
    ├── exploration_boston.png
    └── correlation_matrix.png
```

---

## Instructions d’exécution

1. Ouvrir **Google Colab** : [https://colab.research.google.com](https://colab.research.google.com)
2. Cliquer sur **Fichier → Importer un notebook**
3. Sélectionner le fichier `Boston_Housing_NeuralNetwork.ipynb`
4. Exécuter toutes les cellules : **Runtime → Run all**

Les résultats (métriques et graphiques) sont produits automatiquement à l’exécution du notebook.

---

## Jeu de données

* **Nom :** Boston Housing Dataset
* **Source :** [https://raw.githubusercontent.com/selva86/datasets/master/BostonHousing.csv](https://raw.githubusercontent.com/selva86/datasets/master/BostonHousing.csv)
* **Taille :** 506 échantillons, 14 variables (13 caractéristiques + 1 cible)

### Variables

| Variable | Description                                                |
| -------- | ---------------------------------------------------------- |
| crim     | Taux de criminalité par habitant                           |
| zn       | Proportion de terrains résidentiels                        |
| indus    | Proportion de commerces non‑retail                         |
| chas     | Proximité de la rivière Charles (0/1)                      |
| nox      | Concentration d’oxyde nitrique                             |
| rm       | Nombre moyen de pièces par logement                        |
| age      | Proportion de logements construits avant 1940              |
| dis      | Distance aux centres d’emploi                              |
| rad      | Accessibilité aux autoroutes                               |
| tax      | Taux de taxe foncière                                      |
| ptratio  | Ratio élèves/enseignants                                   |
| b        | Proportion de population afro‑américaine                   |
| lstat    | Pourcentage de population à faible statut socio‑économique |
| **medv** | **Prix médian des maisons (variable cible)**               |

---

## Méthodologie

### 1. Exploration des données

* Analyse des dimensions du jeu de données
* Vérification de l’absence de valeurs manquantes
* Visualisations exploratoires (distributions, corrélations)

### 2. Prétraitement

* Séparation des variables explicatives et de la cible
* **Standardisation des caractéristiques** (nécessaire pour les réseaux de neurones)
* Découpage des données en ensembles d’entraînement et de test avec une **seed fixe** pour la reproductibilité

### 3. Modèles implémentés

#### Baseline — Régression linéaire

* Modèle simple de référence
* Implémentation avec `LinearRegression` (scikit‑learn)

#### Modèle principal — Réseau de neurones (MLP)

* Implémentation avec `MLPRegressor`
* Architecture : **13 → 64 → 32 → 1**
* Fonction d’activation : ReLU
* Optimiseur : Adam

---

## Évaluation

Les modèles sont évalués sur l’ensemble de test à l’aide des métriques suivantes :

* **RMSE** (Root Mean Squared Error)
* **MAE** (Mean Absolute Error)
* **R²** (coefficient de détermination)

Les valeurs numériques exactes sont affichées directement dans le notebook lors de l’exécution.

---

## Résultats et comparaison

* La régression linéaire sert de **baseline**
* Le réseau de neurones permet de capturer des **relations non linéaires** entre les variables
* Une comparaison directe des métriques permet d’identifier le modèle le plus performant

---

## Limites du travail

1. Jeu de données de **petite taille** (506 observations)
2. Données **anciennes** (années 1970)
3. Absence de validation croisée k‑fold
4. Hyperparamètres du réseau fixés manuellement

---

## Améliorations possibles

* Mise en place d’une **validation croisée (k‑fold)**
* Optimisation des hyperparamètres via **GridSearchCV** ou Random Search
* Comparaison avec d’autres modèles (Random Forest, Gradient Boosting, XGBoost)
* Feature engineering et sélection de variables

---

## Bibliothèques utilisées

* **NumPy** : calcul numérique
* **Pandas** : manipulation des données
* **Matplotlib / Seaborn** : visualisation
* **Scikit‑learn** : modèles et métriques de Machine Learning

---

## Références

* Scikit‑learn documentation : [https://scikit-learn.org/](https://scikit-learn.org/)
* Boston Housing Dataset

