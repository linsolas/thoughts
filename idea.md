
# Test d'IntelliJ IDEA v13

## Qu'est-ce qu'IntelliJ

### Introduction

Depuis janvier 2001, la société [JetBrains](http://www.jetbrains.com/) édite le logiciel [IntelliJ IDEA](http://www.jetbrains.com/idea/). Il s'agit d'un *EDI* (ou *IDE* en anglais), à savoir un *Environnement de Développement Intégré* (*Integrated Development Environment*), autrement dit un ensemble d'outils déstinés au développement logiciel. IDEA est ainsi à mettre au même niveau - toutes proportions gardées - d'[Eclipse](http://www.eclipse.org/) ou encore [NetBeans](http://www.netbeans.org/).

Nous allons voir dans cet article quelles sont les principales nouveautés apportées par cette nouvelle version, la 13e, et nous verrons ensuite quelques fonctionnalités avancées de l'EDI qui en font une star des outils de développement.


### Versions et prix

IDEA existe en deux versions : **Community** et **Ultimate**. Pour faire simple, la version **Community**, gratuite, est avant tout destinée au développement d'applications "lourdes" Java, Scala et Android. Dès qu'il s'agira de développer des applications web, il faudra se tourner vers l'édition **Ultimate**. Son prix, pour une licence personnelle, est de 179€.

Un comparatif complet des deux éditions est visible [ici](http://www.jetbrains.com/idea/features/editions_comparison_matrix.html).

Vous pouvez télécharger l'une des deux versions sur la [page dédiée](http://www.jetbrains.com/idea/download/). Notez au passage qu'IntelliJ IDEA est compatible Windows, Mac et Linux.


## Les nouveautés de la version 13

Comme à chaque fin d'année, JetBrains publie sa nouvelle version majeure de son EDI. 2013 n'échappe pas à la règle, et a vu la version 13 de l'outil sortir. Quelles sont les principales nouveautés de cette version ? C'est ce que nous allons voir.

### Android Studio

Les développeurs d'applications mobiles pour Android vont être contents. Annoncé lors du Google I/O de 2013, IDEA est désormais l'EDI standard pour le développement d'applications mobiles pour l'OS de Google.

Cet Android Studio se compose de différents éléments :

* Meilleure intégration de [Gradle](http://www.gradle.org/), l'outil de construction des applications Android.
* Éditeur visuel pour la partie graphique des applications.
* Émulateur d'appareils Android.
* Éditeur XML dédié à Android.
* Outil d'inspection Lint, pour analyser la qualité du code 

Autre bonne nouvelle, l'Android Studio est proposé dès la version **Community**.


### Support de JavaEE 7 et Spring

Attention, ces nouveautés ne sont disponibles que pour la version **Ultimate**.
La 13e édition d'IDEA dispose d'un support complet des spécifications JavaEE 7, ce qui implique :

* Gestion du framework web Java Server Faces (JSF) 2.2.
* Support du *Contexts and Dependency Injection* (CDI) 1.1.
* Introduction des nouvelles annotations de JAX-RS 2.0 pour les web-services RESTful.
* Amélioration du client REST intégré.
* Présence des annotations utilisées pour les *Web Sockets*.
* Intégration des nouvelles versions des serveurs d'applications : Glassfish 4.0, WildFly 8, Tomcat 8, etc.

Pour ce qui est de Spring, le support déjà bien présent dans les précédentes versions est amélioré. On y retrouvera une meilleure gestion de Spring MVC permettant une navigation aisée entre les controlleurs et les pages HTML associées, la détection des contextes non mappés et annotés avec @Context, ou encore 


### Langages alternatifs

Déjà bien supportés dans la précédente version, le support pour Scala ou Groovy s'améliore encore.

Pour Groovy, différentes fonctionnalités de refactoring ont été mises en place, comme l'introduction de variables ou de constantes. IDEA propose désormais la possibilité de créer des tests avec la librairie [Spock](https://code.google.com/p/spock/). Différents nouveaux inspecteurs ont également été introduits.

Concernant Scala, IDEA offre le support de l'outil [sbt](http://www.scala-sbt.org/), des options de réorganisation du code ou encore la génération de méthodes de base (telles que *hashCode* ou *equals*).


### Développement web

Vous l'aurez deviné, les fonctionnalités propres au développement web ne sont disponibles que pour la version **Ultimate**. Les nouveautés sont celles-ci :

* Débogeur JavaScript amélioré, en particulier pour Google Chrome et [Node.js](http://nodejs.org/).
* Amélioration du refactoring CSS.
* Support de la librairie de test [Karma](https://github.com/karma-runner/karma).
* Support de la verison 1.0 de [Dart](https://www.dartlang.org/).
* Début de l'intégration du futur standard des [composants web](http://www.w3.org/TR/components-intro/).
* Gestion des langages de *templating* [Moustache](http://mustache.github.io/) ou [Handlebars](http://handlebarsjs.com/).


### Généralités

Pour ce qui est des gestionnaires de sources, différentes améliorations sont apportées pour Git ou Mercurial. On notera ainsi l'ajout d'une fonctionnalité de "pull-request" pour GitHub.
Pour celles et ceux qui sont encore sur Subversion (SVN), ils seront heureux d'apprendre qu'IDEA est enfin compatible avec Subversion 1.8.

Concernant l'interface graphique, différentes améliorations ont été apportées, les thèmes Darcula et *Light* étant toujours présents. À noter la présence d'un mode "Présentation" qui ravira celles et ceux qui font des présentations techniques et qui doivent montrer du code. 

Dans l'optique d'avoir tout sous la main dans un même outil, IDEA intègre désormais la possibilité d'exécuter des commandes shell localement ou à distance (*via* une connexion SSH) directement par la vue "Ligne de commandes".

Pour améliorer la productivité, la nouvelle fonction de recherche permet d'accéder à pratiquement tout à travers la même fenêtre : classe, méthode, action, paramétrage, etc.

Retrouvez toutes ces nouveautés, et bien plus encore sur la [page dédiée du site de JetBrains](http://www.jetbrains.com/idea/whatsnew/index.html).


## Ce qui fait la force d'IntelliJ

On reproche souvent à IntelliJ IDEA d'être payant et d'avoir un prix relativement élevé. Une licence unique coûte 179€ si elle est personnelle, 449€ s'il s'agit d'une licence d'entreprise. Toutefois, ceux qui ont vraiment goûté à cet EDI n'ont pas envie de faire machine arrière et ne peuvent plus se passer de l'outil. Voyons dans ce châpitre quelques pistes permettant d'expliquer ceci.

### Autocomplétion

L'autocomplétion est une fonctionnalité absolument indispensable à tout bon outil de développement. IDEA non seulement n'échappe pas à la règle, mais propose sans aucun doute la plus puissante dans sa catégorie. Tout d'abord, la complétion "basique" qui consiste à aider le développeur à écrire son code Java fonctionne sans faille. Mais avec IDEA, elle va plus loin. Elle est capable d'aider à compléter le nom des variables ou des classes par exemple. Elle prend également en considération le contexte actuel, ne proposant ainsi que les types qui sont compatibles dans le contexte de la ligne de code courante. IntelliJ IDEA peut ainsi aider le développeur à compléter les requêtes HQL présentes dans des chaînes de caractères dans le code Java.

La puissance de l'auto-complétion ne se borne pas au langage Java, puisqu'il supporte sans broncher les langages web - HTML, CSS ou JavaScript - le XML (il est par exemple capable de compléter les noms des classes Java dans les fichiers Spring), Scala, Groovy, etc. En fait, il n'y a pratiquement aucun endroit où IDEA n'est pas à même de proposer une auto-complétion efficace.

Si le sujet vous intéresse, vous pouvez lire l'article [20 code completions in IntelliJ IDEA](http://jetbrains.dzone.com/articles/top-20-code-completions-in-intellij-idea) (en anglais), ou encore visualiser la vidéo disponible sur la page du site de JetBrains consacrée à l'[auto-complétion](http://www.jetbrains.com/idea/features/code_completion.html).


### Analyse et inspections

IntelliJ IDEA analyse en temps réel et en permanence votre code, à la recherche de problèmes potentiels. À chaque fois qu'il détecte une erreur, IDEA va surligner le problème, et proposera parfois même une solution. De même, lorsqu'IDEA détecte une inconsistence quelconque dans le code, il va proposer, grâce au principe des **inspections** la meilleure correction possible. Ces inspections sont classées selon leur nature. Nous trouvons ainsi des inspections dédiées au style de codage, aux problèmes de performances ou de sécurité, d'autres dédiées à des langages précis (HTML, XML, Groovy, etc.) ou encore à des frameworks particuliers (Guice, GWT, Less, Maven, etc.).

Il existe plusieurs centaines d'inspections disponibles dans IDEA, difficile de les résumer ici, mais en voici quelques exemples :

* Ajout d'un test de non nullité, permettant d'éviter l'apparition de NullPointerException.
* Une condition est toujours fausse (par exemple en testant la nullité d'un objet que l'on a initialisé plus tôt), mettant ainsi en avant du code mort.
* Possibilité de simplifier des expressions booléennes.
* Erreur dans la définition d'une entité Hibernate, par exemple des champs non présents dans la base de données.
* Code inutilisé : imports, variables globales, méthodes privées, propriété d'un fichier *.properties* inutilisée dans l'application, etc.
* Copie manuelle de tableaux.
* Dépendances dupliquées dans les pom.xml de Maven.
* Vérification de la validité des sélecteurs utilisés dans jQuery.
* Détection de problèmes dans la configuration des beans de Spring.


### Outils de refactoring

Les fonctionnalités de refactoring proposées par IDEA en font également sa force. Il est ainsi possible de réaliser en un clic - ou une combinaison de touches - ce genre de choses :

* Déplacement d'un morceau de code sélectionné vers une nouvelle méthode.
* Extraction d'une partie d'une classe vers une nouvelle, pour alléger la première.
* Inversion de conditions booléennes.
* Suppression sécurisée de composants. Lors de la suppression d'une méthode par exemple, IDEA va s'assurer qu'elle n'est plus utilisée dans le projet, et avertira le développeur le cas échéant.

Comme souvent, ces fonctionnalités puissantes ne se limitent pas au langage Java, et sont également présentes pour d'autres langages, comme le XML par exemple. On pourra ainsi renommer des noeuds ou des attributs, convertir des noeuds en attributs, etc.

Vous trouverez plus d'informations sur le refactoring sur [cette page](http://www.jetbrains.com/idea/features/refactoring.html).

### D'autres fonctionnalités avancées


### Références

* [Site officiel]()
* [Détails des fonctionnalités supportées par IDEA](http://www.jetbrains.com/idea/features/index.html)
* [FAQ d'IntelliJ IDEA]()
* [Article de présentation de la v12]()
* []()
* []()
* []()


## Conclusion

Sans être une révolution, cette nouvelle version d'IntelliJ IDEA améliore encore un outil extrêmement bien fait et ultra-productif.
Si vous êtes développeur d'applications Android, alors il ne faut pas hésiter et se jeter (au moins) sur la version **Community**.
Si vous possédez déjà une version précédente de l'outil, il faudra sans doute fouiller un peu dans la liste des nouveautés pour voir si une mise à jour s'avère nécessaire.
Si vous n'avez encore jamais mis les mains sur cet outil, alors il ne faut vraiment pas manquer l'occasion d'y jeter un oeil, soit avec la version **Community**, soit avec la version d'essai de 30 jours de la version **Ultimate**.



