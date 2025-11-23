# MMCTR Track 2 – Multimodal CTR Prediction

Ce projet implémente une solution pour le **challenge MMCTR Track 2** ([source officielle](https://erel-mir.github.io/challenge/mmctr-track2/)).

L’objectif est de prédire le **taux de clic (CTR)** sur des items multimodaux en combinant :

- Images des items
- Textes (titres, descriptions)
- Métadonnées (catégorie, tags, année, etc.)

Le projet est structuré pour fournir une solution **modulaire, scalable et industrialisable**.

---

## Tâches du challenge

### Tâche 1 – Embedding multimodal des items
- Extraire des embeddings à partir de :
  - Images
  - Texte
  - Métadonnée
- Fusionner ces embeddings pour créer un **embedding final 128-D par item**.

### Tâche 2 – CTR Prediction
- Construire un modèle qui prédit la probabilité de clic d’un utilisateur sur un item.
- Entrées :
  - Embeddings items de la Tâche 1
  - Historique des interactions utilisateur
  - Features contextuelles (temps, device, etc.)
- Sortie :
  - Probabilité de clic entre 0 et 1
- Evaluation : **AUC sur le set de test**

---

## Fonctionnalités principales

- Pipeline complet de **prétraitement multimodal**
- Encoders séparés pour image, texte et métadonnées
- Fusion des embeddings via MLP
- Modèle CTR configurable et entraînable
- Script d’inférence pour prédictions sur des nouveaux items
- Optionnel : API FastAPI pour déploiement rapide

---

## Installation

```bash
git clone https://github.com/you66-s/multimodal-ctr-prediction
cd mmctr-project
cd mmctr-project
pip install -r requirements.txt