# Cours PHP 
> Rédigé par Néhémie Barkia 
___________________________

## Niveau débutant ⭐
### Les bases :
Avant tout, il faut savoir que le code PHP ne sera exécuté uniquement s'il est compris dans un fichier `.php`. Il doit être compris dans les balises php : `<?php MON CODE ICI ?>`. Chaque instruction de code doit être terminée avec un `;`.


### Déclaration d'une variable : 
Une variable sert à stoquer des informations (dynamiques ou non). Celle ci débute avec un `$` suivi de son nom. Elle doit obligatoirement commencer par une lettre. Ce nom peut comprendre des lettre, des chifres et underscore uniquement. Elle ne doit pas contenir d'espace. 

Types de variables : 
IL y a différents types de variables. Les deux les plus courrantes sont les **int** et les **chaines de carratères**.

```php
// Déclaration d'un INT : 
$monint = 0;

// Déclaration d'une chaine de carractère :
$machaine = "ceci est une chaine";
```

### Mathématique des variables : 
Comme dans ton language, nous pouvons ajouter, soustraire, multiplier des variables. Voici quelques exemples : 
```php
// Déclaration des varialbles
$a = 50; 
$b = 25;

$somme = $a + $b;      
$soustraction = $a - $b;
$multiplication = $a * $b;
$division = $a / $b;
```

### Les conditions :
Créer des conditions, c'est essentiels ! Les conditions sont régie par l'instuction `if`. Voyons comment sela fonctionne :
```php
$a = 50; 
$b = 25;

// Condition simple
if ($a + $b === 75){
    // Si a + b font 75
} else {
    // Sinon (si aucune condition n'est remplie)
}

// Condition avancée 
if ($a + $b === 75){
    // Si a + b font bien 75
} elif ($a + $b === 80) {
    // Sinon si a + b font 80
} else {
    // Sinon (si aucune condition n'est remplie)
}
```

### Afficher du contenu :
Le code PHP peut s'exectuter à n'importe quel endroit d'un code HTML. Pour afficher quelque chose on utilise la commande `echo "Mon texte";`.

Exemple : 
```php
<?php
// Déclaration de ma variable
$mavariable "Mon premier titre !";
?>

<html>
<body>
<h1><?php 
// Ici je vais afficher le contenu de la variable "mavariable". Son contenu va donc etre insséré entre les balises H1.
echo "$mavariable";

?></h1>
<p>My first paragraph.</p>
</body>
</html>
```
Donc, comme vous pouvez le voir, ont met du code php là où l'on veux.
 

## Niveau intermédiaire ⭐⭐
### Avant-propos :
Comme dans tous les métier, celui de développeur comprend des bonnes pratiques. Dans le niveau intermediaire, je vais vous apprendre comment "bien" codder. 

### Les commentaires :
__Les commentaires sont très importants__ ! Bien qu'à priori vous pouver trouver inutile un commentaire sur des lignes de codes simple. Ils vous permettents de vous retrouver plus facilement dans ce que vous avez fait et ce que vous devez faire. Il sont important également dans le cadre d'un developpement fait à plusieurs, il faut que vos collègues sachent directement ce que vous avez fait ! 

### Les fonctions 
Il y a une règle simple dans le developpement, il ne faut gagner du temps et éviter les duplicatats ! Les fonctions vous serons d'une grande utilité pour ça ! 

#### Création d'une fonction :
Une fonction sert donc à contracter le code. Je vais d'abort vous montrer un code répétitif sans fonction puis vous montrer les bonnes pratiques : 
```php
// !!!!!!! Ce qu'il ne faut pas faire !!!!!!! 
$voiture = "Jaune"; 

// Test des différentes conditions
if ($voiture === "Jaune") {
    echo "La voiture est Jaune";
};

if ($voiture) === "Rouge" {
    echo "La voiture est Rouge";
};

if ($voiture) === "Verte" {
    echo "La voiture est Verte";
};

if ($voiture) === "Bleu" {
    echo "La voiture est Bleu";
};



// !!!!!!! Ce qu'il faut faire !!!!!!! 
$voiture = "Jaune"; 

// Création de la fonction
function afficherlacouleur($mavariable)
{
  echo "La voiture est $mavariable";
}

// Test des différentes conditions
if ($voiture === "Jaune") {
    afficherlacouleur("Jaune");
};

if ($voiture) === "Rouge" {
    afficherlacouleur("Rouge");
};

if ($voiture) === "Verte" {
    afficherlacouleur("Verte");
};

if ($voiture) === "Bleu" {
    afficherlacouleur("Bleu");
};

```

### Conditions imbriquées
Dans le dernier exemple, je n'ai pas pratiqué les bonnes manières vis à vis des conditions. Je vais donc montrer comment réaliser des conditions imbriqués qui simplifient la lecture du code :
```php
// !!!!!!! Ce qu'il ne faut pas faire !!!!!!! 
$voiture = "Jaune"; 

// Création de la fonction
function afficherlacouleur($mavariable)
{
  echo "La voiture est $mavariable";
}

// Test des différentes conditions
if ($voiture === "Jaune") {
    afficherlacouleur("Jaune");
}

if ($voiture) === "Rouge" {
    afficherlacouleur("Rouge");
}

if ($voiture) === "Verte" {
    afficherlacouleur("Verte");
}

if ($voiture) === "Bleu" {
    afficherlacouleur("Bleu");
}



// !!!!!!! Ce qu'il faut faire !!!!!!! 
$voiture = "Jaune"; 

function afficherlacouleur($mavariable)
{
  echo "La voiture est $mavariable";
}

// Création d'un switch.
// A chaque fois nous devons finir le cas par l'instruction "break;".
switch ($voiture) {
    case "Jaune":
        afficherlacouleur("Jaune");
        break;
    case "Rouge":
        afficherlacouleur("Rouge");
        break;
    case "Verte":
        afficherlacouleur("Verte");
        break;
    case "Bleu":
        afficherlacouleur("Bleu");
        break;
}
```

## Niveau difficile ⭐⭐⭐
### Imports :
A tous moments dans votre code php, vous pouvez importer d'autres fichier php. C'est très pratique pour éviter les répétitions. Typiquement nous pouvons importer sur chaque page de notre site, un simple fichier `config.php` qui répertorie les différentes informations d'identifiaction à une base de donnée.

> Fichier config.php
```php
// Définition des variables
$mavar1 = "Chien";
$mavar2 = "Chat";
```

> Fichier index.php
```php
include './config.php';  // Import des informations d'identifiaction à la base de donneés

// Affichage des variable
echo "$mavar1"; // --> Cela affiche "Chien"
echo "$mavar2"; // --> Cela affiche "Chat"
```
### Envoyer des données entre deux pages PhP
Pour avoir un site dynamique, vous aurez recours à l'envoie de différentes informations entre les pages de votre site. Il existe trois grandes méthodes : 
##### 1 - Get (Lien)
La méthode Get est la façon la plus simple de faire transiter différentes informations au travers des liens de votre site web. Elle est visible mais rudement pratique !

> index.php
```php
// Si je tape l'url : monsite.com/index.php?id=Nem
$utilisateur = $_GET['id'];
echo "Bonjour $utilisateur !";
```

##### 2 - Post (formulaire HTML)
La méthode Post est utilisée avec les données envoyées avec les formulaires html. Nous pouvons récuperer les informations inscrites dans les formulaires.
> index.php
```php
<form action="../action.php" method="post"> // Ici on précise vers quel fichier php nous envoyons les données du formulaire
    <div>
        <label for="name">Identifiant :</label>
        <input type="text" id="identifiant" name="nouvel_utilisateur">
    </div>
     <button type="submit" value="ok">Créer l'utilisateur</button>
</form>
```

> action.php
```php
$identifiant = $_POST['nouvel_utilisateur'];
echo "$identifiant"; // Le résultat sera le texte inscrit dans le formulaire précédement
```

##### 3 - Les Cookies
Vous connessez surement les cookies, ceux-ci vous permetent de stoquer des variables directement sur l'ordinateur de l'utilisateur de votre site. Ce cookie et lû par chaque page de votre site web. Vous pouvez y inscrire n'importe quelles variables.

__Toutes les pages de votre site aurons l'obligation de commencer comme ceci :__
```php
<?php
session_start();
```

__Stoquer une variable dans le cookie :__ 
```php
$_SESSION['utilisateur'] = "Jean"; // J'inscrit dans le cookie "utilisateur", la chaine de caractère "Jean".
```

IMPORTANT : IL FAUT STOQUER DANS UN COOKIE UNIQUEMENT DES INFORMATIONS QUI PEUVENT ÊTRE DETRUTES !
--> Le cookie peut être supprimé à tous moments par l'utilisateur !
   

### Lien avec une base de données
La base de données permet de stoquer efficactement des tas d'informations et de pouvoir les consulter rapidement !

Premièrement, je vous recommendre de créer un fichier `options.php` :
> options.php
```php

/*  
*  =========================================================================
*  Veuillez spécifiez les informations de connection à votre base de données
*  =========================================================================
*/ 

$hotedeconnexion = "127.0.0.1"; // 127.0.0.1 = Localhost
$basededonnee = "MaBaseDeDonnées";
$utilisateurdb = "MonSuperCompte";
$motdepassedb = "MonSuperMDP!@";

```

Requêtte simple :
```php
include './config.php';  // Import des informations de connexion à la base de données.

//  Connexion à la base de donnée.
$mysqli = new mysqli("$hotedeconnexion", "$utilisateur", "$motdepasse", "$basededonnee");
if ($mysqli->connect_errno) {
    echo "Echec lors de la connexion à MySQL !";   // Affichage de l'erreur.
    echo "Erreur N°$mysqli->errno : $mysqli->error";    // Affichage de l'erreur.
}
// Création d'une table SQL.
if (!$mysqli->query("CREATE TABLE IF NOT EXISTS `matable` ( `id` INT PRIMARY KEY NOT NULL AUTO_INCREMENT, `utilisateur` varchar(50) NOT NULL);")) {
    echo "Echec lors de la requêtte SQL !";   // Affichage de l'erreur.
    echo "Erreur N°$mysqli->errno : $mysqli->error";    // Affichage de l'erreur.
}
```

Nous pouvons également faire une requette plus complexe que nous allons pouvoir parcourir :
```php
include './config.php';  // Import des informations de connexion à la base de données.

// Établissement de la connexion au serveur mysql.
$cnx = new PDO("mysql:host=$hotedeconnexion;dbname=$basededonnee", "$utilisateur", "$motdepasse");
// Commande SQL permetant de récupérer la liste des tickets actifs.
$req = 'SELECT * FROM `tickets` where `etat` = "0" OR `etat` = "1";';
// Envoie au serveur la commande via le biais des informations de connexion.
$res = $cnx->query($req);

// Boucle tant qu'il y a de lignes corespondantes à la requettes
while ($ligne = $res->fetch(PDO::FETCH_OBJ)) {
    echo "$ligne->description"; // Par exemple, nous affichons le champs "description" de tous les réultats de la requêtte SQL. 
}
```
