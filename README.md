# Projet 12 — Détection de faux billets avec Python

## Contexte et objectif
Projet de formation Data Analyst : construire une méthode de classification de billets à partir de mesures géométriques, puis appliquer le modèle retenu à de nouveaux billets.

## Démarche
1. Exploration et préparation des données ; traitement des valeurs manquantes.
2. Séparation entraînement/test et standardisation adaptée aux modèles.
3. Comparaison de K-means, régression logistique, KNN et Random Forest.
4. Sélection de la régression logistique et sauvegarde du modèle, du standardiseur et de la médiane d'imputation.
5. Application à un fichier de billets à prédire et export CSV des résultats.

## Résultats consignés dans le notebook d'analyse
Sur un jeu de test de 300 billets : **K-means : 98,67 %**, **régression logistique : 99 %**, **KNN optimisé (k=12) : 99 %**, **Random Forest : 99 %** d'exactitude. Ces résultats sont issus de l'étude ; ils n'ont pas été réexécutés pour cette publication.

## Contenu du dépôt
- `01_analyse_detection_faux_billets.ipynb` : exploration, modèles, comparaison et sauvegarde.
- `02_application_detection_faux_billets.ipynb` : prédictions sur de nouveaux billets et export.
- `requirements.txt` : bibliothèques nécessaires.
- `.gitignore` : exclusions pour les données et fichiers générés.

## Exécution locale
1. Installer Python et Jupyter ; installer les dépendances : `pip install -r requirements.txt`.
2. Placer le fichier de données d'analyse `billets.csv` dans le dossier de travail. Le premier notebook le lit avec le séparateur `;`.
3. Exécuter **dans l'ordre** les cellules de `01_analyse_detection_faux_billets.ipynb` afin de générer `modele_ONCFM.pkl`, `scaler_ONCFM.pkl` et `mediane_ONCFM.pkl`.
4. Placer `billets_production.csv` dans le même dossier (colonnes attendues : `diagonal`, `height_left`, `height_right`, `margin_low`, `margin_up`, `length`).
5. Exécuter `02_application_detection_faux_billets.ipynb`. Il produit `resultats_ONCFM.csv`.

**Attention :** les données CSV et les fichiers `.pkl` ne sont pas inclus dans cette version publique. Les fichiers `.pkl` doivent être générés localement à partir des données d'entraînement. Ne jamais charger des fichiers `.pkl` provenant d'une source non fiable.

## Limites
Les performances indiquées correspondent au jeu de test du projet et ne garantissent pas la même performance sur d'autres billets. Les fichiers de données ne sont pas distribués ici : l'exécution intégrale requiert d'en disposer légitimement. Les sorties des notebooks ont été retirées pour la publication ; le code n'a pas été réentraîné ni modifié.

## Auteur
Roger AGNEROH — Data Analyst Junior, formation OpenClassrooms.

[Portfolio](https://agnerohroger-arch.github.io/)
