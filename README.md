
Yupik
=====

A collection of modules inspired by Inuit.css
=============================================

## reworking in progress !

<!--This is a french version, [english version here](https://github.com/laurentperroteau).-->

What Yupik:
-----------

At first, what [Inuit.css](https://github.com/inuitcss/getting-started) :

It's a lightweight framework purely CSS (no JavaScript) based on SASS (SCSS syntax), object-oriented, scalable and modular, for front-end developers. It uses the BEM naming convention, separates the models independently, compatibility IE8 + and have a lot of good practice.


Cette dernière version de Inuit ( la [version 5](https://github.com/csswizardry/inuit.css) n'est plus maintenue mais fonctionne très bien) liste simplement [des modules](https://github.com/inuitcss) qu’il faudra importer dans votre CSS. Pour tester, commencer par le [Starter Kit](https://github.com/inuitcss/starter-kit).

This lastest version of Inuit (the [V5](https://github.com/csswizardry/inuit.css) is no longer maintained, but works very well) simply list [modules](https://github.com / inuitcss) import requirement in your CSS. To test, try [Starter Kit](https://github.com/inuitcss/starter-kit).


Liste of modules: 
-----------------

* TOOLS :
* [Function](https://github.com/laurentperroteau/yupik-function) : "response" function and other functions only useful to mixin
* MIXINS :
* Vendor : mixin that generate "vendor prefixes"
* [Position](https://github.com/laurentperroteau/yupik-mixin-position) : mixins that simplified the use of "position" property
* [Font](https://github.com/laurentperroteau/yupik-mixin-font) : mixins that simplified fonts declarations
* [Shape](https://github.com/laurentperroteau/yupik-mixin-shape) : mixins to create shape
* [Gradient](https://github.com/laurentperroteau/yupik-mixin-gradient) : mixin which applied a linear cross-browsers solution (IE7+) with Compass
* Placeholder : styling placeholder of inputs
* [Transition](https://github.com/laurentperroteau/yupik-mixin-transition) : useful placeholders for CSS3 transition
* OBJECTS :
* Vertical center : center vertically almost everything
* UI ELEMENTS :
* [Checkbox](https://github.com/laurentperroteau/yupik-checkbox) : styling checkbox without JavaScript and without lose user experience [__DEMO__](http://codepen.io/laurentperroteau/pen/vEKQbo?editors=110)
* [Dropdown](https://github.com/laurentperroteau/yupik-dropdown) : styling &lt;select&gt; element easily without lose user experience [__DEMO__](http://codepen.io/laurentperroteau/pen/ZYOmPv?editors=110)
* [Breadcrumb](https://github.com/laurentperroteau/yupik-breadcrumb) : styling arrow-shaped breadcrumb [__DEMO__](http://codepen.io/laurentperroteau/pen/bNeQxp?editors=110)


How to use the modules:
-----------------------

Symply import them in your SCSS file, preceded with configuration variable (if needed) (eg with the Inuit [objects.media](https://github.com/inuitcss/objects.media)) :

````scss
$inuit-enable-media--flush: true;
@import "bower_components/inuit-media/objects.media";
````

Yupik works the same way :

````scss
$yupik-checkbox-radius: 3px;
@import "bower_components/yupik-checkbox/ui.checkbox";
````

The modules must not be modified and should not be versioned ... configurations are sufficient and you will not have to overload style.

It's also possible use a "namespace" to prefix classes : either the Inuit global namespace or an own namespace to each module..

 
Prérequis:
----------

 1 - SASS (version 3.3 is not required), optionally Node.js and Bower
 2 - Yupik is inspired by Yupik Inuit.css but do not depend (except clearfix and box-sizing modules)


Dependency management: 
----------------------

Yupik (as Inuit.css) uses [Bower](http://bower.io). If you don't already know, read the [Getting Started, new to Bower ?](https://github.com/inuitcss/getting-started#new-to-bower)

    $ bower init
    $ bower install --save yupik-[module]


Important notes about mixins:
-----------------------------

* As in CSS, mixins parameters must be separated by spaces (not commas)
* A numerical value will default generated pixel, to use another unit, it must specify:

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