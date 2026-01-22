# Projet Algorithme – Analyse & Modélisation de Données ECG

## Description du projet

Ce projet s’inscrit dans le cadre du **Projet Algorithme** (Master Data Science / Big Data & IA).  
Il vise à construire un pipeline complet d’analyse de données ECG (électrocardiogramme), incluant :

- Exploration des données
- Méthodes non supervisées (clustering)
- Méthodes supervisées et Deep Learning
- Transformers et données textuelles médicales
- Apprentissage par renforcement
- Analyse comparative des modèles

Les travaux portent principalement sur des **signaux ECG**, avec une approche orientée **Machine Learning**, **Deep Learning** et **IA moderne**.

---

## Objectifs

- Explorer et comprendre des données ECG réelles
- Identifier des groupes de patients similaires (clustering)
- Construire des modèles de classification de risques cardiaques
- Exploiter des textes cliniques via des modèles Transformers
- Simuler une prise de décision médicale via apprentissage par renforcement
- Comparer les performances des approches classiques et avancées
- Structurer un projet reproductible et documenté

---

## Structure du dépôt

```
Projet-Algorithme/
│
├── notebooks/
│   ├── 01_exploration_non_supervisee.ipynb
│   ├── 02_supervise_deep_learning.ipynb
│   ├── 03_transformers_textes_medicaux.ipynb
│   ├── 04_reinforcement_learning.ipynb
│   └── utils.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── features.py
│   ├── models.py
│   └── evaluation.py
│
├── docs/
│   └── description_datasets.md
│
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Données

### Important

Les **datasets ne sont pas stockés directement sur GitHub** en raison de leur taille.

Ils sont mis à disposition via **SwissTransfer**.

### Lien de téléchargement des données

https://www.swisstransfer.com/d/6714f2de-4583-4b57-a677-3ea9bd3d5a7a

Après téléchargement, place les données dans un dossier local, par exemple :

```
Dataset Projet/
├── ptb-xl.csv
├── mitbih_train.csv
├── mitbih_test.csv
├── ptbdb_normal.csv
└── ptbdb_abnormal.csv
```

Ce dossier est volontairement ignoré par Git (`.gitignore`).

---

## Méthodologie

### Étape 1 – Exploration & Non-Supervisé
- Analyse exploratoire (EDA)
- Nettoyage et normalisation des signaux
- Réduction de dimension (PCA – Analyse en Composantes Principales)
- Clustering :
  - KMeans
  - DBSCAN
- Évaluation via silhouette score

### Étape 2 – Supervisé & Deep Learning
- Modèles classiques (régressions, forêts, etc.)
- Réseaux de neurones :
  - CNN (Convolutional Neural Network) pour signaux ECG
  - LSTM (Long Short-Term Memory) pour séries temporelles
- Évaluation multi-métriques :
  - Accuracy
  - F1-score
  - ROC-AUC

### Étape 3 – Transformers & Attention
- Utilisation de **ClinicalBERT** pour textes cliniques médicaux
- Tokenisation et extraction d’embeddings via HuggingFace
- Fusion multimodale :
  - Embeddings ECG (CNN)
  - Embeddings texte (BERT)
- Couche d’attention multi-têtes (Multi-Head Attention)
- Visualisation de l’attention (heatmaps, mots-clés médicaux)
- Comparaison avec une baseline TF-IDF

### Étape 4 – Apprentissage par Renforcement
- Problème simulé de décision médicale
- États : caractéristiques patient (âge, poids, etc.)
- Actions : doses de traitement
- Reward : réduction d’un risque médical simulé
- Environnement personnalisé (Gym)
- Algorithme : PPO (Proximal Policy Optimization)
- Comparaison avec des baselines simples

### Étape 5 – Discussion Critique
- Analyse des limites :
  - Biais des datasets médicaux
  - Déséquilibre des classes
  - Contraintes matérielles (mémoire GPU)
- Enjeux éthiques :
  - Données de santé et RGPD
  - Explicabilité des modèles (XAI)
- Perspectives :
  - Modèles multimodaux médicaux
  - Apprentissage par renforcement avec retour humain
  - Déploiement MLOps en environnement hospitalier

---

## ⚙️ Installation & Environnement

### Prérequis
- Python ≥ 3.9
- Environnement virtuel recommandé

### Installation

```bash
pip install -r requirements.txt
```

Principales librairies utilisées :
- numpy
- pandas
- scikit-learn
- matplotlib
- seaborn
- tensorflow
- keras
- wfdb
- transformers
- stable-baselines3
- gym

---

## Exécution

1. Télécharger les données via SwissTransfer
2. Placer les fichiers dans le dossier `Dataset Projet/`
3. Lancer les notebooks dans l’ordre :
   - `01_exploration_non_supervisee.ipynb`
   - `02_supervise_deep_learning.ipynb`
   - `03_transformers_textes_medicaux.ipynb`
   - `04_reinforcement_learning.ipynb`

---

## Organisation du travail

- Approche modulaire (notebooks + scripts Python)
- Séparation claire :
  - preprocessing
  - extraction de features
  - modèles
  - évaluation
- Travail en binôme avec répartition par étapes

---

## Licence

Projet académique – usage pédagogique uniquement.

---

## Auteurs

Raphaël COLNOT  
Clément METOIS  

Master Data Science / Big Data & Intelligence Artificielle
