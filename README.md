
Yupik
=====

> A collection of modules inspired by Inuit.css

Revoir nom, pluriels etc ...


Compatibility :
---------------

* SASS 3.3 n'est pas requis, en règle général, j'ai suivi les conseils de l'auteur d'inuit : "[adding advanced Sass features will close this openness back up](https://github.com/inuitcss/CONTRIBUTING)"


Liste dépendances :
-------------------

* Dépendances Inuit.css : seulement les placeholders clearfix et box-sizing sont utilisé pour quelques modules

| Nom         | Vendor   | Yupik    | P | V | P == publish, V = versionné sur github
|-------------|----------|----------|---|---|
| TOOLS       |          |          |   |   |
| ----------- |          |          |   |   |
| function    |          |          | x | x |
|             |          |          |   |   |
| MIXINS      |          |          |   |   |
| ----------- |          |          |   |   |
| vendor      |          |          | x |   |
| position    |          | function | x | x |
| gradient    | compass  | function | x | x |
| shape       | vendor   | function | x | x |
| font        |          | function | x | x |
| placeholder |          | function | x |   |
| transition  | vendor   |          | x | x |
|             |          |          |   |   |
| OBJECTS     |          |          |   |   |
| ----------- |          |          |   |   |
| v-center    | vendor   |          | x |   |
|             |          |          |   |   |
| UI          |          |          |   |   |
| ----------- |          |          |   |   |
| breadcrumb  |          |          | x | x |
| order-list  |          |          | x |   |
| switcher    | vendor   |          |   |   |
| checkbox    | vendor   |          | x | x |
| radio       | vendor   |          |   |   |
| dropdown    | vendor   | shape    | x | x |
|             |          | v-center |   |   |



Notes importantes concernant les mixins :
-----------------------------------------

* Comme en CSS, les paramètres des mixins doivent etre séparé par des espaces (et non pas des virgules)
* Une valeur numérique sera par défault généré en pixel, pour utiliser une autre unité, il faut la précisé

````scss
.element {
    @include absolute(10 50%);
}
````

````css
.element {
    position: absolute;
    left: 10px;
    top: 50px;
}
````

Gestion des dépendances : 
-------------------------
Si Inuit.css propose aussi de gérer les dépendances avec GitSubmodule, Yupik n'est prévu pour l'instant qu'avec l'usage de Bower : si vous ne connaisser pas encore, lizer le [Getting Started](https://github.com/inuitcss/getting-started#new-to-bower).
Penser à faire un ````bower init```` en début de projet et d'instaler en ajoutant le flag ````--save```` :
````$ bower install --save yupik-[module]````



Exemples UI : 
-------------
* dropdown : ajout mixin triangle et précisé de quel module est vient (pour l'instant, pas dépendances externes)
* 


TODO :
------
* voir mettre dans readme chaque module "part of repository of Yupik module", inspired by inuitcss
* changer de certain element ui de la couleur corporate de yupik (celle par défaut)
* préciser que la majorité des élements peuvent etre utiliser avec placeholder (mais normalement inutile puisque si besoin on peux préfixer)