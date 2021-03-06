# Formules magiques

Ici vous trouverez tous les ingrédients que nous allons utiliser pour notre PONG. On n'utilisera pas dès le premier cours tout ce qui est listé ici mais je vous demanderai de lire en diagonale cette page afin d'aller y piocher le moment venu ce qu'il vous faut.

Dans ce document, on ne rentre pas dans le détail, ce sera à vous de vous documenter grâce aux liens fournis si vous voulez aller plus loin.
Si vous voulez une approche plus exhaustive [je vous conseille ce cours](https://developer.mozilla.org/fr/docs/Learn/JavaScript/First_steps)

Pour se donner du courrage, dites vous que si vous maîtrisez bien tout ce qui est expliqué ici, que tout cela devient naturel c'est que vous serez prêts à faire n'importe quoi en javascript si vous y consacrez un peu de temps et de neuronnes. Vous n'aurez pas un niveau suffisant pour lire du Shakespeare dans le texte mais vous en saurez suffisamment pour demander votre chemin à Londres.

# Javascript natif

### Quelques notions de syntaxe

A quoi ressemble Javascript rapidement...

```javascript

// ceci est une ligne de commentaire

/*
* Ce sont aussi
* des lignes de commentaires
*/

// toto est une variable, let permet de déclarer une variable. 
// Une variable est un sujet sur le plan liguistique, ce sujet comme son nom l'indique peut varier, en d'autres termes changer de valeur.
let toto="un truc";

// var et const permettent aussi de déclarer des variables (ou constantes dans le second cas) mais nous ne les utiliserons pas ici, nous n'utiliserons que let
var toto="un truc";
const toto="un truc";

// manger() est une fonction (on dit aussi méthode). 
// Une fonction fait référence à une action, on distingue les fonctions facilement car elles ont des parenthèses
// Une fonction est un verbe sur le plan liguistique.
manger();

//ici nous avons une fonction avec des arguments
manger(starter, mainCourse, dessert);

// Un verbe sans sujet n'a souvent pas beaucoup de sens.
// ici on a une phrase qui commence à ressembler à un programme
david.manger("Salade", "Pizza", 2 * fraises + 999 * chantilly );

//toutes les lignes ci-dessous sont correctes...
let hello="world";  // c'est la version qu'on va préférer
let hello="world"   // sans le point virgule je n'aime pas (et ça vous coutera des points) mais ça marche aussi.
let hello  =  'world'   // marche aussi avec de simples quotes et on note au passage que les espaces n'ont pas d'incidence non plus.

//ces trois syntaxes sont correctes

alert("hello world");

// on peut sauter des lignes, c'est souvent utilisé pour éviter d'avoir de longues lignes incompréhensibles.
alert(
  "hello world"
);

// Cette version démontre que les indentations n'ont pas d'incidence en javascript. 
alert(
   "hello world"
        );

```

En résumé on peut faire n'importe quoi avec les sauts de lignes, les points virgules et les espaces.
Mais comme vous n'êtes pas des psychopathes vous allez indenter votre code de manière à ce qu'il soit lisible.

#### Les choses obligatoires !

Pour le reste 
- Une `(` parenthèse ouverte doit toujours être fermée `)`
- Des `[` crochets ouverts doivent toujours être fermés `]`
- Des `{` accolades ouvertes doivent toujours être fermées `}`

#### Les conventions fortement conseillées

##### camelCase
Toutes nos variables et toutes nos fonctions utiliseront [le format camelCase](https://wprock.fr/blog/conventions-nommage-programmation/#conventions-le-camel-case).
Ce n'est pas obligatoire mais c'est une convention en javascript. 

##### PascalCase
Toutes nos Classes et tous les NomsDeFichierQuiContiennentUneClasse.js seront [au format PascalCase](https://wprock.fr/blog/conventions-nommage-programmation/#conventions-le-pascal-case).
Ce n'est toujours pas obligatoire mais c'est aussi une convention en javascript. 

##### $elementJQuery
Un peu plus bas dans ce document je vous présenterai jQuery, 
retenez simplement ici que quand on utilisera un dollar  `$` devant une variable ça voudra dire que c'est du jquery et donc un élément html.

```javascript
  // ceci est l'élément html jQuery où s'affiche un score
  $score1=$("#score-joueur-1");
  
  // ceci est le score du joueur 1 (on va dire qu'il a 188 points)
  score1=188;
```


### La console de votre navigateur

La console de votre navigateur doit être tout le temps ouverte quand vous testez votre code. 
Si la console affiche du rouge, alors il faut résoudre le problème avant de passer à autre chose.

#### La console vous permet de tester du code.


Copiez / collez ce code dans la console et appuyez sur ENTER

```javascript
  // Je ne comprends rien au code ci-dessous mais je peux le tester quand même...
  alert("Hello world");
  if(confirm("Si tu as compris appuies sur OK")){
    alert("super");
  }else{
    alert("Annuler n'est pas une option");
  }
```

#### La console vous permet surtout de *logger* des choses.
Copiez / collez ce code dans votre fichier javascript principal

```javascript
  console.log("Hello world");
  console.log(new Date());
```

C'est très très pratique car ça permet d'avoir un petit espion en dehors du jeu, 
par exemple pour déterminer le résultat d'une addition, la vitesse d'une balle ou ce genre de choses...


### Un peu de Maths...

```javascript
  console.log(1+1);
  console.log(10-5);
  console.log(10*5);
  console.log(1000 / 4);
  
  // utiliser des variables
  let a = 10;
  let b = 5;
  let resultat = a + b;
  console.log("resultat",resultat);
  
  // incrémenter pour aller plus vite
  // c++; est équivalent à c = c+1; C'est simplement plus rapide à écrire.
  let c=0;
  c++;
  c++;
  c++;
  console.log("c",c);

  //ou bien encore...
  let d=10;
  d+=5;
  console.log("d",d);
  
```

#### Ma fonction préférée Math.random()

[Math.random()](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Math/random) renvoie un chiffre aléatoire entre 0 et 1;

Essayez ceci dans la console...

```javascript
  console.log(Math.random());
  console.log(Math.random());
  console.log(Math.random());
```

Pour générer un chiffre aléatoire entre 0 et 100 on fera donc...

```javascript
  console.log( Math.random() * 100 );
```

### Les conditions, on les utilisera énormément...

Si(la balle touche le mur){
  fais ceci
}Sinon{
  fais celà
}

```javascript
  if( 10 > 5){
    alert("touche le mur");
  }else{
    alert("touche pas le mur");
  }
```

```javascript
  //essayez ce code plusieurs fois d'affilée dans la console
  if( Math.random() > 0.5){
    alert("gagné");
  }else{
    alert("perdu");
  }
```

### Les opérateurs, on les utilisera énormément avec nos conditions

```javascript
  if(1+1 === 2){
    console.log("On va afficher ça");
  }else{
     console.log("On va pas afficher ça");
  }
  
  if(1+4 > 3){
    console.log("On va afficher ça aussi");
  }
  
  if(1+1+1 <= 3){
    console.log("On va afficher ça encore");
  }
  
```


#### Convertir le texte "150px" en nombre 150

Je ne rentre pas dans le détail de la fonction [parseInt](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/parseInt).
Pour le moment retenez simplement que ça permet de transformer un [String](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String) 
en [Number](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Number) 

```javascript
  console.log( parseInt("150px") );
```
## Faire des boucles temporelles

https://www.w3schools.com/jsref/met_win_setinterval.asp

```javascript
let i=0;
setInterval(function(){
    i++;
    // affiche le résultat de i dans le titre de page toutes les 1000 millisecondes.
    document.title=i; 
}, 1000);
```
## Faire un truc...mais plus tard

https://www.w3schools.com/jsref/met_win_settimeout.asp

```javascript
setTimeout(
    function(){
        alert("il faut se réveiller!");
    },5000
);
```

## Ecouter les touches du clavier

Les notions d'écouteur sont un peu complexes à aborder sans avoir quelques semaines de pratique, je vous livre donc le code qui vous permettra de faire ce que vous voulez pour notre PONG sans pour autant vous l'expliquer.

Savoir quand une touche est enfoncée et savoir de quelle touche il s'agit.

```javascript
window.addEventListener("keydown", function (event) {
  if (event.defaultPrevented) { return}
  console.log("La touche '"+event.key+ "' a été enfoncée")
  event.preventDefault();
}, true);
```

Savoir quand une touche est relachée et savoir de quelle touche il s'agit.

```javascript
window.addEventListener("keyup", function (event) {
  if (event.defaultPrevented) { return}
  console.log("La touche '"+event.key+ "' a été relachée")
  event.preventDefault();
}, true);
```
## Les tableaux
**Vous n'en aurez pas besoin au début.** 
Les tableaux permettent de gérer des listes. 
Par exemple des listes de sons à jouer aléatoirement, des listes de balles, des listes de bonus à toucher, etc...

Je ne vous explique pas ici en détail comment ça marche, ce n'est pas la littérature qui manque à ce sujet.
https://developer.mozilla.org/fr/docs/Learn/JavaScript/First_steps/tableaux

Juste histoire que vous sachiez à quoi ça ressemble...
```javascript
//déclarer un tableau
let shopping = ['pain', 'lait', 'fromage', 'houmous', 'nouilles'];
shopping[0]; // renvoie "pain"
shopping[1]; // renvoie "lait"

//parcourir le tableau
for (var i = 0; i < shopping.length; i++) { 
  console.log( shopping[i] ); 
}

```


## Afficher la page en fullscreen

Google et stackoverflow sont vos amis pour cette fois :smiling_imp:

# jQuery

[jQuery](https://jquery.com/) est ce que l'on appelle un **framework** javascript.
C'est un des programmes les plus utilisés au monde. 
Je vous invite à lire la [page wikipedia de jQuery](https://fr.wikipedia.org/wiki/JQuery).

## Pas obligatoire mais...
L'utilisation de jQuery n'est pas obligatoire mais pour faire ce que nous allons faire ce serait du snobisme de s'en passer.
jQuery va nous simplifier la vie. On l'utilisera quand c'est pratique de l'utiliser, on s'en passera quand ce sera contre productif.

Si vous êtes curieux, sur ce site (http://youmightnotneedjquery.com/) au nom qui en dit long, vous pourrez voir comment faire la même chose en utilisant ou pas jQuery. 

Personnellement ce que j'en retiens c'est que des fois "you will need jquery" pour pas vous prendre la tête.

Un petit exemple; dans notre PONG nous aurons besoin de calculer la largeur du terrain de tennis.

```javascript
//pour obtenir cette largeur avec jQuery, ça donnera ça:
let largeur = $terrain.width();

//pour obtenir cette largeur sans jQuery, ça donnerait ça:
let largeur = parseFloat(getComputedStyle($terrain, null).width.replace("px", ""));

//Convaincus ?
console.log("élève en PLS");

```


## Pour installer jQuery

Les diverses méthodes d'installation sont expliquées ici:
https://jquery.com/download/

Celle que nous allons utiliser pour ne pas perdre de temps...

```html
<!--à placer dans votre <head> pour ce coup-ci -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
```

## Pour sélectionner un élément HTML avec jquery 

Dites vous que c'est pareil qu'en CSS, c'est ce que l'on appelle un sélecteur.

Pour sélectionner un élément html par son id on utilise `#`

```html
<div id="robert">
  De Niro
</div>
```
```javascript
//javascript
let $robert = $("#robert");
console.log($robert); // on aura ici un seul objet
console.log("le texte dans l'objet ", $robert.text() );
```

Pour sélectionner des éléments html par leur classe on utilise `.`

```html
<div class="pokemon">
  Germignon
</div>
<div class="pokemon">
  Macronium
</div>
<div class="pokemon">
  Méganium
</div>
```
```javascript
//javascript
let $pokemons = $(".pokemon"); // on aura ici plusieurs objets
console.log($pokemons );
```

## Pour connaître les tailles d'un élément jQuery HTML

https://api.jquery.com/width/

https://api.jquery.com/height/


```javascript
let $monMachin = $("#mon-machin");
console.log($monMachin.width());
console.log($monMachin.height());
```

## Pour connaître/définir les positions d'un élément jQuery HTML

https://api.jquery.com/css/

```javascript
let $monMachin = $("#mon-machin");

//obtenir les positions
console.log($monMachin.css("top")); // attention ce qui va s'afficher ici ne sera pas forcément un nombre...
console.log($monMachin.css("left"));

//définir les positions
$monMachin.css("top",300);
$monMachin.css("left",600);
//un peu plus fun...
$monMachin.css("left", Math.random() * 500 );

```
#### Notes

La fonction `css` permet de lire et définir des propriétés css, ça ne sert pas uniquement à connaître top et left.

```javascript
$monMachin.css("color");
$monMachin.css("background-color","#FF0000");
```

#### Attention

Il existe une fonction `position()` et une fonction `offset()` dans jQuery. 
Ces fonctions qui permettent de manipuler les positions d'objets HTML sont très pratiques mais peuvent engendrer des bugs incompréhensibles quand on n'a pas suffisament de pratique d'HTML et CSS. **ON NE VA PAS LES UTILISER**.

## Gérer les evênements de click souris et touch en jQuery

#### La version souris
```javascript
$monBouton.on("mousedown", function (event) {
    event.preventDefault(); //je ne vous explique pas pour l'instant à quoi ça sert c'est trop complexe
    console.log("tu as appuyé sur $monBouton");
});
$monBouton.on("mouseup", function (event) {
    event.preventDefault();
    console.log("tu as relaché la souris sur $monBouton");
});
```

#### La même chose en tactile
```javascript
$monBouton.on("touchstart", function (event) {
    event.preventDefault();
    console.log("tu as appuyé sur $monBouton");
});
$monBouton.on("touchend", function (event) {
    event.preventDefault();
    console.log("tu as relaché sur $monBouton");
});
```

## Ajouter ou supprimer des classes CSS avec jQuery

https://api.jquery.com/addclass/

https://api.jquery.com/removeClass/

```javascript

//ajouter une classe
$monMachin.addClass("nom-de-ma-classe-css");
//retirer une classe
$monMachin.removeClass("nom-de-ma-classe-css");

```


# La Programmation Orientée Objet (POO)

## Classes javascript

Attention on parle bien de javascript ici, pas de CSS. 
Une classe CSS et une classe Javascript n'ont rien en commun si ce n'est le concept abstrait de classe qui est commun à la plupart des langages de programmation. 

#### Pour créer une classe...

```javascript

//fichier Eleve.js
class Eleve{
  constructor(nom,prenom){
    this.nom=nom;
    this.prenom=prenom;
    this.ecole="ETPA";
  }
  //fait parler l'élève
  parle(phrase){
    let blabla="My name is "+ this.nom +", "+this.nomEtPrenom+", je voulais vous dire: "+phrase;
    alert(blabla);
  }
  /**
  * Renvoie le nom et le prénom
  * @returns {String}
  **/
  get nomEtPrenom(){
    return this.prenom+" "+this.nom
  }
  
  
}
```

#### Pour utiliser cette classe...

```javascript

let jamesBond=new Eleve("Bond","James");
jamesBond.parle("On ne vit que deux fois");

let donald=new Eleve("Duck","Donald");
donald.parle("Ne pas me confondre avec un président des Etats Unis");

```

# Pour gérer l'Audio

La gestion du son n'est pas la priorité, ce sera la cerise sur le PONG.

Pour gérer le son dans notre jeu, on utilisera la librairie sound.js.
C'est un peu comme jQuery, c'est un framework qui nous simplifiera la vie.
Vous n'aurez besoin que de ce qui est expliqué dans cette page: https://createjs.com/getting-started/soundjs



