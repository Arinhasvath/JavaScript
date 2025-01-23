# JavaScript
# 🚀 Tutoriel JavaScript pour Débutants

## 1. Les Variables et Types de Données

```javascript
// Déclaration d'une variable avec 'let'
let monAge = 25;  // 'let' permet de déclarer une variable qui peut être modifiée plus tard
// Le signe '=' est l'opérateur d'affectation qui assigne la valeur 25 à la variable monAge

// Déclaration d'une constante avec 'const'
const PI = 3.14159;  // 'const' crée une variable qui ne peut pas être modifiée
// Utilisation: pour les valeurs qui ne doivent jamais changer

// Les différents types de données
let texte = "Bonjour!";           // Type: String (chaîne de caractères)
let nombre = 42;                   // Type: Number (nombre)
let estVrai = true;               // Type: Boolean (booléen: vrai/faux)
let tableauFruits = ["pomme", "banane", "orange"];  // Type: Array (tableau)
let personne = {                  // Type: Object (objet)
    nom: "Alice",
    age: 30
};

// Pour voir le type d'une variable
console.log(typeof texte);    // Affiche: "string"
console.log(typeof nombre);   // Affiche: "number"
```

## 2. Les Opérations de Base

```javascript
// Opérations mathématiques
let a = 10;
let b = 5;

let addition = a + b;        // 15
let soustraction = a - b;    // 5
let multiplication = a * b;  // 50
let division = a / b;        // 2

// Opérations sur les chaînes
let prenom = "Jean";
let nom = "Dupont";
let nomComplet = prenom + " " + nom;  // Concaténation: "Jean Dupont"
// Le '+' avec des strings les combine (concatène)

// Opérateurs de comparaison
let estEgal = (a === b);        // false (égalité stricte: valeur ET type)
let estPlusGrand = (a > b);     // true
let estPlusOuEgal = (a >= b);   // true
```

## 3. Les Structures Conditionnelles

```javascript
// If...else (si...sinon)
let age = 18;

if (age >= 18) {
    console.log("Vous êtes majeur!");  // Cette ligne s'exécute si age >= 18
} else {
    console.log("Vous êtes mineur!");  // Cette ligne s'exécute si age < 18
}

// Switch (alternative à plusieurs if...else)
let fruit = "pomme";

switch (fruit) {
    case "pomme":
        console.log("C'est une pomme!");
        break;  // 'break' est important pour sortir du switch
    case "banane":
        console.log("C'est une banane!");
        break;
    default:  // s'exécute si aucun case ne correspond
        console.log("Fruit inconnu");
}
```

## 4. Les Boucles

```javascript
// Boucle for (pour)
for (let i = 0; i < 5; i++) {
    console.log(i);  // Affiche: 0, 1, 2, 3, 4
}
// i = 0: initialisation
// i < 5: condition de continuation
// i++: incrémentation après chaque tour

// Boucle while (tant que)
let compteur = 0;
while (compteur < 3) {
    console.log(compteur);  // Affiche: 0, 1, 2
    compteur++;  // Incrémente compteur
}

// Boucle foreach sur un tableau
let fruits = ["pomme", "banane", "orange"];
fruits.forEach(function(fruit) {
    console.log(fruit);  // Affiche chaque fruit
});
```

## 5. Les Fonctions

```javascript
// Déclaration d'une fonction simple
function direBonjour(nom) {
    return "Bonjour " + nom + "!";
}
// 'function': mot-clé pour déclarer une fonction
// 'nom': paramètre que la fonction accepte
// 'return': renvoie le résultat

// Utilisation de la fonction
let message = direBonjour("Alice");  // message = "Bonjour Alice!"

// Fonction avec plusieurs paramètres
function calculerSomme(a, b) {
    let resultat = a + b;
    return resultat;
}

// Fonction fléchée (moderne)
const multiplier = (x, y) => x * y;
// Version plus concise d'une fonction
// Particulièrement utile pour les callbacks
```

## 🎮 Petit Projet Pratique

```javascript
// Créons un petit jeu de devinette
function jouerDevinette() {
    // Math.random() génère un nombre entre 0 et 1
    // Math.floor() arrondit à l'entier inférieur
    const nombreSecret = Math.floor(Math.random() * 100) + 1;
    let essais = 0;
    let trouve = false;

    while (!trouve && essais < 10) {
        // prompt() demande une entrée à l'utilisateur
        let tentative = prompt("Devinez le nombre (entre 1 et 100):");
        essais++;

        if (tentative == nombreSecret) {
            alert("Bravo! Vous avez trouvé en " + essais + " essais!");
            trouve = true;
        } else if (tentative < nombreSecret) {
            alert("Plus grand!");
        } else {
            alert("Plus petit!");
        }
    }

    if (!trouve) {
        alert("Perdu! Le nombre était " + nombreSecret);
    }
}

// Pour lancer le jeu:
// jouerDevinette();
```

## 📝 Exercices Pratiques

1. Créez une fonction qui calcule l'âge à partir d'une année de naissance
2. Faites un programme qui affiche la table de multiplication d'un nombre
3. Créez un tableau de nombres et écrivez une fonction qui trouve le plus grand

## 🔍 Points Importants à Retenir

- JavaScript est sensible à la casse (majuscules/minuscules)
- Chaque instruction se termine par un point-virgule (;)
- Les accolades {} délimitent les blocs de code
- Le code est exécuté de haut en bas
- 'console.log()' est votre meilleur ami pour déboguer

## 🎯 Prochaines Étapes

- Manipuler le DOM (Document Object Model)
- Gérer les événements (clicks, input, etc.)
- Utiliser les promesses et async/await
- Découvrir les classes et l'orienté objet
