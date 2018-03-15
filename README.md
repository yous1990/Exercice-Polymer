Ce projet est un exercice de développement web.

## Objectif

Vous allez apporter des modifications à une webapp utilisant la librairie [Polymer 2](https://www.polymer-project.org/2.0/start/quick-tour) autour des WebComponents.

Cette application affiche des articles récupérés depuis [NewsAPI](https://newsapi.org/), qui regroupe plusieurs sources d'actualités. Elle permettra également de filtrer les contenus affichés.

Les navigateurs ciblés sont les dernières versions de Firefox, Chromium et Edge.

## Méthode de travail

Le code est versionné sur ```git```. Vous respecterez les pratiques suivantes :

- vous travaillez dans une branche séparée de ```master```

- vos commits sont simples (une fonctionnalité maximum) et documentés en anglais

Les tâches sont assez indépendantes, traitez-les à votre rythme.

Si vous vous sentez créatifs, n'hésitez pas à aller plus loin que l'exercice (mais respectez toujours les spécifications données).

## Prérequis

Installer un environnement de travail pour Polymer:

- installer ```nodejs``` et ```npm``` sur la machine

- installer ```bower``` et ```polymer-cli``` : ```npm install -g bower polymer-cli```

## Préparation

1) Cloner ce dépôt git et explorer les fichiers

2) Pour installer les dépendances du projet, lancer la commande ```bower install``` dans le dossier du projet

3) Pour tester l'application en local, lancer la commande ```polymer serve```

## Exercices

### Modification de l'élément `news-card`

L'élément `news-card` affiche une news, composée d'un titre, de son auteur, d'une image, d'une date de publication, d'une description et d'un lien vers l'article.

Naviguez à l'url de la démo (ex.: http://127.0.0.1:port_number/src/news-card/demo/index.html)

1) Ajoutez les propriétés suivantes à l'élément :
`title`, `author`, `description`, `img` et `href` de type String et `publishedAt` de type Date.

2) Modifiez le template de l'élément et ajouter du style pour correspondre aux spec cf img.

3) Convertissez la date dans un format lisible en anglais.

4) Nous voudrions que la description soit révélée au survole de l'image, par dessus celle-ci, faites les modifications nécessaires.

5) Ajouter à l'image, un placeholder de votre choix en base64.

6) Au clic sur l'élément le lien doit s'ouvrir dans un nouvel onglet.

7) Augmentez l'ombre autour de l'élément lorque le curseur est dessus.

8) Optionel - Vous pouvez modifier la démo de l'élément `news-card` pour récupérer les données depuis le fichier `data.json` en utilisant l'API Fetch. Dans le fichier de démo `news-card/demo/index.html`, écoutez l'évènement `WebComponentsReady` sur le document, puis récupérez le contenu du fichier `data.json`, sélectionnez l'élément `news-card` et peuplez-le avec ces données.

### Récupération des données de NewsAPI

Créer une nouvelle clé d'API sur https://newsapi.org/ et configurez l'élément `<news-list>` dans `search-new-app/search-new-app.html`.

Naviguez à l'url de l'application servie par la commande `polymer serve`.

Créer une nouvel élement `<news-list>` qui prends en entrée l'id d'une source et une clé d'API.

- il utilise l'élément [`iron-ajax`](https://www.webcomponents.org/element/PolymerElements/iron-ajax) pour générer une requête qui récupère des articles quand la source change.
- il maintient une propriété `news` sauvegardant le contenu de la dernière requête.
- il [itère](https://www.polymer-project.org/2.0/docs/devguide/templates)  sur les news pour les afficher avec `<news-card>`.