# Speed Dating avec Tinder — Analyse Exploratoire des Données (EDA)

## Contexte du projet

Dans un contexte de **baisse des matches**, Tinder cherche à mieux comprendre **ce qui donne réellement envie à deux personnes de se revoir** après une première rencontre.

Pour répondre à cette problématique, ce projet s’appuie sur un **dataset réel de speed dating**.
Chaque interaction correspond à un rendez-vous de 4 minutes, à l’issue duquel chaque participant indique s’il souhaite ou non un **second rendez-vous**.

Ce projet a été réalisé dans le cadre du **module EDA (Exploratory Data Analysis)** de la formation Data Science (Jedha), avec un objectif clair :
**transformer une analyse statistique en recommandations business actionnables**.

---

## Objectifs

### Objectif analytique

* Identifier les **facteurs clés** qui influencent la probabilité d’un second rendez-vous.
* Comparer :

  * ce que les participants **pensent** important
  * et ce qui **fonctionne réellement** dans la prise de décision.

### Objectif business (Tinder)

* Aider Tinder à :

  * améliorer son **algorithme de matching**
  * optimiser la **présentation des profils**
  * augmenter le **taux de match réel** et la satisfaction utilisateur.

---

## Données utilisées

* **Source** : Speed Dating Experiment (2002–2004)
* **Volume** : plus de 8 000 speed dates
* **Granularité** :
  → 1 ligne = 1 interaction entre deux personnes

### Principales variables

* **Décision** :

  * `match` → second rendez-vous mutuel (variable cible)
* **Notes attribuées** :

  * Attractiveness
  * Sincerity
  * Intelligence
  * Fun
  * Ambition
  * Shared interests
* **Informations complémentaires** :

  * sexe, âge, origine/race,
  * auto-évaluations,
  * ordre du rendez-vous dans la soirée.

Un *data dictionary* détaillé accompagne le dataset pour interpréter correctement les variables.

---

##  Nettoyage & préparation des données

L’objectif n’était pas de construire un pipeline complexe, mais de garantir une **EDA propre, lisible et explicable**.

Étapes réalisées :

* suppression des lignes sans :

  * variable cible
  * âge
  * genre
* sélection des variables pertinentes pour l’analyse
* création de variables dérivées :

  * `gender_label` (Homme / Femme),
  * `same_race` (1 si même origine, 0 sinon)
* contrôle des valeurs manquantes sur les variables clés.

Choix assumé : **simplicité, transparence, pédagogie**, adaptés à un projet de fin de module EDA.

---

## Analyses réalisées

### 1. Profil des participants

* Répartition hommes / femmes
* Distribution des âges (principalement 20–35 ans)
* Taux global de match relativement faible

➡️ Montre que les participants restent sélectifs, même en rencontre réelle.

---

### 2. Préférences déclarées (par sexe)

Analyse des critères que les participants disent valoriser chez un partenaire :

* **Hommes** : attractivité, fun
* **Femmes** : sincérité, intelligence
* Les intérêts partagés sont peu cités comme prioritaires

➡️ Hypothèse initiale : le déclaratif ne reflète pas forcément la réalité.

---

### 3. Impact réel sur le second rendez-vous

Analyse du taux de match en fonction des **notes réellement reçues** :

**Top 3 facteurs réels** :

1. Attractivité perçue
2. Fun / ambiance du rendez-vous
3. Intérêts partagés (effet très fort)

➡️ Les intérêts partagés ont un impact **bien plus élevé que ce que les participants déclarent**.

---

### 4. Intérêts partagés vs même origine

Comparaison de deux leviers souvent évoqués dans le matching :

* même origine / race
* intérêts partagés

**Résultat** :

* Même origine → effet faible
* Intérêts partagés → effet très fort sur le taux de match

➡️ Les points communs culturels et de centres d’intérêt sont bien plus déterminants.

---

### 5. Auto-évaluation : réalistes ou non ?

Comparaison entre :

* auto-évaluation des participants
* notes reçues par les autres

Résultat :

* corrélations positives mais faibles
* nombreux cas de surestimation ou sous-estimation

➡️ Les utilisateurs ont une perception imparfaite de leur attractivité réelle.

---

### 6. Ordre du rendez-vous dans la soirée

Analyse de l’effet du moment du rendez-vous (début vs fin) :

* léger effet possible (fatigue ou échauffement)
* impact global limité par rapport aux critères relationnels

➡️ L’ordre joue moins que la qualité perçue de l’échange.

---

## Recommandations business pour Tinder

À partir des analyses, plusieurs leviers concrets émergent :

### 1. Renforcer le matching par intérêts partagés

* Prioriser les profils avec **fort taux de points communs**
* Mettre ces intérêts en évidence dès l’écran de match

### 2. Adapter la présentation selon le genre

* Valoriser davantage :

  * sincérité / intelligence pour les profils masculins vus par des femmes
  * fun / visuel pour les profils féminins vus par des hommes

### 3. Proposer un coaching de profil

* Suggestions de photos
* Mise en avant de traits appréciés
* Aide à la calibration de l’image projetée

### 4. Optimiser l’ordre d’affichage des profils

* Réduire la fatigue de décision
* Tester des stratégies d’exposition progressive

---

## Stack technique

* **Python**
* **pandas / numpy**
* **matplotlib / seaborn**
* Analyse réalisée dans un **notebook unique**, structuré et commenté en français.

---

## Conclusion

Ce projet montre que :

* l’attractivité reste importante
* mais que le **fun** et surtout les **intérêts partagés** sont des leviers majeurs
* largement sous-estimés par les utilisateurs eux-mêmes

👉 Pour Tinder, mieux exploiter ces dimensions représente une **opportunité forte d’augmentation du taux de match réel**, tout en améliorant la qualité des rencontres.

---

## Auteur

Projet réalisé par **FAYCEL FADDAOUI**
Formation Data Science — Jedha
Module : Exploratory Data Analysis (EDA)
