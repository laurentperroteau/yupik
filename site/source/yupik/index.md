title: yupik
date: 2014-12-20 11:18:17
---

This is a french version, [english version here](https://github.com/laurentperroteau).

Qu'est-ce que Yupik :
---------------------

Yupik est une [collection de modules](https://github.com/yupik) inspirés par (et qui complète) [Inuit.css](https://github.com/inuitcss/getting-started).

Donc qu'est-ce que Inuit.css :

C'est un framework ultra-léger purement CSS (pas de JavaScript) basé sur SASS (syntaxe SCSS), orienté objet, évolutif et modulable, destinés aux développeurs Front-End. Il utilise la convention de nommage BEM, sépare les modèles indépendamment, est compatible IE8+ et est plein de bonne pratique.


Cette dernière version de Inuit ( la [version 5](https://github.com/csswizardry/inuit.css) n'est plus maintenue mais fonctionne très bien) liste simplement [des modules](https://github.com/inuitcss) qu’il faudra importer dans votre CSS. Pour tester, commencer par le [Starter Kit](https://github.com/inuitcss/starter-kit).


Liste des modules : 
-------------------

* TOOLS :
* [Function](https://github.com/laurentperroteau/yupik-function) : la fonction "Responsive" et autres fonctions utilisées dans les mixins
* MIXINS :
* Vendor : mixin qui génère les "vendor prefixes"
* [Position](https://github.com/laurentperroteau/yupik-mixin-position) : mixins qui simplifie l'utilisation de la propriété "position"
* [Font](https://github.com/laurentperroteau/yupik-mixin-font) : mixins qui simplifie la déclaration de police
* [Shape](https://github.com/laurentperroteau/yupik-mixin-shape) : mixins pour créer des formes
* [Gradient](https://github.com/laurentperroteau/yupik-mixin-gradient) : mixin qui génère un dégradé linéaire compatible IE7+ avec Compass
* Placeholder : styler le placeholder des inputs
* [Transition](https://github.com/laurentperroteau/yupik-mixin-transition) : CSS3 placeholders de transition
* OBJECTS :
* Vertical center : centrer verticalement presque n'importe quoi
* UI ELEMENTS :
* [Checkbox](https://github.com/laurentperroteau/yupik-checkbox) : styler des cases à cocher sans JavaScript et sans perdre l'expérience utilisateur [__DEMO__](http://codepen.io/laurentperroteau/pen/vEKQbo?editors=110)
* [Dropdown](https://github.com/laurentperroteau/yupik-dropdown) : Styler l'élément &lt;select&gt; facilement sans perdre l'expérience utilisateur [__DEMO__](http://codepen.io/laurentperroteau/pen/ZYOmPv?editors=110)
* [Breadcrumb](https://github.com/laurentperroteau/yupik-breadcrumb) : styler un file d'arianne en forme de fleche [__DEMO__](http://codepen.io/laurentperroteau/pen/bNeQxp?editors=110)


Comment utiliser les modules :
------------------------

Il suffit d'importer dans votre fichier SCSS, le module en le précédent (si besoin) des variables de configuration (exemple avec l'[objects.media](https://github.com/inuitcss/objects.media) d'Inuit) :

````scss
$inuit-enable-media--flush: true;
@import "bower_components/inuit-media/objects.media";
````

Yupik fonctionne de la meme manière :

````scss
$yupik-checkbox-radius: 3px;
@import "bower_components/yupik-checkbox/ui.checkbox";
````

Les modules ne doivent pas être modifié et ne devraient pas être versionné... les configurations sont suffisantes et vous n'aurez pas à surcharger de style.

On peut également préfixer les classes d'un "namespace" : soit celui global à tout Inuit ou un particulier à chaque module.

 
Prérequis :
--------------

 1 - SASS (la version 3.3 n'est pas obligatoire), optionnellement Node.js et Bower
 2 - Yupik s'inspire de Inuit.css mais n'en dépend pas (à l'exception des modules clearfix et box-sizing)



Gestion des dépendances : 
-------------------------

Yupik (comme Inuit.css) utilise [Bower](http://bower.io). Si vous ne connaissez pas encore, lisez le [Getting Started, new to Bower ?](https://github.com/inuitcss/getting-started#new-to-bower)

    $ bower init
    $ bower install --save yupik-[module]


Notes importantes concernant les mixins :
-----------------------------------------

* Comme en CSS, les paramètres des mixins doivent être séparé par des espaces (et non par des virgules)
* Une valeur numérique sera par défaut généré en pixel, pour utiliser une autre unité, il faut la préciser :

````scss
.element {
    @include absolute(10 50%);
}

/* Generated style */
.element {
    position: absolute;
    left: 10px;
    top: 50%;
}
````