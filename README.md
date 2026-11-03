<p align="center">
  <img src="header_banner.svg" alt="Digital Transformation & Labor Productivity — UE, 2010–2023" width="100%" />
</p>

<h1 align="center">Internet, haut débit et productivité du travail dans l'Union européenne (2010–2023)</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Langage-R-276DC3?style=for-the-badge&logo=r&logoColor=white" alt="R" />
  <img src="https://img.shields.io/badge/Panel-plm-1F6FEB?style=for-the-badge" alt="plm" />
  <img src="https://img.shields.io/badge/Visualisation-ggplot2-E67E22?style=for-the-badge" alt="ggplot2" />
  <img src="https://img.shields.io/badge/Données-World%20Bank%20WDI-2E8B57?style=for-the-badge" alt="World Bank WDI" />
  <img src="https://img.shields.io/badge/Licence-MIT-green?style=for-the-badge" alt="MIT License" />
</p>

<p align="center">
  <strong>Une étude économétrique en données de panel sur 15 pays de l'UE, de 2010 à 2023.</strong>
</p>

---

## 🎯 Objectif du projet

Ce projet étudie le lien entre la transformation numérique et la productivité du travail dans 15 pays de l'Union européenne sur la période **2010–2023**.

L'objectif est d'évaluer dans quelle mesure l'accès à Internet et le développement du haut débit fixe sont associés à la productivité du travail, mesurée par le **PIB par personne employée**.

**Question de recherche :** l'amélioration de la connectivité numérique est-elle associée à une productivité du travail plus élevée dans les pays étudiés ?

## 📊 Données et variables

- **Source :** [World Development Indicators (WDI) — Banque mondiale](https://databank.worldbank.org/source/world-development-indicators).
- **Périmètre :** 15 pays de l'Union européenne.
- **Période :** 2010–2023.

| Variable | Mesure / description |
|---|---|
| Productivité du travail | PIB par personne employée |
| Accès à Internet | Pourcentage de la population utilisant Internet |
| Haut débit fixe | Abonnements au haut débit fixe |

Les données sont préparées avant estimation : vérification et nettoyage, traitement des valeurs manquantes et transformation logarithmique des variables retenues.

## 🧪 Méthodologie économétrique

L'analyse repose sur trois spécifications classiques pour les données de panel :

1. **MCO poolés (Pooled OLS)** — modèle de référence sans effets individuels spécifiques.
2. **Effets fixes (Fixed Effects)** — contrôle de l'hétérogénéité individuelle invariante dans le temps.
3. **Effets aléatoires (Random Effects)** — prise en compte des composantes individuelles aléatoires.

### Tests de spécification et de sélection

| Test | Objectif |
|---|---|
| Test de Chow / Fisher | Comparer le modèle poolé au modèle à effets fixes |
| Test de Breusch–Pagan (LM) | Évaluer la pertinence des effets aléatoires par rapport au modèle poolé |
| Test de Hausman | Comparer les estimateurs à effets fixes et à effets aléatoires |

Selon les résultats consignés dans le projet, **le modèle à effets aléatoires est retenu**.

### Diagnostics et robustesse

Les diagnostics portent sur :

- l'hétéroscédasticité ;
- l'autocorrélation des erreurs ;
- la multicolinéarité, examinée à l'aide du VIF ;
- la normalité des résidus, notamment avec le test de Shapiro–Wilk.

Des **erreurs standards robustes de type HAC (Arellano)** sont ensuite utilisées afin d'obtenir une inférence plus robuste face aux problèmes détectés.

## 🔎 Résultat principal

L'estimation initiale met en évidence un **effet positif et statistiquement significatif d'Internet au seuil de 5 %** sur la productivité du travail.

Cependant, après l'application de la correction robuste HAC (Arellano), cet effet **perd sa significativité statistique**.

### Interprétation

Ce résultat invite à la prudence : la relation positive observée dans le modèle initial n'est pas suffisamment robuste pour conclure à un effet statistiquement significatif après correction. Il illustre l'importance des diagnostics et des erreurs standards robustes dans l'analyse économétrique des données de panel.

> **À retenir :** le signe estimé est positif, mais la significativité statistique de l'effet d'Internet ne résiste pas à la correction HAC.

## 🗂️ Structure du dépôt

```text
.
├── header_banner.svg
├── panel_econometrie.R
├── panel_digital_productivity.csv
├── Digital_Transformation_Labor_Productivity_Report.pdf
├── LICENSE
└── README.md
```

| Fichier | Description |
|---|---|
| `panel_econometrie.R` | Script R : préparation des données, estimations, tests et diagnostics. |
| `panel_digital_productivity.csv` | Jeu de données de panel issu des WDI de la Banque mondiale. |
| `Digital_Transformation_Labor_Productivity_Report.pdf` | Rapport détaillé présentant les résultats et leur interprétation. |
| `header_banner.svg` | Bannière du dépôt GitHub. |
| `LICENSE` | Texte de la licence MIT. |

## ⚙️ Installation et exécution

### Prérequis

- **R 4.3.1** ou version ultérieure.
- Les packages R utilisés dans l'analyse : `plm`, `lmtest`, `sandwich`, `car`, `stargazer` et `ggplot2`.

### Installer les packages

```r
packages <- c("plm", "lmtest", "sandwich", "car", "stargazer", "ggplot2")

missing_packages <- packages[!packages %in% rownames(installed.packages())]
if (length(missing_packages) > 0) {
  install.packages(missing_packages)
}
```

### Lancer l'analyse

Après avoir placé le script et le fichier CSV dans le même dossier de travail, exécuter :

```r
source("panel_econometrie.R")
```

Le script contient les étapes de l'analyse économétrique. Pour les détails des résultats et de leur interprétation, consulter le rapport PDF inclus dans le dépôt.

## 🧰 Outils et technologies

- **R** — traitement et analyse statistique ;
- **plm** — estimation des modèles de données de panel ;
- **lmtest** et **sandwich** — tests et inférence robuste ;
- **car** — diagnostics de multicolinéarité ;
- **stargazer** — présentation des résultats économétriques ;
- **ggplot2** — visualisation des données et des résultats.

## 👩‍💻 À propos de l'auteure

**Amina Mir**  
Master d'Excellence en Économie Appliquée et Data Science  
FSJES — Université Moulay Ismaïl, Meknès, Maroc

Ce travail s'inscrit dans une démarche de recherche appliquée mobilisant l'économétrie, la science des données et l'exploitation de données économiques publiques.

## 📚 Référence des données

Banque mondiale, *World Development Indicators (WDI)* : [https://databank.worldbank.org/source/world-development-indicators](https://databank.worldbank.org/source/world-development-indicators).

## 📄 Licence

Ce projet est distribué sous licence **MIT**. Consultez le fichier [`LICENSE`](LICENSE) pour les conditions applicables.

---

<p align="center">
  <sub>Réalisé avec R · Économétrie appliquée · Données de panel · 2010–2023</sub>
</p>
