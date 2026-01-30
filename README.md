# Comparaison des Modèles de Classification avec et sans ACP (Wine Dataset)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![XGBoost](https://img.shields.io/badge/Library-XGBoost-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

##  Contexte du Projet

L'objectif est d'évaluer l'impact de la réduction de dimension via l'**Analyse en Composantes Principales (ACP)** sur la performance (Précision vs Temps de calcul) de différents algorithmes de machine learning.

**Problématique :** *Comment l'ACP affecte-t-elle la précision et le temps de calcul des modèles de classification supervisée sur un jeu de données à attributs multiples ?*

---

## Auteur

* **Nom :** DONGMO TCHOUMENE 
* **Prenom :** Anita Belviane
* Master 1 Data science

---

## Le Jeu de Données (Dataset)

Nous utilisons le dataset **Wine Quality** (Vins blancs) provenant du *UCI Machine Learning Repository*.
* **Type :** Classification Multi-classes / Régression (Qualité notée de 0 à 10).
* **Attributs :** 11 caractéristiques physicochimiques (Acidité, Sucre, pH, Alcool, etc.).
* **Classes :** 7 classes de qualité différentes dans ce sous-ensemble.

---

## Méthodologie

Le notebook suit les étapes suivantes :

1.  **Préparation des données :**
    * Nettoyage et chargement.
    * **Standardisation (StandardScaler)** : Indispensable avant l'ACP pour centrer et réduire les variables.
2.  **Modélisation de référence (Sans ACP) :**
    * Entraînement sur les 11 attributs originaux.
3.  **Application de l'ACP (Réduction de dimension) :**
    * Variation du nombre de composantes $k \in \{2, 3, 5, 10\}$.
    * Analyse de la variance expliquée.
4.  **Comparaison des Modèles :**
    * SVM (Support Vector Machine)
    * XGBoost
    * Arbre de Décision (Decision Tree)
    * Régression Logistique
    * Perceptron Multi-couches (MLP)

---

## Résultats Clés

L'étude comparative a permis de tirer les conclusions suivantes :

* **Meilleur compromis :** La configuration avec **$k=5$ composantes principales** offre le meilleur équilibre entre réduction de dimension (54.5% de réduction) et maintien de la performance (Variance expliquée : ~72.86%).
* **Robustesse :** Le modèle **XGBoost** s'est montré le plus robuste, maintenant de bonnes performances même après réduction de dimension.
* **Impact de l'ACP :** L'ACP est particulièrement bénéfique pour réduire le temps de calcul des modèles lourds comme le MLP, bien qu'une réduction trop forte ($k=2$) entraîne une perte significative d'information.

> *Pour plus de détails,lancez le notebook.*

---

## Installation et Utilisation

Pour reproduire ces résultats, clonez ce dépôt et installez les dépendances nécessaires.

### 1. Cloner le projet
```bash
git clone [https://github.com/AnitaBelviane/Data-Analysis.git](https://github.com/AnitaBelviane/Data-Analysis.git)
cd Data-Analysis
```

### 2. Installer les dépendances
```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost
```
### 3. Lancer le Notebook
```bash
jupyter notebook "Classification_Supervisée_ACP.ipynb"
```
