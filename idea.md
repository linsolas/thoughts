# Test d'IntelliJ IDEA v13

Cet article a pour but de montrer les nouveautés apportées par la 13e version d'IntelliJ IDEA de JetBrains, et de présenter quelques unes de ses forces en tant qu'outil de développement.

## Qu'est-ce qu'IntelliJ

Faisons en premier lieu un rapide tour de l'outil.

### Introduction

Depuis janvier 2001, la société [JetBrains](http://www.jetbrains.com/) édite le logiciel [IntelliJ IDEA](http://www.jetbrains.com/idea/). Il s'agit d'un *EDI* (ou *IDE* en anglais), à savoir un *Environnement de Développement Intégré* (*Integrated Development Environment*), autrement dit un ensemble d'outils déstiné au développement logiciel. IDEA est ainsi à mettre au même niveau - toutes proportions gardées - d'[Eclipse](http://www.eclipse.org/) ou encore de [NetBeans](http://www.netbeans.org/).

Pour information, **IntelliJ** fait référence à la plateforme commune de JetBrains pour tous leurs outils de développement, IDEA étant l'EDI de développement Java. Il est donc plus juste de dire "je travaille avec IDEA" que "je travaille sur IntelliJ", bien que ce soit souvent la seconde phrase la plus courante.


### Versions et prix

IDEA existe en deux versions : **Community** et **Ultimate**. Pour faire simple, la version **Community**, gratuite, est avant tout destinée au développement d'applications "lourdes" Java, Scala et Android. Dès qu'il s'agit de développer des applications web, il faut se tourner vers l'édition **Ultimate**. Son prix, pour une licence personnelle, est de 179€ (hors promotion ou prix de mise à jour).

Un comparatif complet des deux éditions est visible [ici](http://www.jetbrains.com/idea/features/editions_comparison_matrix.html).

Vous pouvez télécharger l'une des deux versions sur la [page dédiée](http://www.jetbrains.com/idea/download/). Notez au passage qu'IntelliJ IDEA est compatible Windows, Mac et Linux.


### Principales fonctionnalités

Je ne vais pas détailler ici toutes les fonctionnalités d'IDEA, il me faudrait un livre entier pour cela. Je passe toutefois en revue les principales fonctionnalités et langages, frameworks ou outils supportés.

#### Langages et framework supportés

La version **Community** gère nativement les langages suivants : Java, Scala, Groovy, Clojure et XML, XSD et DTD. Avec la version **Ultimate** s'ajoutent les langages dédiés au développement web, à savoir le HTML, CSS, JavaScript, CoffeeScript, ActionScript. Viennent également le support du Freemarker, de Velocity, du XSL, XPath, SQL, Ruby et JRuby, Python ou encore PHP.
Certains de ces langages nécessitent toutefois l'ajout de plugins gratuits.

Avec la version **Ultimate** vient également le support des frameworks les plus courants pour le développement autour de l'écosystème de la JVM ou du web. On citera par exemple Spring, Play! framework, JavaEE 6, GWT, Hibernate, Struts, Grails, Griffon, Sass, LESS, Rails, Django, Node.js, etc.

#### Gestionnaires de sources

Si vous travaillez sur CVS (désolé pour vous), SVN, Mercurial ou Git (ou GitHub), alors la version **Community** sera suffisante pour vous. Si vous avez Team Foundation Server, Perforce, ClearCase ou encore Visual SourceSafe, c'est vers la version **Ultimate** qu'il vous faudra vous tourner.

#### Outils de construction

Les principaux outils de construction d'applications sont présents dans les deux éditions d'IDEA. On y retrouve ainsi Maven, Grandle, Ant et Gant Build Tools.

#### Développement et autres fonctions

Pour ce qui concerne le développement à proprement parler, IDEA offre une excellente intégration des outils de tests (JUnit, TestNG, Spock ou encore Cucumber), un historique local des modifications de fichiers, une intéropérabilité avec Eclipse, ou encore un gestionnaire de contexte. Ce dernier permet de travailler sur un ticket JIRA (ou n'importe quel autre gestionnaire de tickets) et d'y associer un contexte. Ainsi, lorsque l'on rouvre un ticket JIRA sur lequel on avait déjà commencé à travailler, IDEA va rouvrir les fichiers qui étaient ouverts lorsque le contexte de ce ticket avait été précédemment fermé. Si vous êtes adeptes de [Mylyn](http://www.eclipse.org/mylyn/) sur Eclipse, cette fonction devrait vous intéresser. Vous pouvez voir [ici](http://www.jetbrains.com/idea/features/tasks_and_context.html) pour plus de détails (en anglais).
A ce propos, IDEA s'interface sans problème avec les plus populaires des systèmes de tickets : JIRA, YouTrack, Lighthouse, GitHub, Redmine, Trac, etc.

Si vous possédez la version **Ultimate**, vous disposerez également d'un gestionnaire complet de base de données (éditeur SQL, définition de schémas, diagrammes, etc.), d'un designeur UML, d'outils de couverture de code, du "Structural Search and Replace" (voir le chapitre dédié plus loin).


L'intégralité des fonctionnalités d'IDEA est à trouver sur [cette page](http://www.jetbrains.com/idea/features/index.html).



## Les nouveautés de la version 13

Comme à chaque fin d'année, JetBrains publie sa nouvelle version majeure de son EDI. 2013 n'échappe pas à la règle, et a vu la version 13 de l'outil sortir. Quelles sont les principales nouveautés de cette version ? C'est ce que nous allons voir.

### Android Studio

Les développeurs d'applications mobiles pour Android vont être contents. Annoncé lors du [Google I/O de 2013](https://developers.google.com/events/io/), IDEA est désormais l'EDI standard pour le développement d'applications mobiles pour l'OS de Google.

![Android Studio](http://www.jetbrains.com/idea/whatsnew/img/13/android_multiple_devices_preview.png "Andoid Studio")

Cet Android Studio se compose de différents éléments :

* Éditeur visuel pour la partie graphique des applications.
* Émulateur d'appareils Android.
* Meilleure intégration de [Gradle](http://www.gradle.org/), l'outil de construction des applications Android.
* Éditeur XML dédié à Android.
* Outil d'inspection Lint, pour analyser la qualité du code.

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

![Client REST intégré](http://www.jetbrains.com/idea/whatsnew/img/13/rest_client.png "Client REST intégré")

Pour ce qui est de Spring, le support déjà bien présent dans les précédentes versions est encore amélioré. On y retrouve une meilleure gestion de Spring MVC permettant une navigation aisée entre les controlleurs et les pages HTML associées, la détection des contextes non mappés et annotés avec @Context, ou encore des améliorations sur la performances, la documentation ou les fenêtres spécifiques à Spring (telle que celle de la vue des beans).


### Langages alternatifs

Déjà bien supportés dans la précédente version, le support pour Scala ou Groovy s'améliore encore.

Pour Groovy, différentes fonctionnalités de refactoring ont été mises en place, comme l'introduction de variables ou de constantes. IDEA propose désormais la possibilité de créer des tests avec la librairie [Spock](https://code.google.com/p/spock/). Différents nouveaux inspecteurs ont également été introduits.

Concernant Scala, IDEA offre le support de l'outil [sbt](http://www.scala-sbt.org/), des options de réorganisation du code ou encore la génération de méthodes de base (telles que *hashCode* ou *equals*).

![Réarrangeur de code Scala](http://www.jetbrains.com/idea/whatsnew/img/13/scala_rearranger.png "Réarrangeur de code Scala")

### Développement web

Vous l'aurez deviné, les fonctionnalités propres au développement web ne sont disponibles que pour la version **Ultimate**. Les nouveautés sont entre autres :

* Débogeur JavaScript amélioré, en particulier pour Google Chrome et [Node.js](http://nodejs.org/).
* Amélioration du refactoring CSS.
* Support de la librairie de test [Karma](https://github.com/karma-runner/karma).
* Support de la version 1.0 de [Dart](https://www.dartlang.org/).
* Début de l'intégration du futur standard des [composants web](http://www.w3.org/TR/components-intro/).
* Gestion des langages de *templating* [Moustache](http://mustache.github.io/) ou [Handlebars](http://handlebarsjs.com/).


### Généralités

Pour ce qui est des gestionnaires de sources, différentes améliorations sont apportées pour Git ou Mercurial. On notera ainsi l'ajout d'une fonctionnalité de "pull-request" pour GitHub.
Pour celles et ceux qui sont encore sur Subversion (SVN), ils seront heureux d'apprendre qu'IDEA est enfin compatible avec Subversion 1.8.

Concernant l'interface graphique, différentes améliorations ont été apportées, les thèmes Darcula et *Light* étant toujours présents. À noter la présence d'un mode "Présentation" qui ravira celles et ceux qui font des présentations techniques et qui doivent montrer du code. 

Dans l'optique d'avoir tout sous la main dans un même outil, IDEA intègre désormais la possibilité d'exécuter des commandes shell localement ou à distance (*via* une connexion SSH) directement par la vue "Ligne de commandes".

![Un terminal est intégré à IDEA](http://www.jetbrains.com/idea/whatsnew/img/13/ij13_terminal.png "Un terminal est intégré à IDEA")

Pour améliorer la productivité, la nouvelle fonction de recherche permet d'accéder à pratiquement tout à travers la même fenêtre : classe, méthode, action, paramétrage, etc.

![Une recherche vraiment complète](http://www.jetbrains.com/idea/whatsnew/img/13/ij13_search.png "Une recherche vraiment complète")

Vous pouvez retrouver toutes ces nouveautés, et bien plus encore sur la [page dédiée du site de JetBrains](http://www.jetbrains.com/idea/whatsnew/index.html).


## Ce qui fait la force d'IntelliJ

On reproche souvent à IntelliJ IDEA d'être payant et d'avoir un prix relativement élevé. Une licence unique coûte 179€ si elle est personnelle, 449€ s'il s'agit d'une licence d'entreprise. Pour cette dernière, cela représente généralement moins d'une journée de prestation et cela risque de lui en faire gagner bien plus.

Ceux qui ont vraiment goûté à cet EDI, comme moi, n'ont plus envie de faire machine arrière et ne peuvent plus se passer de l'outil. Voyons dans ce châpitre quelques pistes permettant d'expliquer ceci.

### L'autocomplétion

L'autocomplétion est une fonctionnalité absolument indispensable à tout bon outil de développement. IDEA non seulement n'échappe pas à la règle, mais propose sans aucun doute la plus puissante dans sa catégorie. Tout d'abord, la complétion "basique" qui consiste à aider le développeur à écrire son code Java fonctionne sans faille. Mais avec IDEA, elle va plus loin. Elle est capable d'aider à compléter le nom des variables ou des classes par exemple. Elle prend également en considération le contexte actuel, ne proposant ainsi que les types qui sont compatibles dans le contexte de la ligne de code courante. IntelliJ IDEA peut ainsi aider le développeur à compléter les requêtes HQL présentes dans des chaînes de caractères dans le code Java.

![Une autocomplétion vraiment performante](http://www.jetbrains.com/idea/features/screenshots/database_injection.png "Une autocomplétion vraiment performante")

La puissance de l'auto-complétion ne se borne pas au langage Java, puisqu'il supporte sans broncher les langages web - HTML, CSS ou JavaScript - le XML (il est par exemple capable de compléter les noms des classes Java dans les fichiers Spring), Scala, Groovy, etc. En fait, il n'y a pratiquement aucun endroit où IDEA n'est pas à même de proposer une auto-complétion efficace.

Si le sujet vous intéresse, vous pouvez lire l'article [20 code completions in IntelliJ IDEA](http://jetbrains.dzone.com/articles/top-20-code-completions-in-intellij-idea) (en anglais), ou encore visualiser la vidéo disponible sur la page du site de JetBrains consacrée à l'[auto-complétion](http://www.jetbrains.com/idea/features/code_completion.html).


### Analyse et inspections

IntelliJ IDEA analyse en temps réel et en permanence votre code, à la recherche de problèmes potentiels. À chaque fois qu'il détecte une erreur, IDEA va surligner le problème, et proposera parfois même une solution. De même, lorsqu'IDEA détecte une inconsistence quelconque dans le code, il va proposer, grâce au principe des **inspections** la meilleure correction possible. Ces inspections sont classées selon leur nature. Nous trouvons ainsi des inspections dédiées au style de codage, aux problèmes de performances ou de sécurité, d'autres dédiées à des langages précis (HTML, XML, Groovy, etc.) ou encore à des frameworks particuliers (Guice, GWT, Less, Maven, etc.).

Il existe plusieurs centaines d'inspections disponibles dans IDEA, difficile de les résumer ici, mais en voici quelques exemples :

* Ajout d'un test de non nullité, permettant d'éviter l'apparition de ```NullPointerException```.
* Une condition est toujours fausse (par exemple en testant la nullité d'un objet que l'on a initialisé plus tôt), mettant ainsi en avant du code mort.
* Possibilité de simplifier des expressions booléennes.
* Erreur dans la définition d'une entité Hibernate, par exemple des champs non présents dans la base de données.
* Code inutilisé : imports, variables globales, méthodes privées, propriété d'un fichier ```.properties``` inutilisée dans l'application, etc.
* Copie manuelle de tableaux non optimisée.
* Dépendances dupliquées dans les ```pom.xml``` de Maven.
* Vérification de la validité des sélecteurs utilisés dans jQuery.
* Détection de problèmes dans la configuration des beans de Spring.

![Un exemple de code potentiellement erroné détecté par IDEA](http://www.jetbrains.com/idea/features/screenshots/code_analysis_dead.png "Un exemple de code potentiellement erroné détecté par IDEA")

Il est toujours possible d'exécuter une inspection sur l'ensemble du projet, et parfois même de faire exécuter automatiquement la correction si celle-ci existe. Par exemple, je peux demander à IDEA tous les endroits où j'ai un ```size() == 0``` qui pourrait être remplacé par un ```isEmpty()```. IDEA va alors me lister tous les endroits où il trouve ```uneListe.size() == 0```, mais aussi là où il va trouver ```uneListe.size() > 0``` et me proposer de le remplacer par un ```uneListe.isEmpty()``` (ou ```!uneListe.isEmpty()``` dane le deuxième cas). Tout cela en un seul clic !

![On peut lancer toutes les inspections d'un coup sur l'ensemble du projet](http://www.jetbrains.com/idea/features/screenshots/code_analysis_batch.png "On peut lancer toutes les inspections d'un coup sur l'ensemble du projet")

Avec tout cela, IDEA va devenir votre ami préféré pour écrire du joli code bien propre...


### Outils de refactoring

Les fonctionnalités de refactoring proposées par IDEA en font également sa force. Il est ainsi possible de réaliser en un clic - ou une combinaison de touches - ce genre de choses :

* Déplacement d'un morceau de code sélectionné vers une nouvelle méthode.
* Extraction d'une partie d'une classe vers une nouvelle, pour alléger la première.
* Inversion de conditions booléennes.
* Suppression sécurisée de composants. Lors de la suppression d'une méthode par exemple, IDEA va s'assurer qu'elle n'est plus utilisée dans le projet, et avertira le développeur le cas échéant.

Comme souvent, ces fonctionnalités puissantes ne se limitent pas au langage Java, et sont également présentes pour d'autres langages, comme le XML par exemple. On pourra ainsi renommer des noeuds ou des attributs, convertir des noeuds en attributs, etc.

Vous trouverez plus d'informations sur le refactoring sur [cette page](http://www.jetbrains.com/idea/features/refactoring.html).

### SSR, ou Structural Search and Replace

Le *Structural Search and Replace* (autrement dit la recherche et remplacement structurels) est un outil qui n'est pas toujours facile à manier mais diablement efficace. Il n'est d'ailleurs disponible que dans la version **Ultimate**.

Il est parfois nécessaire de faire une recherche un peu complexe dans tout le code de son application. Cela peut-être une classe (```class A implements B { }```), une déclaration (```a = b```), un commentaire (```// TODO A faire```) ou une expression (```new MaClasse();```). Bref, des choses qu'une simple recherche n'est pas capable de trouver. Et bien c'est le rôle du SSR. On ne lui donne pas un texte à chercher, mais plutôt un *template*.
Prennons un exemple. Je souhaite utiliser la librairie [AssertJ](https://github.com/joel-costigliola/assertj-core) pour rendre mes assertions plus expressives dans mes tests unitaires. Avec JUnit, mon assertion s'écrit ```assertEquals(42, unEntier)```, alors qu'avec AssertJ, ce sera ```assertThat(unEntier).isEqualTo(42)```. Si je souhaite faire un changement automatique de toutes mes assertions en une seule fois, je vais avoir du mal avec une recherche normale. Avec le SSR, je peux faire cela en un clin d'oeil. Tout d'abord, je saisis le template suivant :

	assertEquals($a$, $b$);

Vous noterez l'utilisation de variables ```$a$``` et ```$b$```. Ensuite, je lui indique par quoi remplacer :

	assertThat($b$).isEqualTo($a$);

Et le tour est joué ! Pour être sûr de ne pas faire d'erreur, IDEA me montre une prévisualisation des changements avant de les appliquer.

Pour vous aider, il existe un certain nombre de templates prédéfinis, sur lesquels il sera plus prudent de partir pour arriver à ses fins.


Vous pouvez jeter un oeil sur [la documentation du SSR](http://www.jetbrains.com/idea/documentation/ssr.html) (en anglais).

## Petits conseils pour bien migrer vers IntelliJ IDEA

Fin 2012, j'ai acheté la version 12 d'IntelliJ, bien décidé à m'y mettre pour de vrai. J'avais déjà essayé par le passé d'y jeter un oeil, mais mes habitudes sur Eclipse ont eu raison de toutes mes tentatives. Mais cette fois-ci fût la bonne, et je ne voudrais jamais avoir à faire machine arrière ! Pour vous aider à franchir le pas, voilà quelques petites astuces.

Tout d'abord, il faut persévérer un peu. C'est vrai qu'il est parfois destabilisant de quitter un outil - en l'occurrence Eclipse - dans lequel on a pris ses habitudes au fil des ans, mais croyez-moi, cette fois c'est pour votre bien !

Premier point : la vue "Workspace" d'Eclipse disparait. IDEA ne gère qu'un seul projet à la fois par fenêtre (il est toutefois possible d'ouvrir autant de fenêtre d'IDEA que voulu). Finalement, ce n'est guère gênant, sauf si on a l'habitude de travailler sur dix projets *en même temps* (mais là, il y a sans doute un problème, non ?).

Autre chose : les raccourcis clavier. On ne peut pas travailler efficacement sur un outil sans en connaître les raccourcis clavier, du moins les principaux. IDEA propose une option pour faire correspondre autant que possible les raccourcis claviers à ceux d'Eclipse ou de NetBeans. Pour cela, il faut aller dans *Settings > Keymap* puis choisir *Eclipse* ou *NetBeans* dans le sélecteur *Keymaps*. Toutefois, je vous conseille vivement de laisser les raccourcis par défaut et de les apprendre. Pour vous aider, vous pouvez télécharger et imprimer un [pense-bête](http://www.jetbrains.com/idea/docs/IntelliJIDEA_ReferenceCard.pdf) ([la version pour Mac](http://www.jetbrains.com/idea/docs/IntelliJIDEA_ReferenceCard_Mac.pdf)) ou pourquoi pas vous [acheter un t-shirt](http://www.ptxstore.com/jetbrains/product_info.php?products_id=1638).

![T-shirt JetBrains](http://www.ptxstore.com/jetbrains/images/CUJB12S-M10.jpg "T-shirt JetBrains")

Il existe aussi le raccourci "universel", Ctrl + Shift + A, qui vous permet d'exécuter n'importe quelle action en tapant simplement son nom. Enfin, je vous recommande le plugin "[Key Promoter](http://plugins.jetbrains.com/plugin/1003?pr=idea)" qui détecte quand vous réalisez une action alors qu'un raccourci clavier existe. Dans pareille situation, le plugin va afficher une popup vous indiquant le raccourci à utiliser pour gagner du temps. C'est très pratique.

Si certaines personnes de votre équipe travaillent toujours sur Eclipse (les pauvres !), alors il faudra peut-être penser à ajouter [le plugin de formattage d'Eclipse](http://plugins.jetbrains.com/plugin/6546), ce qui vous assurera d'avoir les mêmes conventions que vos camarades. A noter aussi qu'il aussi est possible [de demander à IDEA de sauvegarder les méta-données du projet au format Eclipse](http://www.jetbrains.com/idea/features/eclipse_java.html) (fichier ```.classpath```) plutôt qu'IDEA (fichier ```*.iml```).


Quoiqu'il en soit, si vous vous sentez perdus, n'hésitez pas à consulter la [F.A.Q.](http://java.developpez.com/faq/intellijidea) ou [le forum dédié](http://www.developpez.net/forums/f1871/java/edi-outils-java/autres-edi/intellij/) de Developpez.com.


D'autres conseils sur [la page dédiée](http://confluence.jetbrains.com/display/IntelliJIDEA/IntelliJ+IDEA+for+Eclipse+Users) de JetBrains (en anglais). [Une page similaire](http://confluence.jetbrains.com/display/IntelliJIDEA/IntelliJ+IDEA+for+NetBeans+Users) existe si vous êtes un utilisateur de NetBeans.

## Conclusion

Sans être une révolution, cette nouvelle version d'IntelliJ IDEA améliore encore un outil extrêmement bien fait et ultra-productif.
Si vous êtes développeur d'applications Android, alors il ne faut pas hésiter et se jeter (au moins) sur la version **Community**.
Si vous possédez déjà une version précédente de l'outil, il faudra sans doute fouiller un peu dans la liste des nouveautés pour voir si une mise à jour s'avère nécessaire.
Si vous n'avez encore jamais mis les mains sur cet outil, alors il ne faut vraiment pas manquer l'occasion d'y jeter un oeil, soit avec la version **Community**, soit avec la version d'essai de 30 jours de la version **Ultimate**.



### Références

* [Site officiel](http://www.jetbrains.com/idea/)
* [Détails des fonctionnalités supportées par IDEA](http://www.jetbrains.com/idea/features/index.html)
* [Détails des nouveautés de la version 13](http://www.jetbrains.com/idea/whatsnew/index.html)
* [FAQ d'IntelliJ IDEA sur Developpez.com](http://java.developpez.com/faq/intellijidea)
* [Article de présentation de la v12](http://damienrieu.developpez.com/tutoriel/java/nouveautes-intellij-12/)
* [Forum IntelliJ de Developpez.com](http://www.developpez.net/forums/f1871/java/edi-outils-java/autres-edi/intellij/)


