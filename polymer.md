Lors de [Devoxx France 2014](http://www.devoxx.fr), j'ai présenté avec mon ami [Julien Jakubowski](https://twitter.com/jak78) un "Tools In Action" sur la [création de web component avec Google Polymer](http://cfp.devoxx.fr/devoxxfr2014/talk/HXP-745/Cr%C3%A9ons%20un%20web%20component%20avec%20Polymer).

Peut-être que vous n'avez pas eu la chance de venir y assister. Je vous propose donc une initiation à Google Polymer et aux web components.


# Les web components, qu'est-ce que c'est ?

Un site internet, c'est un ensemble de pages écrites en HTML (dans la plupart des cas du moins). Aujourd'hui, ces sites sont de plus en plus riches, de plus en plus dynamiques. Les composants qui structurent une page web sont de fait plus complexes.
Paradoxalement, le langage HTML est un langage assez pauvre, puisqu'il ne dispose que d'un peu plus d'une centaine de "mots", les balises.
Résultat, il faut généralement bidouiller pour créer un vrai composant. Ainsi, avec Twitter Bootstrap, la création d'un panneau d'onglets va nécessiter d'utiliser les balises de liste (```<ul>``` et ```<li>```) comme cela :

```xml
<ul class="nav nav-tabs">
  <li class="active"><a href="#home" data-toggle="tab">Home</a></li>
  <li><a href="#profile" data-toggle="tab">Profile</a></li>
  <li><a href="#messages" data-toggle="tab">Messages</a></li>
  <li><a href="#settings" data-toggle="tab">Settings</a></li>
</ul>
```

Ce n'est pas trop moche, mais cela reste moins lisible que quelque chose de ce genre :

```xml
<tabs-pane>
	<tab title="Home" active="true">...</tab>
	<tab title="Profile">...</tab>
	<tab title="Messages">...</tab>
	<tab title="Settings">...</tab>
</tabs-pane>
```

Or la lisibilité est un critère très important quand on sait que l'on doit passer 80% du temps à lire du code et 20% à en écrire.

Dans le même genre, est-ce qu'il ne serait pas plus pratique d'écrire ceci pour embarquer un tweet dans une page :

```
<tweet tweetId="123456789"></tweet>
```

Hé bien c'est le but des web components que de proposer de créer ses propres balises HTML et de pouvoir les exporter facilement.

# Le standard web Component

Finalement, créer ses propres tags HTML n'est pas quelque chose de nouveau, on peut le faire grâce à différents frameworks - comme par exemple avec une directive AngularJS - voire même en pur JavaScript.
Mais les web components sont en réalité [un standard en cours d'élaboration par le W3C](http://www.w3.org/TR/components-intro/), et c'est là sa force première. Pour être plus précis, il s'agit d'un ensemble de standards, comprennant les briques nécessaires à l'élaboration d'un composant web. Je pense par exemple au [shadow DOM](http://w3c.github.io/webcomponents/spec/shadow/) ou encore au [HTML template](https://dvcs.w3.org/hg/webcomponents/raw-file/tip/spec/templates/index.html#template-element).

Ces standards sont toujours à l'étude, mais il existe quelques implémentations pour pouvoir jouer dès à présent avec les web components. Celui qui va nous intéresser plus particulièrement c'est celle de Google, à savoir [Polymer](http://www.polymer-project.org/).

![Google Polymer](http://www.polymer-project.org/images/logos/p-logo.svg "Google Polymer")


# Let's start!

Assez parlé, codons ! Je vous propose de coder une balise `progress-bar`, basée sur [celle proposée par Twitter Bootstrap](http://getbootstrap.com/components/#progress). Le code HTML est le suivant :

```html
<div class="progress progress-striped">
  <div class="progress-bar progress-bar-info" role="progressbar" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100" style="width: 20%">
    <span class="sr-only">20% Complete</span>
  </div>
</div>
```


Commençons par créer une application web toute simple. On va donc s'appuyer sur [yo](https://github.com/yeoman/yo), qui permet grâce à un générateur spécifique de nous créer une application blanche, préconfigurée pour un contexte particulier. On exécute ainsi la commande `yo webapp`. Une fois la structure générée, un petit `npm install` puis `bower install` nous permettent d'être prêt à coder. Pour nos besoins, j'ai un peu épuré le projet, en supprimant quelques éléments inutiles et en enlevant jQuery, qui n'est pas toujours utile.

Grâce à sa pré-configuration grâce à `yo`, nous disposons d'une tâche [Grunt](http://gruntjs.com/) (une sorte de `Apache Ant`, mais pour JavaScript) `serve`, qui va nous permettre de modifier notre code et de voir automatiquement le navigateur se recharger pour prendre ces modifications en compte. Il nous suffit donc d'exécuter `grunt serve`, et c'est tout ! Notre page sera dès lors visible à l'adresse http://localhost:9000.

Première étape, il nous faut ajouter la librairie Polymer à notre projet. On va donc utiliser [bower](http://bower.io/) pour gérer notre dépendance, on exécute donc la commande `bower install polymer --save` (l'option `--save` permet d'ajouter la dépendance dans le fichier `bower.json`). Nous disposons maintenant de `Polymer` dans le répertoire `bower_components`, mais aussi de `platform`. Comme je l'ai expliqué, les web components se basent sur un ensemble de briques qui ne sont aujourd'hui pas toutes supportées nativement par les navigateurs. Il faut donc les émuler, via des "polyfills". Et c'est précisément le rôle de `platform`.

Voilà notre HTML de base pour bien démarrer :

```html
<!doctype html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Polymer</title>
        <meta name="viewport" content="width=device-width">
        <link rel="stylesheet" href="../bower_components/bootstrap/dist/css/bootstrap.css">
        <!-- Nos dépendances pour utiliser Polymer -->
        <script src="../bower_components/platform/platform.js"></script>
        <script src="../bower_components/polymer/polymer.js"></script>
    </head>
    <body>
        <div class="container">
            <div class="header">
                <h3 class="text-muted">Google Polymer</h3>
            </div>
            <div class="footer">
                <p><span class="glyphicon glyphicon-heart"></span> Polymer</p>
            </div>
        </div>
	</body>
</html>
```

Commençons par créer un élément Polymer pour le composant `progress-bar`. A noter qu'un composant Polymer doit être composé de deux mots séparés par un `-` (sans doute pour éviter la confusion avec les "vrais" tags HTML) :

```html
<polymer-element name="progress-bar">
    <template>
    </template>
    <script>
        var module = (function() {
        })();
        Polymer('progress-bar', module);
    </script>
</polymer-element>
```

On voit trois choses intéressantes :

* le tag `polymer-element` qui prend le nom du composant (`progress-bar`) ;
* le tag `<template>` qui va nous permettre d'ajouter le code HTML ;
* la partie script qui nous permet d'initialiser un objet `module` qui correspond à notre composant Polymer, ainsi que la ligne `Polymer('progress-bar', module);` qui permet de l'enregistrer pour l'utiliser par la suite.

On injecte alors le code HTML de la barre de progression dans le `<template>`, comme suit:

```html
<polymer-element name="progress-bar">
    <template>
        <div class="progress progress-striped">
            <div class="progress-bar progress-bar-info" role="progressbar" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100" style="width: 20%">
                <span class="sr-only">20% Complete</span>
            </div>
        </div>
    </template>
    <script>
        var module = (function() {
        })();
        Polymer('progress-bar', module);
    </script>
</polymer-element>
```

C'est bien, mais il faudrait pouvoir définir le pourcentage de progression dynamiquement, dont acte :

```html
<polymer-element name="progress-bar" attributes="percentage">
    <template>
        <div class="progress progress-striped">
            <div class="progress-bar progress-bar-info" role="progressbar" aria-valuenow="{{ percentage }}" aria-valuemin="0" aria-valuemax="100" style="width: {{ percentage }}%">
                <span class="sr-only">{{ percentage }}% Complete</span>
            </div>
        </div>
    </template>
</polymer-element>
<progress-bar percentage="42"></progress-bar>
```

On voit plusieurs choses :

* il faut définir les attributs passés au composant via l'attribut `attributes="percentage"` ;
* dans le code HTML, on peut accéder à cette information via la syntaxe "double moustaches", `{{ ... }}`. Les habitués d'Angular ne seront pas perdus !

Changeons un peu notre composant pour donner un `min`, un `max` et une `value`, en laissant à la charge du composant de calculer lui-même le pourcentage:

```html
<polymer-element name="progress-bar" attributes="min,max,value">
    <template>
        <div class="progress progress-striped">
            <div class="progress-bar progress-bar-info" role="progressbar" aria-valuenow="{{ value }}" aria-valuemin="{{ min }}" aria-valuemax="{{ max }}" style="width: {{ percentage }}%">
                <span class="sr-only">{{ percentage }}% Complete</span>
            </div>
        </div>
    </template>
    <script>
        var module = (function() {
            return {
                get percentage() {
                    return ((this.value - this.min) / (this.max - this.min)) * 100;
                }
            }
        })();
        Polymer('progress-bar', module);
    </script>
</polymer-element>
<!-- Utilisation dans ma page du web component "progress-bar" -->
<progress-bar min="0" max="20" value="12"></progress-bar>
```

On voit ici aussi que les paramètres, `min`, `max` ou `value` sont disponibles également dans la partie `<script>`.

Et si on souhaite change la valeur courante ? Un web component peut être accédé de la même façon que n'importe quel autre élément du DOM, donc un simple bout de JavaScript suffit :

```html
<button class="btn btn-primary" onclick="changeValue()">Change value</button>
<script>
    function changeValue() {
        var bar = document.querySelector('#progression'); // On récupère l'objet
        bar.value = +bar.min + (Math.random() * (bar.max - bar.min));
    }
</script>
```

Il serait sans doute plus propre de proposer des fonctions, comme par exemple `updateValue`:

```html
<polymer-element name="progress-bar" attributes="min,max,value">
    ...
    <script>
        var module = (function() {
            return {
                get percentage() {
                    return ((this.value - this.min) / (this.max - this.min)) * 100;
                },
                updateValue: function(val) {
                    this.value = val;
                }
            }
        })();
        Polymer('progress-bar', module);
    </script>
</polymer-element>
```

pour pouvoir l'appeler ensuite :

```javascript
function changeValue() {
    var bar = document.querySelector('#progression');
    bar.updateValue(+bar.min + (Math.random() * (bar.max - bar.min)));
}
```


Externalisation
===============

C'est bien beau tout ça, mais comment je fournis ce web component tout beau à une autre équipe ?
C'est simple. Je déplace tout le code du `<polymer-element>` dans un fichier séparé, par exemple `progress-bar.html`, puis je l'importe grâce à cette petite ligne dans mon entête de page :

```
<link rel="import" href="progress-bar.html">
```

Le reste de ma page initiale ne change pas, je peux du coup utiliser mon `<progress-bar id="progression" min="0" max="20" value="12"></progress-bar>` sans problème.
A la limite, je pourrais même sortir le lien vers la librairie `polymer` et le mettre directement dans mon fichier HTML :

`progress-bar.html` :

```html
<script src="../bower_components/polymer/polymer.js"></script>
<polymer-element name="progress-bar" attributes="min,max,value">
    ...
</polymer-element>
```

et dans ma page `index.html` :

```html
<html>
    <head>
        ...
        <script src="../bower_components/platform/platform.js"></script>
        <link rel="import" href="progress-bar.html">
    </head>
    <body>
    	...
        <progress-bar id="progression" min="10" max="20" value="12"></progress-bar>
    </body>
</html>
```

Il est (pour l'instant) encore nécessaire d'avoir un lien vers la librairie `platform` dans la page principale car le `import` est lui-même [un standard](http://www.w3.org/TR/2014/WD-html-imports-20140311/) en cours de travail du W3C et n'est donc pas supporté nativement par les navigateurs. Il faut donc avoir recours au polyfill de `platform` pour l'instant.

Voilà un premier voyage dans le monde des web components avec Polymer. D'autres billets viendront peut-être le compléter...
