# 🌐 Internet, Haut Débit & Productivité du Travail dans l'Union Européenne

### Analyse économétrique sur données de panel | 2010–2023

<p align="center">
  <img src="header_banner.png" alt="Internet, Haut Débit et Productivité du Travail" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Language-R-blue?logo=r" alt="R">
  <img src="https://img.shields.io/badge/Method-Panel%20Data-0077B5" alt="Panel Data">
  <img src="https://img.shields.io/badge/Data-World%20Bank-green" alt="World Bank">
  <img src="https://img.shields.io/badge/Period-2010--2023-orange" alt="Period">
  <img src="https://img.shields.io/badge/Countries-15-blue" alt="15 Countries">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License">
</p>

<p align="center">
  <strong>Applied Economics | Econometrics | Data Science | Digital Transformation</strong>
</p>

---

## 📌 1. Présentation du projet

La transformation numérique constitue aujourd'hui un facteur essentiel de l'évolution des économies modernes. Le développement des infrastructures numériques, notamment l'accès à Internet et le haut débit fixe, pourrait contribuer à améliorer l'efficacité productive et la performance économique.

Ce projet propose une **analyse économétrique sur données de panel** visant à étudier la relation entre le développement numérique et la productivité du travail dans 15 pays de l'Union européenne sur la période **2010–2023**.

L'étude exploite les données de la Banque mondiale (*World Development Indicators – WDI*) et mobilise plusieurs modèles économétriques afin d'examiner les relations entre les variables étudiées et d'évaluer la robustesse des résultats obtenus.

### 🎯 Objectif principal

Analyser dans quelle mesure l'utilisation d'Internet et le développement du haut débit fixe sont associés à l'évolution de la productivité du travail, mesurée par le PIB par personne employée.

---

## ❓ 2. Problématique de recherche

**Dans quelle mesure le développement de l'accès à Internet et du haut débit fixe contribue-t-il à l'amélioration de la productivité du travail dans les pays de l'Union européenne ?**

Cette problématique permet d'examiner le rôle des infrastructures numériques dans la performance économique et de mieux comprendre les liens entre digitalisation et productivité.

---

## 📊 3. Données et variables

Les données utilisées dans cette étude proviennent de la base **World Development Indicators (WDI)** de la Banque mondiale.

### Caractéristiques de l'échantillon

| Caractéristique | Description |
|:---|:---|
| Source | World Bank – World Development Indicators |
| Échantillon | 15 pays de l'Union européenne |
| Période | 2010–2023 |
| Fréquence | Annuelle |
| Structure | Données de panel pays-année |
| Environnement statistique | R / RStudio |

### Variables principales

| Variable | Description |
|:---|:---|
| Productivité du travail | PIB par personne employée |
| Utilisation d'Internet | Pourcentage de la population utilisant Internet |
| Haut débit fixe | Abonnements au haut débit fixe |

### Préparation des données

Avant les estimations économétriques, plusieurs opérations de préparation sont effectuées :

- Importation et exploration des données.
- Nettoyage et traitement des valeurs manquantes.
- Vérification de la cohérence des observations.
- Préparation de la structure de panel.
- Transformation logarithmique des variables.

---

## ⚙️ 4. Méthodologie économétrique

L'analyse repose sur une approche économétrique en données de panel permettant de tenir compte des différences entre les pays et de leur évolution dans le temps.

### Étape 1 — Prétraitement des données

- Importation du jeu de données.
- Exploration statistique des variables.
- Nettoyage et traitement des valeurs manquantes.
- Vérification de la cohérence des observations.
- Transformation logarithmique des variables.

### Étape 2 — Estimation des modèles

Trois modèles économétriques sont estimés et comparés :

| Modèle | Description |
|:---|:---|
| Pooled OLS | Modèle à effets communs |
| Fixed Effects | Modèle à effets fixes |
| Random Effects | Modèle à effets aléatoires |

### Étape 3 — Tests de spécification

Plusieurs tests économétriques sont mobilisés pour orienter le choix du modèle approprié.

| Test | Objectif |
|:---|:---|
| Test de Chow | Comparaison entre le modèle poolé et le modèle à effets fixes |
| Breusch–Pagan | Identification de la présence d'effets individuels aléatoires |
| Hausman | Comparaison entre les modèles à effets fixes et aléatoires |

**Résultat de la sélection :** le modèle à effets aléatoires (*Random Effects*) est retenu à l'issue de la procédure de sélection.

### Étape 4 — Tests diagnostiques

Afin d'évaluer la validité des estimations, plusieurs diagnostics sont réalisés :

- **Hétéroscédasticité :** vérification de la constance de la variance des erreurs.
- **Autocorrélation :** analyse de la dépendance temporelle des erreurs.
- **Multicolinéarité :** analyse à l'aide du Variance Inflation Factor (VIF).
- **Normalité des résidus :** test de Shapiro–Wilk.

### Étape 5 — Correction des erreurs standards

Des erreurs standards robustes de type **HAC (Arellano)** sont utilisées afin de tenir compte des problèmes potentiels d'hétéroscédasticité et d'autocorrélation.

Cette correction permet de vérifier si la significativité statistique des coefficients estimés demeure robuste après ajustement de la variance des erreurs.

---

## 📈 5. Principaux résultats

L'analyse met en évidence une différence importante entre les estimations initiales et les résultats obtenus après correction des erreurs standards.

### Résultat concernant l'utilisation d'Internet

| Spécification | Résultat |
|:---|:---|
| Estimation initiale | Effet positif et statistiquement significatif au seuil de 5 % |
| Après correction HAC (Arellano) | Effet positif, mais statistiquement non significatif |

### 🔍 Interprétation économétrique

Les premières estimations suggèrent une association positive entre l'utilisation d'Internet et la productivité du travail.

Toutefois, après application des erreurs standards robustes HAC selon l'approche Arellano, cet effet perd sa significativité statistique.

Ce résultat souligne l'importance des tests diagnostiques et des corrections robustes dans l'analyse économétrique des données de panel.

### 💡 Conclusion principale

Les résultats initiaux suggèrent que le développement de l'utilisation d'Internet est positivement associé à la productivité du travail dans les pays étudiés.

Cependant, cette relation ne demeure pas statistiquement significative après correction HAC.

**L'étude invite donc à interpréter avec prudence le lien entre transformation numérique et productivité du travail. Les estimations obtenues ne permettent pas d'établir un effet statistiquement robuste de l'utilisation d'Internet.**

---

## 🛠️ 6. Technologies et bibliothèques utilisées

Le projet est réalisé sous **R**, avec plusieurs bibliothèques dédiées à l'économétrie, aux statistiques et à la visualisation des données.

| Technologie / Package | Utilisation |
|:---|:---|
| R | Programmation statistique et analyse des données |
| plm | Estimation des modèles économétriques sur données de panel |
| lmtest | Tests statistiques et économétriques |
| sandwich | Calcul des erreurs standards robustes |
| car | Diagnostics économétriques et calcul du VIF |
| stargazer | Présentation des résultats économétriques |
| ggplot2 | Visualisation graphique des données |

### Environnement de développement

- R
- RStudio
- Git
- GitHub

---

## 📁 7. Structure du dépôt GitHub

```text
Econometric-Analysis-of-Digital-Transformation-and-Labor-Productivity/
│
├── header_banner.png
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
| `header_banner.png` | Bannière graphique du projet |
| `panel_econometrie.R` | Script R contenant les estimations, tests et diagnostics |
| `panel_digital_productivity.csv` | Jeu de données de panel issu du WDI |
| `Digital_Transformation_Labor_Productivity_Report.pdf` | Rapport détaillé de l'étude économétrique |
| `README.md` | Documentation et présentation du projet |
| `LICENSE` | Licence MIT |

---

## 🚀 8. Reproduire l'analyse

L'ensemble de l'analyse peut être reproduit à partir du script R fourni dans le dépôt.

### 1. Cloner le dépôt

```bash
git clone https://github.com/amina-mir/Econometric-Analysis-of-Digital-Transformation-and-Labor-Productivity.git
```

### 2. Accéder au dossier

```bash
cd Econometric-Analysis-of-Digital-Transformation-and-Labor-Productivity
```

### 3. Ouvrir le projet dans RStudio

Ouvrir le dossier contenant les fichiers du projet dans RStudio.

### 4. Installer les packages nécessaires

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

### 5. Charger et exécuter le script

```r
source("panel_econometrie.R")
```

Le script permet de reproduire les étapes de préparation des données, les estimations économétriques, les tests de spécification et les diagnostics.

---

## 🎓 9. Compétences mobilisées

Ce projet met en pratique plusieurs compétences en économie appliquée, économétrie et science des données.

**Économétrie et statistiques**
- Modélisation économétrique sur données de panel.
- Estimation des modèles Pooled OLS, Fixed Effects et Random Effects.
- Tests de spécification et diagnostics économétriques.
- Estimation avec erreurs standards robustes.
- Interprétation et évaluation de la robustesse des résultats.

**Data Science et analyse des données**
- Collecte et préparation des données économiques.
- Nettoyage et transformation des données.
- Analyse exploratoire des données.
- Visualisation et interprétation statistique.
- Programmation avec R.

**Économie appliquée**
- Analyse de la transformation numérique.
- Étude de la productivité du travail.
- Exploitation des indicateurs macroéconomiques internationaux.
- Analyse comparative entre pays européens.

---

## 👩‍💻 10. Auteur

<p align="center">
  <strong>AMINA MIR</strong><br>
  Master d'Excellence en Économie Appliquée et Data Science<br>
  FSJES – Université Moulay Ismail<br>
  Meknès, Maroc
</p>

<p align="center">
  <strong>Applied Economics | Econometrics | Data Science | Data Analytics</strong>
</p>

---

## 📜 11. Licence

Ce projet est distribué sous la **licence MIT**.

Vous êtes libre de consulter, utiliser, modifier et distribuer ce projet conformément aux conditions de cette licence.

Pour plus d'informations, veuillez consulter le fichier [LICENSE](LICENSE).

---

<p align="center">
  ⭐ <strong>Vous trouvez ce projet intéressant ? N'hésitez pas à laisser une étoile au dépôt GitHub !</strong>
</p>

<p align="center">
  <em>Comprendre la transformation numérique à travers l'analyse économique et les méthodes économétriques.</em>
</p>

<p align="center">
  © 2026 Amina Mir — Licensed under the MIT License
</p>
