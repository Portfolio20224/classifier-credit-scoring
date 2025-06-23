# 🧠 Atelier 2 – Apprentissage Supervisé avec Python

Projet réalisé dans le cadre de la 5e année du département MAM à Polytech Lyon dans le cours de *Machine Learning* encadré par **Haytham Elghazel**.

---

## 🎯 Objectif du projet

Mettre en œuvre un **pipeline complet de classification supervisée** appliqué à des données de scoring de crédit, en explorant :

- Le prétraitement des données (données manquantes, variables hétérogènes, etc.)
- Le feature engineering et la sélection de variables
- L’évaluation comparative de plusieurs algorithmes
- L’optimisation et l’automatisation via des pipelines

---

## 📁 Contenu du TP

### I. Classification supervisée sur `credit_scoring.csv`

#### 🔧 Étapes :
1. **Chargement et préparation des données**
   - Séparation en variables explicatives et cible (`status`)
   - Séparation apprentissage/test à 50%

2. **Classification avec 3 modèles :**
   - Arbre de décision CART
   - k-plus-proches-voisins (k=5)
   - Perceptron multi-couche [40, 20]

3. **Normalisation des données continues** (`StandardScaler` ou `MinMaxScaler`)

4. **Réduction de dimension** via ACP (PCA – 3 composantes)

5. **Sélection de variables pertinentes** via `RandomForestClassifier`

6. **Tuning des hyperparamètres** avec `GridSearchCV`

7. **Création d’un pipeline Scikit-learn** :
   - Normalisation → PCA (optionnelle) → Meilleur classifieur
   - Sauvegarde du modèle avec `pickle`

---

### II. Étude de données hétérogènes sur `credit.data`

#### ⚙️ Étapes :
1. **Nettoyage des données numériques**
   - Suppression des `?`
   - Binarisation de la cible

2. **Imputation des valeurs manquantes**
   - Moyenne pour les numériques
   - Valeur la plus fréquente pour les catégorielles

3. **Encodage des variables catégorielles** (`OneHotEncoder`)

4. **Normalisation + fusion finale des données**

5. **Exécution de `run_classifiers` sur ces données**

---

## 🔬 Comparaison de modèles

Comparaison de plusieurs classifieurs avec `cross_val_score` et `KFold` :

- `KNN`, `CART`, `ID3`, `MLP`, `RandomForest`, `XGBoost`, `AdaBoost`, `Bagging`, etc.
- Évaluations :
  - Accuracy, Rappel, Précision
  - AUC ROC
  - Temps d'exécution

Une fonction `run_classifiers()` est fournie pour automatiser cette étape.

---

## 🛠️ Stack technique

| Outil / Librairie   | Rôle |
|---------------------|------|
| `numpy`, `pandas`   | Manipulation des données |
| `matplotlib`        | Visualisation |
| `scikit-learn`      | Modélisation, pipelines, prétraitement |
| `xgboost`           | Modèle performant de boosting |
| `pickle`            | Sauvegarde du pipeline |

---

## ▶️ Exécution

1. Cloner le dépôt :
```bash
git clone https://github.com/ton-user/atelier-apprentissage-supervise.git
