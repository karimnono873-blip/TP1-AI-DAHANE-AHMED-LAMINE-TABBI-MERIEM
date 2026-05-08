# TP N°1 : Classification de Clients avec Random Forest 🛒🌲

**Auteur :** Dahane Ahmed Lamine  
**Enseignante :** Mme. Fergani  
**Module :** Machine Learning / Data Science  

---

## 🎯 Objectif du Projet

Ce projet vise à appliquer un algorithme d'apprentissage supervisé (**Random Forest**) pour segmenter les clients d'un centre commercial. L'objectif est de prédire la catégorie de dépense d'un client (Petit, Moyen ou Gros dépenseur) en fonction de son âge, de son revenu annuel et de son genre, afin d'optimiser les futures stratégies marketing.

Le compte-rendu complet est fourni sous la forme d'une page web interactive et stylisée (`TP1_Random_Forest_Corrige.html`), contenant la théorie, le code complet et l'interprétation des résultats.

---

## 📊 À propos du Dataset

Le jeu de données utilisé est **Mall_Customers.csv**. Il contient 200 enregistrements avec les caractéristiques suivantes :
* `CustomerID` : Identifiant unique du client.
* `Gender` : Genre (Male/Female).
* `Age` : Âge du client.
* `Annual Income (k$)` : Revenu annuel estimé.
* `Spending Score (1-100)` : Score attribué par le centre commercial basé sur le comportement d'achat.

---

## ⚙️ Méthodologie et Traitement des Données

Pour adapter ce dataset à un problème de classification supervisée, les étapes de prétraitement suivantes ont été appliquées :

1. **Création de la cible (Labellisation) :** Discrétisation du `Spending Score` en 3 catégories à l'aide de `pd.cut` :
   * **0 : Petit** (Score 0-40)
   * **1 : Moyen** (Score 40-70)
   * **2 : Gros** (Score 70-100)
2. **Prévention de la fuite de données (Data Leakage) :** Suppression de la colonne `Spending Score` (utilisée pour créer la cible) et de `CustomerID` (non pertinente pour la prédiction).
3. **Encodage :** Transformation de la variable catégorielle `Gender` en format binaire (0/1) via `pd.get_dummies`.

---

## 📈 Évaluation et Visualisation

Le modèle **RandomForestClassifier** (avec 100 arbres) a été évalué à l'aide de :
* **Accuracy Score & Rapport de Classification :** Pour mesurer la précision globale et détaillée par classe.
* **Importance des Variables (Feature Importances) :** Un graphique en barres démontrant que le revenu et l'âge sont les facteurs les plus décisifs, reléguant le genre au second plan.
* **Matrice de Confusion :** Une Heatmap (carte de chaleur) illustrant les performances de prédiction du modèle face à la réalité (Vrais Positifs vs Faux Positifs).

---

## 🚀 Structure du Dépôt

* 📄 `TP1_Random_Forest_Corrige.html` : Le compte-rendu monolithique complet (Théorie, Code, Interprétations). **(Point d'entrée principal)**
* 📁 `Mall_Customers.csv` : Le jeu de données brut.
* 📝 `README.md` : Ce fichier de documentation.

---

## 💻 Comment utiliser ce projet ?

1. **Lire le rapport :** Téléchargez le fichier `TP1_Random_Forest_Corrige.html` et ouvrez-le avec n'importe quel navigateur web (Chrome, Edge, Firefox).
2. **Exécuter le code :** Le script Python est inclus dans le rapport. Vous pouvez le copier et l'exécuter dans un environnement tel que **Google Colab** (en utilisant `files.upload()` pour importer le CSV) ou en local sur **Jupyter Notebook**.

**Prérequis Python :**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
