# Econometric Analysis of Digital Transformation and Labor Productivity (EU 2010–2023)

![Header Banner](https://raw.githubusercontent.com/amina-mir/Econometric-Analysis-of-Digital-Transformation-and-Labor-Productivity/main/headerbanner.svg)

## 🌐 Internet, Haut Débit & Productivité du Travail dans l'UE (2010–2023)

### Analyse Économétrique sur Données de Panel avec R

![Language: R](https://img.shields.io/badge/Language-R-blue.svg) ![Package: plm | ggplot2](https://img.shields.io/badge/Package-plm%20%7C%20ggplot2-orange.svg) ![Data: World Bank WDI](https://img.shields.io/badge/Data-World%20Bank%20WDI-blue.svg) ![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

---

### 🎯 Objectif du Projet

Ce projet vise à mesurer l'impact de l'accès à **Internet** et au **Haut Débit** sur la **productivité du travail** (PIB par personne employée) au sein de 15 pays de l'Union Européenne, sur la période **2010–2023**.

### 📊 Données

* **Source :** Banque Mondiale, World Development Indicators (WDI).
* **Variables Clés :**
    * Productivité du travail (PIB par employé)
    * Taux de pénétration d'Internet
    * Abonnement au haut débit fixe

### 🔬 Méthode Économétrique

L'analyse est réalisée sur des données de panel avec les étapes suivantes :

1. **Prétraitement :** Nettoyage des données, gestion des valeurs manquantes, et transformation logarithmique.
2. **Spécification du Modèle :** Estimation et comparaison de trois modèles (MCO Poolés, Effets Fixes, Effets Aléatoires).
3. **Tests de Sélection :** Choix du modèle via les tests de Chow, Breusch-Pagan, et Hausman.
4. **Diagnostics :** Vérification de l'hétéroscédasticité, autocorrélation, multicolinéarité (VIF), et normalité des résidus.
5. **Correction :** Utilisation d'erreurs standards robustes HAC (Arellano) pour corriger l'hétéroscédasticité et l'autocorrélaton.

### 📝 Résultat Principal

**L'effet d'Internet sur la productivité est positif et significatif (à 5 %) avant correction**, mais il perd sa significativité après l'application de la correction HAC (Arellano). Cela souligne l'importance de modèles robustes pour valider les conclusions économiques.

### 📁 Contenu du Dépôt

| Fichier / Dossier | Description |
| :--- | :--- |
| `panel_econometrie.R` | Script R complet (estimation, tests, diagnostics). |
| `panel_digital_productivity.csv` | Jeu de données de panel (Source : WDI). |
| `Digital_Transformation_Labor_Productivity_Report.pdf`| Rapport complet avec résultats détaillés et interprétation. |
| `header_banner.svg` | Bannière visuelle pour le README. |
| `readme.md` | Ce fichier. |

### 🛠️ Outils

* **R (v4.3.1+)**
* **plm** (modèles de panel)
* **ggplot2** (visualisation)

---

### 👩‍💻 Auteure

**Amina Mir**  
*Master Économie Appliquée et Data Science*  
*FSJES Meknès (Université Moulay Ismail)*
