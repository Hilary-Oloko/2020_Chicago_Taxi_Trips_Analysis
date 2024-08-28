Down below you will find the French translation.
Vous trouverez plus bas la traduction en français

# Chicago Taxi Trips Analysis

This little project aims to manipulate data using PySpark SQL and implement visualizations with Dash, exploring features that were not tested in my previous project like changing metrics on the same graph or display the same metric but change the graph. 

The focus is on analysing Chicago taxi trip data with an emphasis on geospatial and temporal analysis.

## Get data

The file is too large to be load here. But you can find it by going here: https://www.kaggle.com/datasets/chicago/chicago-taxi-trips-bq
If you don't want to change the code too much, consider adding it to a data folder in your directory.

## Data Processing with PySpark SQL

1. **Data Cleaning:**
   - Removed rows with no geolocation for dropoff and pickup to ensure the integrity of our visualization based on maps.

2. **Filtering Criteria:**
   - Retained only trips longer than 60 seconds and at least 0.12 miles (approximately 200 meters) to focus on meaningful trips.

3. **Handling Missing Values:**
   - Replaced null values in the Total Trip and Tips columns with average values. 

I wanted to replace these based on averages of similar locations but faced challenges due to my current Spark skills. If you have any solutions, don't hesitate to contact me!

4. **Period Calculation:**
   - Added a new column, "Period," derived from the pickup datetime, categorized into three values: Morning, Afternoon, and Evening.

5. **Exporting transformed data:**
   I exported the transformed data as a CSV file. Because the dataframe was very large, It was divided into 11 parts.

## Visuals in the Report

### Filters
- Year
- Month
- Period

### Cart
- Total number of trips
- Total revenue
- Average distance per trip (Km)
- Average duration (minutes)

### Geospatial Analysis
- Identification of locations with the highest average payment.
- Identification of locations where the highest tips are given on average.

### Temporal Analysis
- Bar and line charts to analyze average trip duration by time of day.
- Identification of peak and off-peak periods based on trip costs (seasonality analysis).

Run the main Python script to start the dashboard. The dashboard will be accessible via a local web server using http://127.0.0.1:8050/.

![image](https://github.com/user-attachments/assets/362d5046-8362-4031-a808-34324f9f5830)

# Analyse des Courses de Taxi à Chicago

## Vue d'ensemble du projet
Ce projet vise à manipuler des données en utilisant PySpark SQL et à mettre en œuvre des visualisations avec Dash, en explorant des fonctionnalités qui n'avaient pas été testées dans des projets précédents comme changer de métrique sur le même graphique ou afficher la même métrique mais changer de graphique.

Je me suis concentrée sur l'analyse des données de courses de taxi à Chicago, avec une attention particulière sur l'analyse géospatiale et temporelle.

## Obtenir les données

Le fichier est beaucoup trop lourd pour que je puisse le charger ici. Mais vous pouvez le trouver en allant ici : https://www.kaggle.com/datasets/chicago/chicago-taxi-trips-bq
Si vous ne voulez pas trop changer le code, pensez à l'ajouter dans un dossier data de votre répertoire.

## Transformation des données avec PySpark SQL

1. **Nettoyage des données :**
   - Suppression des lignes sans géolocalisation pour les points de dropoff et pickup afin d'assurer l'intégrité de notre visualisation basée sur des cartes.

2. **Critères de filtrage :**
   - Conservation uniquement des trajets d'une durée supérieure à 60 secondes et d'au moins 0,12 miles (environ 200 mètres) pour se concentrer sur des trajets assez significatifs.

3. **Gestion des valeurs manquantes :**
   - Remplacement des valeurs nulles dans les colonnes Total Trip et Tips par des valeurs moyennes.

J'ai cherché à remplacer ces valeurs en fonction des moyennes des localisations similaires, mais j'ai rencontré des difficultés en raison de mes compétences actuelles en Spark. Si vous avez des solutions faites moi signe.

4. **Calcul de la période :**
   - Ajout d'une nouvelle colonne, "Period," dérivée de la date et heure de "pickup", classée en trois valeurs : Matin, Après-midi et Soir.

5. **Export des données transformées :**
   J'ai exporté les données transformées sous forme de CSV. Parce que le dataframe était très lors, j'ai il a été divisé en 11 parties.

## Visuels du rapport

### Filtres
- Année
- Mois
- Période

### Cartes
- Nombre total de courses
- Chiffre d'affaires total
- Distance moyenne par course (Km)
- Durée moyenne (minutes)

### Analyse géospatiale
- Identification des localisations avec les paiements le plus élevé en moyenne.
- Identification des localisations où les pourboires sont les plus élevés en moyenne.

### Analyse temporelle
- Graphiques en barres et en lignes pour analyser la durée moyenne des courses par période de la journée.
- Identification des périodes de pointe et de creux en fonction du coût des trajets (analyse de la saisonnalité).

Ensuite, lancez le script Python principal pour démarrer le dashboard. Le dashboard sera accessible via un serveur web local en utilisant http://127.0.0.1:8050/.

![image](https://github.com/user-attachments/assets/96d8a2de-8c6a-4073-8daf-3185f0677a11)
