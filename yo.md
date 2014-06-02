

yo
===

Aujourd'hui, quand on fait du développement web, et donc en particulier du JavaScript, il n'est plus possible de se passer de bons outils pour développer correctement. [Yeoman](http://yeoman.io/) est l'un d'entre eux. Cet outil est en fait une composition de trois outils :

* [grunt](http://gruntjs.com/), le "[Ant](http://ant.apache.org/)" du JavaScript, c'est-à-dire un exécuteur de tâches ;
* [bower](http://bower.io/) le gestionnaire de dépendances ;
* [yo](https://github.com/yeoman/yo) dont on va parler ici.

Yo est ce que l'on appelle un *project scaffolder*, que l'on pourrait traduire en français par "échaffaudeur de projet". Ok, on n'est pas trop aidé. L'idée derrière ce genre d'outils est de générer le squelette d'une application en fonction d'un contexte donné. Un exemple tout bête : je souhaite démarrer une application avec AngularJS. Plutôt que de passer quelques minutes / heures à configurer les bases de mon projet, je vais utiliser un générateur ```yo``` pour me faire ce travail. Une fois exécuté, je n'aurais alors plus qu'à développer mon projet, toutes les bases étant mises en place.

## Installation de yo

```yo``` s'installe via ```npm```, ce qui signifie qu'il vous faudra installer [NodeJS](http://nodejs.org/) si ce n'est déjà fait. Une fois installé, il suffit de lancer la commande ```npm install -g yo``` (l'option ```-g``` assure une installation globale au système) pour que ```yo``` soit installé. Un petit ```yo -v``` nous assurera de sa bonne installation.

## Utiliser un générateur yo

Concrètement, ```yo``` va faire appel à un générateur spécifique pour générer le squelette de notre application. Si je tape simplement ```yo``` dans ma console, celui-ci va me propose quelques options (le nombre d'options va dépendre de ce qui est installé sur ma machine) :

```
$> yo
[?] What would you like to do? (Use arrow keys)
> Run the Generator generator (0.4.4)
  Run the Webapp generator (0.4.9)
  Run the Karma generator (0.8.1)
  Run the Mocha generator (0.1.3)
  Update your generators
  Install a generator
  Find some help
  Get me out of here!
```

Comme vous le voyez, les choix qui s'offrent à moi sont soit l'exécution d'un générateur, soit la mise à jour ou l'installation de nouveaux générateurs.
Normalement, seuls les deux premiers générateurs (générateur de générateur ```yo``` et générateur d'applications web) sont disponibles initialement.

Admettons que nous voulons créer une application AngularJS. Nous allons donc faire appel au [générateur Angular](https://github.com/yeoman/generator-angular). Deux options s'offrent à nous :

1. Passer par la commande ```npm install -g generator-angular```, qui installera le générateur ;
2. Passer par la ligne de commande de ```yo``` :

```
$> yo
[?] What would you like to do?
  Run the Generator generator (0.4.4)
  Run the Karma generator (0.8.1)
  Run the Webapp generator (0.4.9)
  Run the Mocha generator (0.1.3)
  Update your generators
> Install a generator
  Find some help
  Get me out of here!


$> yo
[?] What would you like to do? Install a generator
[?] Search NPM for generators: angular
[?] Here's what I found. Install one? (Use arrow keys)
> generator-angular
  generator-angular-axiom
  generator-angular-beego
  generator-angular-bootstrap
  generator-angular-bootstrap-less
  generator-angular-browserify-express
  generator-angular-caveman2
  generator-angular-cmelion
(Move up and down to reveal more choices)
```

Dans les deux cas, c'est bien ```npm``` qui va s'exécuter pour installer le générateur. 
Pour lancer la génération, c'est la même chose : soit nous exécutons la commande ```yo angular``` (le nom du générateur, sans le ```generator-``` devant), soit nous passons par la commande ```yo``` et on se laisse guider par l'outil. Attention, ```yo``` génère les sources de l'application dans le répertoire courant, pensez donc à créer un sous-répertoire avant.

Là, en fonction du générateur, un certain nombre de questions vont nous être posées, par exemple pour savoir si nous voulons utiliser [SASS](http://sass-lang.com/) ou [Bootstrap](http://getbootstrap.com/) :

```
$> yo angular

     _-----_
    |       |
    |--(o)--|   .--------------------------.
   `---------´  |    Welcome to Yeoman,    |
    ( _´U`_ )   |   ladies and gentlemen!  |
    /___A___\   '__________________________'
     |  ~  |
   __'.___.'__
 ´   `  |° ´ Y `

Out of the box I include Bootstrap and some AngularJS recommended modules.

[?] Would you like to use Sass (with Compass)? No
[?] Would you like to include Bootstrap? Yes
[?] Which modules would you like to include? (Press <space> to select)
>[X] angular-resource.js
 [X] angular-cookies.js
 [X] angular-sanitize.js
 [X] angular-route.js
```

Une fois la commande terminée, nous diposons d'un répertoire bien configuré. Il est parfois requis d'exécuter les commandes ```npm install``` (pour installer les contributions Grunt) et ```bower update``` (pour télécharger les dépendances de l'application) afin d'être tout à fait prêt, mais normalement le générateur va se charger de cette opération.
Voici les principaux éléments de structure de l'application générée :

```
bower.json                     -> Déclaration des dépendences pour Bower
Gruntfile.js                   -> Définition des tâches pour Grunt
package.json                   -> Description de l'application
  +- app                       -> Répertoire des sources
  |    +- bower_components     -> Dépendences téléchargées par Bower
  |    + *                     -> Sources de l'application
  +- node_modules              -> Modules NodeJS nécessaires à l'application (essentiellement pour Grunt)
  +- test                      -> Répertoire des tests (Karma et Jasmine)
       +- *                    -> Sources des tests

```

Comme on peut le voir, ```yo``` fait appel à ses deux copains de ```yeoman``` pour travailler : ```Bower``` et ```Grunt```.
En tapant par exemple ```grunt serve```, ```Grunt``` va exécuter quelques tâches et démarrer un serveur :

```
$> grunt serve
Running "serve" task

Running "clean:server" (clean) task

Running "bowerInstall:app" (bowerInstall) task

Running "concurrent:server" (concurrent) task

Running "copy:styles" (copy) task
Copied 1 files

Done, without errors.

Running "autoprefixer:dist" (autoprefixer) task
Prefixed file ".tmp/styles/main.css" created.

Running "connect:livereload" (connect) task
Started connect web server on 127.0.0.1:9000.

Running "watch" task
Waiting...
```

Grâce à la tâche [livereload](https://github.com/gruntjs/grunt-contrib-livereload) de ```Grunt```, chaque modification du code va entraîner le rechargement automatique de la page :

```
Waiting...OK
>> File "app\views\main.html" changed.

... Reload app\views\main.html ...
Completed in 0.001s at Sun Jun 01 2014 11:02:17 GMT+0200 (Romance Daylight Time) - Waiting...
```

Comme je le disais plus haut, cela prend à peine une minute, et au final, nous disposons d'une application prête pour le développement.


## Créer son propre générateur

Bien qu'il existe tout un tas de générateur, il peut arriver le besoin d'en créer un soi-même. C'est le rôle du ```generator-generator```, qui comme son nom l'indique, génère le squelette d'un générateur. Soyons fous, et lançons la commande ```yo generator``` :



