# Analyse de Satisfaction Client - Airbnb Paris 
Exploration de données visant à déterminer si la localisation et le prestige du quartier influencent la qualité de l'expérience voyageur à Paris.

**Lien vers le Notebook :** [Voir l'analyse complète (airbnb_paris.ipynb)](./airbnb_paris.ipynb)

## Méthodologie et Démarche

**Technologies utilisées :** Python, Pandas, Matplotlib, Jupyter Notebook.

Ce projet part d'un cas classique en Data Science : la gestion de l'imprévu.
Initialement, l'objectif était de cartographier les prix des loyers par quartier. Cependant, lors de l'audit technique des données (`df.info()`), j'ai découvert que la colonne `price` était inutilisable (données manquantes).

J'ai donc **pivoté l'analyse** pour me concentrer sur une autre métrique clé : la **satisfaction client** (`review_scores_rating`).

Mon pipeline de travail :
1.  **Nettoyage (Cleaning) :** Suppression des données vides et sélection des colonnes pertinentes (Quartier, Notes, GPS).
2.  **Filtrage :** Création d'un "filtre de crédibilité". J'ai exclu les logements ayant moins de 10 commentaires pour éviter que des notes basées sur un seul avis ne faussent les moyennes.
3.  **Agrégation :** Groupement par quartier (`groupby`) pour établir un classement fiable.
4.  **Visualisation :** Création d'une carte thermique géographique (Heatmap) via les coordonnées Latitude/Longitude.

## Résultats Clés et Optimisations

L'analyse révèle des tendances contre-intuitives :

* **Le "Paradoxe du Prestige" :** Les quartiers les plus chers et centraux (Élysée, Louvre) sont souvent les moins bien notés.
* **La prime à l'authenticité :** Les quartiers "villages" de l'Est parisien (Ménilmontant, Buttes-Chaumont) dominent le classement de satisfaction.
* **Homogénéité :** J'ai pu démontrer statistiquement que l'écart entre le meilleur et le moins bon quartier est infime (< 0.1 point), prouvant que la localisation n'est pas un facteur discriminant pour la qualité à Paris.


## Ce que j'ai appris

Ce projet "Bac à Sable" m'a permis de solidifier mes bases en **Pandas** et **Matplotlib** mais également de comprendre plusieurs réalités du métier de Data Analyst :
1.  **Adaptabilité :** Savoir pivoter quand une variable clé (le prix) manque, plutôt que d'abandonner.
2.  **Esprit critique :** Se méfier des moyennes simples. Le filtrage des données est aussi important que leur analyse.
3.  **Rigueur :** L'importance de structurer un notebook avec un storytelling clair pour rendre les chiffres intelligibles.

## Pistes d'amélioration

Ce projet est voué à évoluer. Les prochaines étapes pourraient être :
* Constituer mon propre jeu de données "Prix" en scrapant le site Airbnb.
* Analyser les commentaires textuels (NLP) pour comprendre *pourquoi* certains quartiers plaisent plus que d'autres.

---
*Projet réalisé dans le cadre d'un apprentissage en Data Science.*
