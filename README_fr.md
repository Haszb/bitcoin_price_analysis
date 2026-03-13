# Analyse du Prix du Bitcoin

Un projet de machine learning pour analyser et prédire les mouvements de prix du Bitcoin (BTC/USDT) en utilisant des réseaux de neurones récurrents (RNN).

## Aperçu

Ce projet explore si les données historiques de prix du Bitcoin contiennent un signal prédictif exploitable. Il emploie des **réseaux de neurones récurrents (RNN)** avec une approche auto-régressive multi-étapes qui simule les conditions de trading réelles, où les modèles doivent s'appuyer sur leurs propres prédictions précédentes plutôt que sur les valeurs observées réelles.

## Fonctionnalités

- **Analyse Exploratoire des Données (EDA)** - Analyse statistique et visualisation des données de prix du Bitcoin
- **Prédiction de Séries Temporelles Multi-étapes** - Modèles basés sur les RNN pour la prévision des prix futurs
- **Prédiction Auto-régressive** - Modèles qui prédisent en utilisant leurs propres sorties précédentes
- **Intégration MLflow** - Suivi des expériences et gestion des modèles
- **Dashboards Interactifs** - Visualisations Plotly/Dash pour les résultats des modèles

## Structure du Projet

```
bitcoin_price_analysis/
├── data/
│   ├── dataset/          # Données brutes BTC/USDT horaires
│   └── 2026_01_15/       # Instantanés de données traitées
├── version_english/      # Notebooks et documentation en anglais
├── version_français/     # Notebooks et documentation en français
├── mlruns/               # Données de suivi d'expériences MLflow
├── requirements.txt      # Dépendances Python
├── README.md             # Documentation en anglais
└── README_fr.md          # Documentation en français
```

## Démarrage Rapide

### Prérequis

- Python 3.10+
- pip

### Installation

1. Cloner le dépôt :
   ```bash
   git clone <repository-url>
   cd bitcoin_price_analysis
   ```

2. Créer et activer un environnement virtuel :
   ```bash
   python -m venv .venv
   .venv\Scripts\activate  # Windows
   # ou
   source .venv/bin/activate  # Unix/macOS
   ```

3. Installer les dépendances :
   ```bash
   pip install -r requirements.txt
   ```

4. Installer ipykernel pour le support des notebooks Jupyter :
   ```bash
   python -m ipykernel install --user --name=bitcoin_price_analysis --display-name "Python (bitcoin_price_analysis)"
   ```

### Utilisation

1. **Analyse Exploratoire des Données** : Ouvrir `version_français/EDA.ipynb` dans Jupyter Notebook
2. **Modélisation ML** : Ouvrir `version_français/ML modelization.ipynb` dans Jupyter Notebook
3. **Voir les Résultats MLflow** :
   ```bash
   # Démarrer le serveur de suivi MLflow
   mlflow ui --host 127.0.0.1 --port 5000
   ```
   Puis ouvrir votre navigateur à `http://localhost:5000` pour accéder à l'interface MLflow et voir les expériences, métriques et artefacts de modèles.

4. **Lancer le Dashboard de Prédiction** :
   Exécuter le serveur du dashboard depuis le notebook de 
   en éxécutant la cellule finale pour démarrer le serveur Dash. Puis ouvrir votre navigateur à `http://127.0.0.1:8050/` pour voir les courbes de prédiction interactives et l'analyse grid.

## Données

Le projet utilise des données de prix BTC/USDT horaires de Binance :

- **Fichier** : `data/dataset/BTCUSDT_1h.csv`
- **Format** : CSV avec données OHLCV (Open, High, Low, Close, Volume)

## Approche Machine Learning

### Architecture du Modèle

- **Type** : Réseaux de Neurones Récurrents (RNN)
- **Stratégie** : Prédiction multi-étapes auto-régressive
- **Contrainte** : Les modèles utilisent uniquement leurs propres prédictions précédentes pour les estimations futures

## Documentation

| Document | Description |
|----------|-------------|
| Article 1 - Introduction du Projet | Aperçu des objectifs et de la méthodologie du projet |
| Article 4 - Une Nouvelle Direction | Évolution de l'approche de recherche |

## Stack Technique

- **Python** - Langage de programmation principal
- **TensorFlow/Keras** - Framework de deep learning
- **scikit-learn** - Utilitaires de machine learning
- **MLflow** - Suivi des expériences
- **Plotly/Dash** - Visualisations interactives
- **Pandas/NumPy** - Manipulation de données
- **Jupyter** - Développement interactif

## Notebooks

- **EDA.ipynb** - Analyse Exploratoire des Données
- **ML modelization.ipynb** - Entraînement et évaluation des modèles

## Contribuer

1. Forker le dépôt
2. Créer une branche de fonctionnalité
3. Apporter vos modifications
4. Soumettre une pull request

## Licence

Ce projet est à but de recherche et d'éducation.

## Avertissement

Ce projet est destiné **uniquement à des fins éducatives et de recherche**. Il n'est pas destiné au trading en direct ni ne constitue un conseil financier. Le trading de cryptomonnaies comporte un risque de perte significatif.

---

*Dernière mise à jour : Mars 2026*
