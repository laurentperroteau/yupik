title: yupik
date: 2014-12-20 11:18:17
---

<a class="repo" href="https://github.com/laurentperroteau/yupik" target="_blank">Github</a>

This is a french version, [english version on Github](https://github.com/laurentperroteau/yupik).

Qu'est-ce que Yupik :
---------------------

Yupik est une [collection de modules](https://github.com/yupik) inspirés par (et qui complète) [Inuit.css](https://github.com/inuitcss/getting-started).

Donc qu'est-ce que Inuit.css :

C'est un framework ultra-léger purement CSS (pas de JavaScript) basé sur SASS (syntaxe SCSS), orienté objet, évolutif et modulable, destinés aux développeurs Front-End. Il utilise la convention de nommage BEM, sépare les modèles indépendamment, est compatible IE8+ et plein de bonne pratique.

Cette dernière version de Inuit liste simplement [des modules](https://github.com/inuitcss) qu’il faudra importer dans votre CSS. Pour tester, commencer par le [Starter Kit](https://github.com/inuitcss/starter-kit) (la [version 5](https://github.com/csswizardry/inuit.css) n'est plus maintenue mais fonctionne très bien).



Liste des modules : 
-------------------

* TOOLS:
* [Function](https://github.com/laurentperroteau/yupik-function):  la fonction "Responsive" et autres fonctions utilisées dans les mixins
* MIXINS:
* [Vendor](https://github.com/laurentperroteau/yupik-mixin-vendor) : mixin qui génère les "vendor prefixes" (voir note concernant les “vendor prefixes”)
* [Position](https://github.com/laurentperroteau/yupik-mixin-position) : mixins qui simplifie l'utilisation de la propriété "position"
* [Font](https://github.com/laurentperroteau/yupik-mixin-font) : mixins qui simplifie la déclaration de police
* [Shape](https://github.com/laurentperroteau/yupik-mixin-shape) : mixins pour créer des formes
* [Gradient](https://github.com/laurentperroteau/yupik-mixin-gradient) : mixin qui génère un dégradé linéaire compatible IE7+ avec Compass
* [Placeholder](https://github.com/laurentperroteau/yupik-mixin-placeholder) : styler le placeholder des inputs
* [Transition](https://github.com/laurentperroteau/yupik-mixin-transition) : CSS3 placeholders de transition (équivalent des slide up/down et fade in/out de jQuery en CSS3)
* OBJECTS:
* [Vertical center](https://github.com/laurentperroteau/yupik-vertical-center) : centrer verticalement presque n'importe quoi
* UI ELEMENTS:
* [Checkbox](https://github.com/laurentperroteau/yupik-checkbox) : styler des checkbox sans JavaScript et sans perdre l'expérience utilisateur [__DEMO__](http://codepen.io/laurentperroteau/pen/vEKQbo?editors=110)
* [Radio](https://github.com/laurentperroteau/yupik-radio) : stylé des boutons radios without JavaScript and without lose user experience [__DEMO__](http://codepen.io/laurentperroteau/pen/bNwKbL?editors=110)
* [Dropdown](https://github.com/laurentperroteau/yupik-dropdown) : styler l'élément &lt;select&gt; facilement sans perdre l'expérience utilisateur [__DEMO__](http://codepen.io/laurentperroteau/pen/ZYOmPv?editors=110)
* [Breadcrumb](https://github.com/laurentperroteau/yupik-breadcrumb) : styler un file d'arianne en forme de fleche [__DEMO__](http://codepen.io/laurentperroteau/pen/bNeQxp?editors=110)
* [Order-list](https://github.com/laurentperroteau/yupik-order-list) : styler une liste ordonée avec un numéro (ou autre) dans un cercle


Comment utiliser les modules :
------------------------------

Il suffit d'importer le module dans votre fichier SCSS en le précédent (si besoin) des variables de configuration (exemple avec l'[objects.media](https://github.com/inuitcss/objects.media) d'Inuit) :

````scss
$inuit-enable-media--flush: true;
@import "bower_components/inuit-media/objects.media";
````

Yupik fonctionne de la même manière :

````scss
$yupik-checkbox-radius: 3px;
@import "bower_components/yupik-checkbox/ui.checkbox";
````

Les modules ne doivent pas être modifié et ne devraient pas être versionné... les configurations sont suffisantes et vous n'aurez pas à surcharger de style.

On peut également préfixer les classes d'un "namespace" : soit celui global à tout Inuit ou un particulier pour chaque module.

 
Pré requis :
------------

* SASS (la version 3.3 n'est pas obligatoire), optionnellement Node.js et Bower
* Yupik s'inspire de Inuit.css mais n'en dépend pas (à l'exception des modules très général clearfix et box-sizing)



Gestion des dépendances : 
-------------------------

Yupik (comme Inuit.css) utilise [Bower](http://bower.io). Si vous ne connaissez pas encore, lisez le [Getting Started, new to Bower ?](https://github.com/inuitcss/getting-started#new-to-bower).

    $ bower init
    $ bower install --save yupik-[module]

Si vous ne souhaitez pas dépendre de dépôt externe, il est préférable de les installer tout de même avec Bower pour s'assurer d'avoir les bonnes versions et d'ensuite les copier dans votre projet.


Note concernant les "vendor prefixes" :
---------------------------------------

Yupik recommande l'utilisation de [Autoprefixer](https://github.com/postcss/autoprefixer), c'est pour cette raison que la génération des préfixes est désactivé par défaut. Si vous ne l'utilisez pas, la mixin "vendor" a été prévu, il suffit de l'activer :

````scss
$yupik-vendor: true;
@import "bower_components/yupik-mixin-vendor/mixins.vendor";
````

Notes importantes concernant les mixins :
-----------------------------------------

* Comme en CSS, les paramètres des mixins doivent être séparé par des espaces (et non par des virgules)
* Une valeur numérique sera par défaut généré en pixel, pour utiliser une autre unité, il faut la préciser :

````scss
.element {
    @include absolute(10 50%);
}

/* Style generated */
.element {
    position: absolute;
    left: 10px;
    top: 50%;
}
````