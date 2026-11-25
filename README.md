# Pipeline de données Bureau&Co

Auteur : Melissa HIMENE

Ce projet nettoie le fichier des ventes et calcule le chiffre d'affaires par ville.

## Ce que fait le projet

Le pipeline lit `data/ventes.csv`, nettoie les données (doublons, lignes
invalides, noms de villes) et calcule le chiffre d'affaires par ville
et par catégorie de produit.

## Résultats

- 12 lignes lues, 9 lignes gardées.
- Chiffre d'affaires par ville : Paris 525, Lyon 450, Bordeaux 330,
  Marseille 250, Lille 240.
- Chiffre d'affaires par catégorie : Informatique 945, Mobilier 850.

## Lancer le projet

```bash
pip install -r requirements.txt
python pipeline.py
pytest -v
ruff check .
```

Les résultats sont écrits dans le dossier `output/`.

## Docker

```bash
docker build -t pipeline-data .
docker run --rm -v "$(pwd)/output:/app/output" pipeline-data
```
