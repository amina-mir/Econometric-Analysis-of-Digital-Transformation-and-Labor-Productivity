 
<p align="center">
  <img src="./header_banner.svg" alt="Digital Transformation and Labor Productivity" width="100%">
</p>

<h1 align="center">Internet, Haut Débit & Productivité du Travail dans l'Union Européenne</h1>

<p align="center">
  <strong>Analyse économétrique sur données de panel | 2010–2023</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Language-R-blue?logo=r" alt="R">
  <img src="https://img.shields.io/badge/Econometrics-Panel%20Data-orange" alt="Panel Data">
  <img src="https://img.shields.io/badge/Visualization-ggplot2-orange" alt="ggplot2">
  <img src="https://img.shields.io/badge/Data-World%20Bank%20WDI-blue" alt="World Bank">
  <img src="https://img.shields.io/badge/License-MIT-green" alt="MIT License">
</p>

---

## 1. Présentation du projet

Ce projet vise à étudier la relation entre la transformation numérique et la productivité du travail au sein de 15 pays de l'Union européenne sur la période **2010–2023**.

L'objectif principal est d'analyser dans quelle mesure l'accès à Internet et le développement du haut débit fixe sont associés à l'évolution de la productivité du travail, mesurée par le PIB par personne employée.

L'étude mobilise des techniques économétriques sur données de panel afin de comparer différentes spécifications et d'évaluer la robustesse des résultats obtenus.

## 2. Problématique de recherche

**Dans quelle mesure le développement de l'accès à Internet et du haut débit fixe contribue-t-il à l'amélioration de la productivité du travail dans les pays de l'Union européenne ?**

Cette problématique permet d'examiner le rôle des infrastructures numériques dans la performance économique et de mieux comprendre les liens entre digitalisation et productivité.

## 3. Données et variables

**Source des données :** World Bank – World Development Indicators (WDI).

- **Période :** 2010–2023
- **Échantillon :** 15 pays de l'Union européenne
- **Structure :** Données de panel pays-année

### Variables principales

| Variable | Description |
|---|---|
| Productivité du travail | PIB par personne employée |
| Utilisation d'Internet | Pourcentage de la population utilisant Internet |
| Haut débit fixe | Abonnements au haut débit fixe |

Les données sont nettoyées, préparées et transformées avant l'estimation économétrique, notamment par l'utilisation de transformations logarithmiques.

## 4. Méthodologie économétrique

L'analyse repose sur une approche économétrique en données de panel.

### Étape 1 – Prétraitement des données

- Importation et exploration des données.
- Nettoyage et traitement des valeurs manquantes.
- Vérification de la cohérence des observations.
- Transformation logarithmique des variables.

### Étape 2 – Estimation des modèles

Trois modèles économétriques sont estimés et comparés :

| Modèle | Description |
|---|---|
| Pooled OLS | Modèle à effets communs |
| Fixed Effects | Modèle à effets fixes |
| Random Effects | Modèle à effets aléatoires |

### Étape 3 – Tests de spécification

Les tests suivants sont utilisés pour orienter le choix du modèle :

- **Test de Chow :** comparaison entre le modèle poolé et le modèle à effets fixes.
- **Test de Breusch-Pagan :** identification de la présence d'effets individuels aléatoires.
- **Test de Hausman :** comparaison entre les modèles à effets fixes et aléatoires.

Le modèle à effets aléatoires est retenu à l'issue de la procédure de sélection.

### Étape 4 – Tests diagnostiques

Plusieurs diagnostics sont réalisés afin d'évaluer la validité des estimations :

- Hétéroscédasticité.
- Autocorrélation des erreurs.
- Multicolinéarité à l'aide du VIF.
- Normalité des résidus à l'aide du test de Shapiro-Wilk.

### Étape 5 – Correction de la variance des erreurs

Des erreurs standards robustes de type **HAC (Arellano)** sont utilisées afin de tenir compte des problèmes d'hétéroscédasticité et d'autocorrélation.

Cette étape permet d'évaluer la robustesse de la significativité statistique des coefficients estimés.

## 5. Principaux résultats

L'analyse met en évidence un résultat économétrique important :

- L'effet estimé de l'utilisation d'Internet sur la productivité du travail est positif et statistiquement significatif au seuil de 5 % avant correction.
- Après l'application des erreurs standards robustes HAC (Arellano), cet effet perd sa significativité statistique.
- Ce résultat souligne l'importance des diagnostics économétriques et des corrections robustes dans l'interprétation des modèles de panel.

**Conclusion :**

Les résultats suggèrent une association positive entre l'utilisation d'Internet et la productivité du travail dans les estimations initiales. Toutefois, cette relation n'est pas statistiquement robuste après correction HAC.

Il est donc nécessaire de rester prudent dans l'interprétation de l'effet économique du développement numérique.

## 6. Structure du dépôt

```text
Econometric-Analysis-of-Digital-Transformation-and-Labor-Productivity/
│
├── header_banner.svg
├── panel_econometrie.R
├── panel_digital_productivity.csv
├── Digital_Transformation_Labor_Productivity_Report.pdf
├── README.md
└── LICENSE
```

| Fichier | Description |
|---|---|
| `panel_econometrie.R` | Script R contenant les estimations, tests et diagnostics |
| `panel_digital_productivity.csv` | Jeu de données de panel issu du WDI |
| `Digital_Transformation_Labor_Productivity_Report.pdf` | Rapport détaillé de l'étude |
| `header_banner.svg` | Bannière graphique du projet |
| `README.md` | Documentation du projet |
| `LICENSE` | Licence MIT |

## 7. Technologies et outils

| Technologie | Utilisation |
|---|---|
| R | Analyse statistique et économétrique |
| plm | Modélisation des données de panel |
| lmtest | Tests économétriques |
| sandwich | Erreurs standards robustes |
| car | Diagnostics et multicolinéarité (VIF) |
| stargazer | Présentation des résultats |
| ggplot2 | Visualisation des données |

## 8. Reproduire l'analyse

Pour reproduire les analyses :

**1.** Cloner le dépôt :

```bash
git clone https://github.com/amina-mir/Econometric-Analysis-of-Digital-Transformation-and-Labor-Productivity.git
```

**2.** Ouvrir le projet dans RStudio.

**3.** Installer les principaux packages :

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

**4.** Ouvrir et exécuter le script :

```r
source("panel_econometrie.R")
```

## 9. Auteur

<p align="center">
  <strong>AMINA MIR</strong>
  <br>
  Master d'Excellence en Économie Appliquée et Data Science
  <br>
  FSJES – Université Moulay Ismail
  <br>
  Meknès, Maroc
</p>

<p align="center">
  <em>Applied Economics | Econometrics | Data Science | Data Analytics</em>
</p>

---

<p align="center">
  ⭐ If you find this project interesting, feel free to star the repository!
</p>

<p align="center">
  © 2026 Amina Mir — Licensed under the MIT License.
</p>
