# scoring_project
### Présentation:
* L’entreprise souhaite mettre en œuvre un outil de “scoring crédit” pour calculer la probabilité qu’un client rembourse son crédit, puis classifie la demande en crédit accordé ou refusé.
* Elle souhaite donc développer un algorithme de classification en s’appuyant sur des sources de données variées (données comportementales, données provenant d'autres institutions financières, etc.).
* De plus, les chargés de relation client ont fait remonter le fait que les clients sont de plus en plus demandeurs de transparence vis-à-vis des décisions d’octroi de crédit.
* Cette demande de transparence des clients va tout à fait dans le sens des valeurs que l’entreprise veut incarner.

* Prêt à dépenser décide donc de développer un dashboard interactif pour que les chargés de relation client puissent à la fois expliquer de façon la plus transparente possible les décisions d’octroi de crédit, mais également permettre à leurs clients de disposer de leurs informations personnelles et de les explorer facilement.

## Les données:
Nous avons traiter la base de données de 'Home-Credit-Default', le jeux de données téléchargeable sur kaggle ou plutot sur le sit officiel home-credits-default.

## Missions:

* Construire un modèle de scoring qui donnera une prédiction sur la probabilité de faillite d'un client de façon automatique.
* Construire un dashboard interactif à destination des gestionnaires de la relation client permettant d'interpréter les prédictions faites par le modèle, et d’améliorer la connaissance client des chargés de relation client.
* Mettre en production le modèle de scoring de prédiction à l’aide d’une API, ainsi que le dashboard interactif qui appelle l’API pour les prédictions.
## Spécifités de Dashboard:
  
    - Permettre de visualiser le score et l’interprétation de ce score pour chaque client de façon intelligible pour une personne non experte en data science.
    - Permettre de visualiser des informations descriptives relatives à un client (via un système de filtre).
    - Permettre de comparer les informations descriptives relatives à un client à l’ensemble des clients ou à un groupe de clients similaires.
      
  ## Spécifités teckniques:
  - Realiser un dashboard interactif avec streamlit.
  - Tester la mise en oeuvre d’une démarche de type MLOps d’automatisation et d’industrialisation de la gestion du cycle de vie du modèle.
  - Tester l’utilisation de la librairie evidently pour détecter dans le futur du Data Drift en production.
  - L’analyse à l’aide d’evidently vous permettra de détecter éventuellement du Data Drift sur les principales features, entre les datas d’entraînement et les datas de production, au travers du tableau HTML d’analyse que vous aurez réalisé.
  - Le déploiement de l'application dashboard et de l’API seront réalisées sur une plateforme Cloud solution de google cloud).
  - mettre en oeuvre une démarche d’élaboration des modèles avec Cross-Validation, via GridsearchCV ou équivalent.
 
  ## Spécifications contextuelles:
  - Prendre en compte le déséquilibre entre le nombre de bons et de moins bons clients, avec le smoote.
  - Prendre en compte le désiquilibre entre du coût métier entre un faux négatif (FN - mauvais client prédit bon client : donc crédit accordé et perte en capital) et un faux positif (FP - bon client prédit mauvais :
    donc refus crédit et manque à gagner en marge).
  - On suppose que le coût d’un FN est dix fois supérieur au coût d’un FP.
  - creer un score “métier” (minimisation du coût d’erreur de prédiction des FN et FP) pour comparer les modèles, afin de choisir le meilleur modèle et ses meilleurs hyperparamètres.
  -  Attention cette minimisation du coût métier doit passer par l’optimisation du seuil qui détermine, à partir d’une probabilité, la classe 0 ou 1 (un “predict” suppose un seuil à 0.5 qui n’est pas forcément l’optimum).
  -  En parallèle, maintenez pour comparaison et contrôle des mesures plus techniques, telles que l’AUC et l’accuracy.
  -  Execution des testes unitaires comme preuves de pipeline de déploiement continu.

