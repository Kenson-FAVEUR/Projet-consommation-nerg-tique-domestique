# 🔌 Projet de Modélisation de la Consommation Électrique Domestique

## 👤 Auteur
**Kenson FAVEUR**  
📅 Date : 14 Avril 2025

---

## 📋 Objectif du projet

Ce projet vise à analyser la consommation électrique d’un foyer à partir de données mesurées minute par minute sur une période de **six mois** (du 1er janvier au 30 juin 2007). L’objectif est de :

- Comprendre les facteurs qui influencent la consommation d’électricité
- Construire un **modèle prédictif** fiable (régression linéaire multiple)
- Évaluer la performance du modèle
- Proposer des pistes d’amélioration

---

## 📂 Contenu du dépôt

- `data/` : dossier pour les données brutes ou nettoyées
- `scripts/` : fichiers R pour le traitement des données et la modélisation
- `rapport.Rmd` : rapport RMarkdown complet (analyse, graphiques, interprétations)
- `README.md` : ce fichier
- `plots/` : visualisations générées (optionnel)

---

## 🧰 Packages utilisés

- `tidyverse`
- `lubridate`
- `forecast`
- `tseries`
- `imputeTS`
- `zoo`

---

## 📊 Description des données

Les données proviennent de mesures domestiques à fréquence minute. Les variables principales :

- `Global_active_power` : puissance active (kW)
- `Global_reactive_power` : puissance réactive (kW)
- `Voltage` : tension (V)
- `Global_intensity` : intensité du courant (A)
- `Sub_metering_1` à `Sub_metering_3` : sous-compteurs d'énergie (Wh)
- `Date` et `Time` : information temporelle

---

## 🔍 Étapes de l’analyse

1. **Nettoyage des données**
   - Traitement des formats de date/heure
   - Interpolation des valeurs manquantes
   - Conversion des types de variables

2. **Exploration visuelle**
   - Histogrammes, boxplots, saisonnalité horaire et hebdomadaire
   - Analyse des distributions et pics de consommation

3. **Modélisation**
   - Régression linéaire multiple
   - Évaluation des coefficients et de leur signification

4. **Évaluation du modèle**
   - R² = 0.70
   - MAE ≈ 0.4355 kW
   - RMSE ≈ 0.6463 kW

5. **Diagnostic des résidus**
   - Résidus vs valeurs ajustées
   - Q-Q plot
   - Histogramme

6. **Limites & pistes d'amélioration**
   - Absence de dimension temporelle dans le modèle (pas de saisonnalité)
   - Possibilité d’intégrer des modèles de séries temporelles (ARIMA, SARIMA)
   - Intégration de variables comme la température ou les jours fériés

---

## 📈 Résultats principaux

- La consommation suit un **rythme journalier** marqué (pics matin et soir)
- Le **week-end** présente une consommation plus élevée
- Tous les coefficients du modèle sont **hautement significatifs (p < 0.001)**
- Le sous-compteur `Sub_metering_3` (chauffe-eau, climatisation) est le plus énergivore

---

## 🧠 Conclusion

Ce projet montre que la régression linéaire peut fournir un **modèle robuste** pour prédire la consommation électrique à court terme, en s’appuyant uniquement sur les mesures internes d’un foyer. Toutefois, **l’intégration de la dimension temporelle** et de facteurs externes permettrait d’atteindre une meilleure précision.

---

## 📌 À venir

- Version du modèle avec **composantes saisonnières**
- Comparaison avec des modèles non-linéaires ou de machine learning (e.g., random forest, XGBoost)
- Dashboard interactif en Shiny ou Python Streamlit

---

## 📜 Licence

Projet académique – libre d’utilisation à des fins pédagogiques.
