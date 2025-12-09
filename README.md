# Cartographie de la pollution de l'air dans les Alpes-Maritimes (AtmoSud, QGIS)

Projet de cartographie réalisé dans le cadre de ma Licence 3 Intelligence Artificielle à l'Université Côte d'Azur.  
Objectif : analyser et visualiser les variations de pollution de l'air dans le département des Alpes-Maritimes (06) à partir des données de capteurs AtmoSud, en utilisant QGIS.

---

## 🎯 Objectifs du projet

- Représenter la pollution de l'air dans le 06 à deux échelles :
  - **Carte horaire / 24h** (exemple : ozone)
  - **Carte sur 7 jours** (exemple : dioxyde d’azote NO₂)
- Mettre en évidence :
  - Les zones les plus exposées
  - Les différences entre les stations de mesure
  - La dynamique journalière / hebdomadaire des polluants
- Travailler un flux complet : données brutes → préparation → cartographie → interprétation.

---

## 🧾 Données

- Source : **AtmoSud** (réseau de surveillance de la qualité de l’air en région Sud).
- Fichiers utilisés :
  - `QGIS/pollution_06_24h_prop.txt`  
    - Données de pollution sur 24 heures pour un polluant donné.
  - `QGIS/pollution_06_7j_prop.csv`  
    - Données de pollution sur 7 jours pour plusieurs stations.

Les variables principales :
- Nom de la station
- Polluant (ex. : ozone, dioxyde d’azote)
- Valeur mesurée
- Unité
- Date / heure
- Coordonnées projetées (x_l93, y_l93) pour la localisation dans QGIS.

---

## 🗺️ Méthodologie (QGIS)

Travail réalisé essentiellement dans **QGIS** :

1. **Préparation des données**
   - Vérification du format CSV / texte (séparateur, encodage).
   - Sélection des colonnes utiles.
   - Filtre par polluant (ex. NO₂, ozone) et par période (24h ou 7 jours).

2. **Géoréférencement**
   - Utilisation des coordonnées projetées (Lambert 93) pour placer les stations.
   - Chargement d’un fond de carte adapté (département 06).

3. **Symbologie**
   - Application d’une **symbologie graduée** sur la colonne de valeurs.
   - Choix d’une palette allant du vert (faible pollution) au rouge (pollution élevée).
   - Ajustement des classes pour une bonne lisibilité des différences entre stations.

4. **Mise en page cartographique**
   - Ajout d’un titre, de la légende, de l’échelle graphique, de la flèche du nord.
   - Mention de la source des données (AtmoSud).
   - Export en PDF.

Les principales cartes produites sont disponibles dans `outputs/`.

---

## 📂 Contenu du dépôt

- `QGIS/`
  - `pollution_06_24h_prop.txt` : données 24h.
  - `pollution_06_7j_prop.csv` : données 7 jours.
  - `24H.qgz` : projet QGIS pour la carte 24h.
  - `7J.qgz` : projet QGIS pour la carte 7 jours.
- `outputs/`
  - `Carte_Ozone_24H.pdf` : carte finale de l’ozone sur 24h.
  - `Carte_Dioxyde_7J.pdf` : carte finale du dioxyde d’azote sur 7 jours.
- `report/`
  - `Rapport.pdf` : rapport complet expliquant la démarche, les choix de symbologie et l’interprétation des résultats.

---

## ▶️ Comment ouvrir le projet

1. Installer **QGIS** (version 3.x recommandée).
2. Cloner ce dépôt :

   ```bash
   git clone https://github.com/<mon-utilisateur>/cartographie-pollution-atmosud-06.git
   cd cartographie-pollution-atmosud-06
