# Les astuces et remarques du père Fallet
Vous trouverez ci-après un florilège des différentes erreurs que je constate fréquemment
durant mes revues de codes avec mes chères élèves et apprentis.

Bonne lecture, Steve.
## HTML
* Organiser votre site avec des dossiers (`css/`, `fonts/`, `img/`, ... )
 ```
racine-de-mon-site
  │  
  └─── css
  │     └─ fonts.css
  │     └─ main.css
  │ 
  └─── fonts
  │     └─ arial.eot
  │     └─ arial.svg
  │     └─ arial.ttf
  │     └─ arial.woff
  │ 
  └─── img
  │     └─ logo.svg
  │     └─ photo-plage.jpg  
  │ 
  └─ favicon.ico
  └─ index.html
 ```
* Nom des fichiers et dossiers **en minuscules, sans espaces et sans caractères spéciaux** `CSS/Trop Stylé.css` > `css/trop-style.css`
 y compris les images et polices.
* La page d'accueil de votre site doit se nommer `index.html` tout en minuscule.
* Définir la **bonne langue** dans `<html>`.
  Si votre contenu est en français, mettre `<html lang="fr">`, et non `<html lang="en">`.
* Mettre un vrais `<title>` à votre site !
  Le titre doit être composé des mêmes mots-clé que le titre principal du site `<h1>`, suivi du nom de votre site.
```html
<title>Tout l’assortiment de jouets | Migros</title>
```` 
* Il manque `viewport` obligatoire pour un bon affichage sur smartphone 
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
* Ne pas oublier d'ajouter l'**icône de site**, appelée favicon.
```html
<link rel="icon" href="favicon.ico">
```
* Charger le fichier CSS des polices avant le fichier CSS des styles de base.
* Pas d'espaces ni de majuscules, ni de caractères spéciaux dans les id ou 
  class, 
  utiliser des `-` ou  `_` à la place. `class="épéeRouge"` > `class="epee-rouge"`
* Supprimer les espaces inutiles au début des balises.
  * Faux : `<p> apprentie informaticienne 1ère année à l'EMT </p>`
  * Juste : `<p>apprentie informaticienne 1ère année à l'EMT</p>`
* Supprimer les espaces dans `href` pour le numéro de tel : `<a href="tel:0041791234567">Mon tel</a>`
* Un paragraphe `<p>` doit contenir au minimum une phrase. Si ce n'est pas le cas on utilisera une `<div>` à la place.
* Pas d'espace autour du signe `=` dans les attributs HTML
    * Faux : `<ul class = "sommaire">`
    * Juste : `<ul class="sommaire">`
* Les `<p>` peuvent uniquement contenir des éléments inline comme : `<strong>`, `<em>`, `<a>`, ...
* On ne peut pas écrire des textes directement dans le `<body>` il faut les ajouter dans un élément comme : `<p>`, `<div>`, `<h1>`, ...
* Aérer en ajoutant une ligne vide avant les <h2>
* Pas utiliser `<br>` pour créer des espaces ou des marges. On utilise les `<br>` uniquement dans les blocs de textes.
  * Utiliser le CSS avec `padding` ou `margin` pour créer des marges et espacer les éléments.
* Ne pas oublier de préciser le texte alternatif des images avec l'attribut `alt=""`
```html
    <img src="img/fifty-burgers.png" alt="Logo Fifty Burgers"/>
```` 
* Indentation, mettre à la ligne les éléments contenus dans d'autres éléments et les indenter avec 2 ou 4 espaces.
```html
<!-- FAUX -->
<main><h1>Mon titre</h1>
<p>Mon para</p>
</main>
<!-- JUSTE -->
<main>
  <h1>Mon titre</h1>
  <p>Mon para</p>
</main>
```
* Eviter les lignes de code trop grandes (plus de 100 caractère)
```html
<!-- FAUX -->
<a href="./icone/apple-touch-icon.png"><img src="icone/favicon-32x32.png" alt="photo pour mon cv" title="Cliquez pour agrandir" ></a>
<!-- JUSTE -->
<a href="./icone/apple-touch-icon.png">
  <img src="icone/favicon-32x32.png"
       alt="photo pour mon cv"
       title="Cliquez pour agrandir"
  >
</a>
```
* Séparer le contenu `<body>` en trois parties :
```html
<body>
    <header>
        ...
    </header>
    <main>
       ...
    </main>
    <footer>
       ...
    </footer>
</body>
```
* Préférer les entités HTML pour les caractères spéciaux. Pour © utiliser &copy;
* Éviter de donner des tailles aux images en HTML, le faire en CSS avec `height` et `width`
* Toujours **terminer** vos fichiers de code (HTML, CSS, JavaScript, ...) par une **nouvelle ligne vide** pour simplifier les traitements automatisés.
* Valider votre code : https://validator.w3.org/nu/
* On peut ajouter l'objet de l'e-mail `<a href="mailto:steve.fallet@divtec.ch?subject=tutu">` 
## CSS
* Définir le style des liens, couleur.
```css
a {
    color:red;
}
```
* Proposer un style différent pour les liens survolés 
```css
a:hover {
    color:blue;
}
```
* `max-width: 100%` pour toutes les images
* Il manque des instructions pour le design de base du site
```css
body {
    font-family: Verdana, sans-serif;   /* Police d'écriture de base */
    font-weight: normal;                /* Épaisseur du texte de base*/
    font-size: 1.2rem;                  /* taille du texte de base*/
    line-height: 1.4;                   /* Hauteur de ligne de base, généralement entre 1.3 et 1.7 */
    color: black;                       /* couleur du texte de base*/
    background-color: white;            /* couleur d'arrière plan du site */
}
```
* Pas oublier de définir une police générique `sans-serif`, `serif` ou `cursive` pour les familles de polices
    `font-family: Roboto, sans-serif;`
* Dès que l'on change la police d'écriture, il faut préciser l'épaisseur à utiliser
```css
h1 {
    font-family: "Sofia Sans Semi Condensed", sans-serif;
    font-weight: 400;
}
```
* Jamais de `font-size` en `px`, utiliser les `em` ou `rem`
* Manque règle pour la fluidité des images
```css
img {
    max-width:100%;
    height: auto;
}
```
* utiliser des noms de classes CSS représentatifs et compréhensibles.
* Utiliser les `em` à la place des % pour les tailles de textes : `200% => 2em`
* Toujours écrire les noms des couleurs en minuscules
* Toujours ajouter un espace avant l'accolade d'ouverture
* Lien pour les e-mails `<a href="mailto:steve.fallet@kode.ch?subject=contact">steve.fallet@kode.ch</a>"`
```css
/* FAUX */
body{
/* JUSTE */
body {
```
* Toujours ajouter une ligne blanche entre deux blocs de règles CSS
```
h2 {
    color:red;
}

h3 {
    color:blue;
}
```  
* Mettre les accolade sur la même ligne que le sélecteur
```
/* Faux */
h1
{
    color:red;
}

/* Faux */
h1 { color:red; }

/* Juste */
h1 {
    color:red;
}
```
* Revenir à la ligne après la `,` si plusieurs sélecteurs
```css
/* Faux */ 
h1, h2, h3 {
    color:red;
}

/* Juste */
h1,
h2,
h3 {
    color:red;
}
```
* Si valeur `0` pas nécessaire de préciser l'unité : `margin: 0px => margin: 0;`
* Pour les images d'arrière-plan, mettre l'url ou le chemin entre guillemets 
```css
/* Faux */
background-image: url(https://img.freepik.com/photos.jpg);
/* Juste */
background-image: url("https://img.freepik.com/photos.jpg");
```


