# 🌐 Internet, Haut Débit & Productivité du Travail dans l'Union Européenne

### Analyse économétrique sur données de panel | 2010–2023

<p align="center">
  <img src="header_banner.svg" alt="Internet, Haut Débit et Productivité du Travail" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Language-R-blue?logo=r" alt="R">
  <img src="https://img.shields.io/badge/Analysis-Panel%20Data-0077B5" alt="Panel Data">
  <img src="https://img.shields.io/badge/Data-World%20Bank-green" alt="World Bank">
  <img src="https://img.shields.io/badge/Period-2010--2023-orange" alt="Period">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License">
</p>

<p align="center">
  <strong>Digital Transformation • Applied Economics • Econometrics • Data Science</strong>
</p>

---

## 📌 1. Présentation du projet

La transformation numérique constitue aujourd'hui un facteur majeur d'évolution des économies modernes. Le développement des infrastructures numériques, notamment l'accès à Internet et le haut débit fixe, pourrait jouer un rôle important dans l'amélioration de la productivité du travail.

Ce projet propose une **analyse économétrique sur données de panel** visant à étudier la relation entre le développement numérique et la productivité du travail dans 15 pays de l'Union européenne sur la période **2010–2023**.

L'étude s'appuie sur les données de la Banque mondiale (*World Development Indicators – WDI*) et mobilise plusieurs modèles économétriques afin d'identifier les relations entre les variables étudiées et d'évaluer la robustesse des résultats.

### 🎯 Objectif principal

Analyser dans quelle mesure l'utilisation d'Internet et le développement du haut débit fixe sont associés à l'évolution de la productivité du travail, mesurée par le PIB par personne employée.

---

## ❓ 2. Problématique de recherche

**Dans quelle mesure le développement de l'accès à Internet et du haut débit fixe contribue-t-il à l'amélioration de la productivité du travail dans les pays de l'Union européenne ?**

Cette problématique permet d'examiner le rôle des infrastructures numériques dans la performance économique et d'étudier les liens entre digitalisation et productivité.

---

## 📊 3. Données et variables

Les données proviennent de la base **World Development Indicators (WDI)** de la Banque mondiale.

| Caractéristique | Description |
|:---|:---|
| Source | World Bank – WDI |
| Échantillon | 15 pays de l'Union européenne |
| Période | 2010–2023 |
| Fréquence | Annuelle |
| Structure | Données de panel pays-année |
| Environnement | R / RStudio |

### Variables étudiées

| Variable | Description |
|:---|:---|
| Productivité du travail | PIB par personne employée |
| Utilisation d'Internet | Pourcentage de la population utilisant Internet |
| Haut débit fixe | Abonnements au haut débit fixe |

Les données font l'objet d'un travail de préparation comprenant le nettoyage, le traitement des valeurs manquantes, la vérification de la cohérence des observations et les transformations logarithmiques.

---

## ⚙️ 4. Méthodologie économétrique

L'analyse repose sur une approche en données de panel permettant de prendre en compte les différences entre les pays et leur évolution dans le temps.

### Étape 1 — Prétraitement des données

- Importation et exploration du jeu de données.
- Nettoyage et traitement des valeurs manquantes.
- Vérification de la cohérence des observations.
- Transformation logarithmique des variables.
- Préparation de la structure de panel.

### Étape 2 — Estimation des modèles

Trois spécifications économétriques sont estimées et comparées :

| Modèle | Description |
|:---|:---|
| Pooled OLS | Modèle à effets communs |
| Fixed Effects | Modèle à effets fixes |
| Random Effects | Modèle à effets aléatoires |

### Étape 3 — Tests de spécification

Plusieurs tests permettent de guider le choix du modèle :

| Test | Objectif |
|:---|:---|
| Test de Chow | Comparer le modèle poolé au modèle à effets fixes |
| Breusch–Pagan | Identifier la présence d'effets individuels |
| Hausman | Comparer les modèles à effets fixes et aléatoires |

**Résultat de la sélection :** le modèle à effets aléatoires (*Random Effects*) est retenu à l'issue de la procédure de spécification.

### Étape 4 — Tests diagnostiques

Afin d'évaluer la qualité des estimations, plusieurs diagnostics sont réalisés :

- Hétéroscédasticité.
- Autocorrélation des erreurs.
- Multicolinéarité à l'aide du VIF.
- Normalité des résidus à l'aide du test de Shapiro–Wilk.

### Étape 5 — Correction des erreurs standards

Des erreurs standards robustes de type HAC, selon l'approche Arellano, sont mobilisées pour tenir compte des problèmes potentiels d'hétéroscédasticité et d'autocorrélation.

Cette correction permet d'évaluer la robustesse de la significativité statistique des coefficients estimés.

---

## 📈 5. Principaux résultats

L'analyse met en évidence une distinction importante entre les résultats des estimations initiales et ceux obtenus après correction robuste.

### Résultat principal

| Spécification | Résultat pour l'utilisation d'Internet |
|:---|:---|
| Estimation initiale | Effet positif et significatif au seuil de 5 % |
| Après correction HAC (Arellano) | Effet positif, mais non significatif |

### 💡 Interprétation

Les estimations initiales suggèrent une association positive entre l'utilisation d'Internet et la productivité du travail.

Cependant, après application des erreurs standards robustes HAC, cet effet perd sa significativité statistique.

Ce résultat souligne l'importance des diagnostics économétriques et des corrections robustes dans l'interprétation des modèles de panel.

### Conclusion économétrique

L'étude met en évidence une relation initialement positive entre la digitalisation et la productivité du travail. Toutefois, cette relation ne demeure pas statistiquement significative après correction HAC.

**Il convient donc de rester prudent : les résultats ne permettent pas de conclure à un effet statistiquement robuste de l'utilisation d'Internet sur la productivité du travail.**

---

## 🛠️ 6. Technologies et bibliothèques

Le projet est entièrement développé sous **R**, avec des bibliothèques spécialisées en économétrie, statistiques et visualisation.

| Outil / Package | Utilisation |
|:---|:---|
| R | Langage de programmation statistique |
| plm | Modélisation économétrique en données de panel |
| lmtest | Tests statistiques et économétriques |
| sandwich | Estimation des erreurs standards robustes |
| car | Diagnostics et multicolinéarité (VIF) |
| stargazer | Présentation des résultats économétriques |
| ggplot2 | Visualisation et représentation graphique |

---

## 📁 7. Structure du dépôt

```text
Econometric-Analysis-of-Digital-Transformation-and-Labor-Productivity/
│
├── header_banner.svg
│
├── panel_econometrie.R
│
├── panel_digital_productivity.csv
│
├── Digital_Transformation_Labor_Productivity_Report.pdf
│
├── README.md
│
└── LICENSE
```

### Description des fichiers

| Fichier | Description |
|:---|:---|
| `header_banner.svg` | Bannière graphique du projet |
| `panel_econometrie.R` | Script principal des estimations et diagnostics |
| `panel_digital_productivity.csv` | Jeu de données de panel issu du WDI |
| `Digital_Transformation_Labor_Productivity_Report.pdf` | Rapport détaillé de l'étude |
| `README.md` | Documentation du projet |
| `LICENSE` | Licence MIT |

---

## 🚀 8. Reproduire l'analyse

Pour reproduire les résultats de cette étude, suivre les étapes suivantes.

### 1. Cloner le dépôt

```bash
git clone https://github.com/amina-mir/Econometric-Analysis-of-Digital-Transformation-and-Labor-Productivity.git
```

### 2. Ouvrir le projet

Ouvrir le dossier du projet dans RStudio.

### 3. Installer les packages nécessaires

```r
install.packages(c(
  "plm",
  "ggplot2",
  "lmtest",
  "sandwich",
  "car",
  "stargazer"
))
```

### 4. Exécuter le script

```r
source("panel_econometrie.R")
```

Le script contient les différentes étapes de préparation des données, d'estimation des modèles, de tests économétriques et de diagnostics.

---

## 🎓 9. Compétences mobilisées

Ce projet met en pratique plusieurs compétences en économie appliquée et en science des données :

- Économétrie appliquée et analyse de données de panel.
- Modélisation statistique et estimation des paramètres.
- Tests de spécification et diagnostics économétriques.
- Analyse de la transformation numérique.
- Traitement et préparation de données économiques.
- Programmation statistique avec R.
- Visualisation et interprétation des résultats.
- Évaluation de la robustesse des estimations.

---

## 👩‍💻 10. Auteur

**AMINA MIR**

Master d'Excellence en Économie Appliquée et Data Science

FSJES – Université Moulay Ismail  
Meknès, Maroc

**Domaines d'intérêt :**

`Applied Economics` · `Econometrics` · `Data Science` · `Data Analytics` · `Digital Transformation`

---

## 📜 11. Licence

Ce projet est distribué sous licence **MIT**.

Vous êtes libre d'utiliser, de modifier et de distribuer ce travail conformément aux conditions de cette licence.

Voir le fichier [LICENSE](LICENSE) pour plus d'informations.

---

<p align="center">
  ⭐ <strong>Si ce projet vous intéresse, n'hésitez pas à laisser une étoile au dépôt GitHub !</strong>
</p>

<p align="center">
  <em>Étudier les données, comprendre les relations économiques et mesurer les effets de la transformation numérique.</em>
</p>

<p align="center">
  © 2026 Amina Mir — MIT License
</p>
