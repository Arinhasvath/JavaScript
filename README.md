# JavaScript
# 🚀 Tutoriel JavaScript pour Débutants
# 📘 Guide Complet de la Syntaxe JavaScript

## 1. Structure Lexicale Fondamentale

### 1.1 Les Caractères et l'Encodage
```javascript
// JavaScript utilise l'encodage Unicode (UTF-16)
let emoji = "🎮";  // Les émojis sont valides
let français = "àéèêë";  // Les accents sont supportés
```

### 1.2 Sensibilité à la Casse
```javascript
// JavaScript est sensible à la casse (case-sensitive)
let animal = "chat";  // Variable 'animal'
let Animal = "chien"; // Variable différente 'Animal'
// 'animal' et 'Animal' sont deux variables distinctes

// ⚠️ Conventions de nommage:
let nomUtilisateur;    // camelCase pour les variables/fonctions
class MaClasse {}      // PascalCase pour les classes
const MA_CONSTANTE = 5; // SNAKE_CASE pour les constantes
```

### 1.3 Espaces Blancs et Sauts de Ligne
```javascript
// Les espaces et sauts de ligne sont ignorés par le moteur JavaScript
let x=1;     // Valide mais peu lisible
let y = 1;   // Même chose, mais plus lisible
let z = 
1;          // Aussi valide

// Exception: Les sauts de ligne après return peuvent causer des erreurs
return
  5;  // ❌ Interprété comme: return; 5;
return 5;  // ✅ Correct
```

## 2. Structure des Instructions

### 2.1 Terminaison des Instructions
```javascript
// Trois façons de terminer une instruction:

// 1. Point-virgule explicite (recommandé)
let a = 1;
let b = 2;

// 2. Saut de ligne (déconseillé car risqué)
let c = 3
let d = 4

// 3. Points-virgules automatiques (ASI - Automatic Semicolon Insertion)
// ⚠️ À éviter car peut causer des bugs subtils
function maFonction() {
    return  // ASI insère un point-virgule ici!
    {
        resultat: 42
    }
}
```

### 2.2 Blocs de Code
```javascript
// Les blocs sont délimités par des accolades {}
if (true) {
    // Début du bloc
    let x = 1;
    let y = 2;
    // Fin du bloc
}

// Portée des variables (scope)
{
    let local = "Je suis locale";  // Variable locale au bloc
    var globale = "Je suis accessible partout";  // ⚠️ Éviter var
}
// console.log(local);     // ❌ Erreur: local n'existe pas ici
console.log(globale);   // ✅ Fonctionne
```

## 3. Types de Données et Littéraux

### 3.1 Nombres
```javascript
// Différentes syntaxes pour les nombres
let entier = 42;          // Nombre entier
let decimal = 42.5;       // Nombre décimal
let scientifique = 1e6;   // Notation scientifique (1 million)
let binaire = 0b1010;     // Nombre binaire (10 en décimal)
let octal = 0o744;        // Nombre octal
let hexadecimal = 0xFF;   // Nombre hexadécimal

// Nombres spéciaux
let infini = Infinity;    // Représente l'infini
let pasNombre = NaN;      // Not a Number (résultat d'opérations invalides)
```

### 3.2 Chaînes de Caractères
```javascript
// Trois façons de définir des strings
let simple = 'Simple';            // Guillemets simples
let double = "Double";            // Guillemets doubles
let template = `Template ${simple}`; // Template literal (avec interpolation)

// Caractères spéciaux (échappement)
let chemin = "C:\\Documents";     // \\ pour un backslash
let multiLigne = "Ligne 1\nLigne 2"; // \n pour nouvelle ligne
let tabulation = "Colonne1\tColonne2"; // \t pour tabulation

// Template literals multilignes
let html = `
    <div>
        <h1>Titre</h1>
        <p>Paragraphe</p>
    </div>
`;  // Conserve le formatage
```

### 3.3 Objets et Tableaux
```javascript
// Objets littéraux
let personne = {
    // Paire clé-valeur classique
    nom: "Alice",
    
    // Méthode courte (ES6+)
    parler() {
        return `Je m'appelle ${this.nom}`;
    },
    
    // Propriété calculée
    ["age" + "Actuel"]: 25,
    
    // Getter et Setter
    get nomComplet() {
        return this.nom + " Dupont";
    },
    set nomComplet(valeur) {
        this.nom = valeur.split(" ")[0];
    }
};

// Tableaux littéraux
let nombres = [
    1,           // Index 0
    2,           // Index 1
    "trois",     // Les tableaux peuvent mélanger les types
    function() { // Peuvent contenir des fonctions
        return 4;
    },
    [...Array(3)].map((_, i) => i + 5) // Spread et génération
];
```

## 4. Expressions et Opérateurs

### 4.1 Opérateurs d'Égalité
```javascript
// Égalité faible (avec conversion de type)
"5" == 5;    // true  (⚠️ éviter)
"" == 0;     // true  (⚠️ éviter)
null == undefined;  // true  (⚠️ éviter)

// Égalité stricte (recommandée)
"5" === 5;   // false
"" === 0;    // false
null === undefined;  // false

// Différence
"5" !== 5;   // true
5 != "5";    // false (⚠️ éviter)
```

### 4.2 Opérateurs Logiques
```javascript
// AND (&&) - retourne la première valeur falsy ou la dernière valeur
let a = true && "ok";     // "ok"
let b = false && "ok";    // false
let c = null && "ok";     // null

// OR (||) - retourne la première valeur truthy ou la dernière valeur
let d = "texte" || "défaut";  // "texte"
let e = "" || "défaut";       // "défaut"

// Nullish coalescing (??) - null/undefined seulement
let f = null ?? "défaut";     // "défaut"
let g = 0 ?? "défaut";        // 0 (car 0 n'est pas null/undefined)

// Optional chaining (?.)
let obj = {a: {b: {c: 42}}};
let valeur = obj?.a?.b?.c;  // 42 (sécurisé)
```

## 5. Fonctions et Classes

### 5.1 Déclarations de Fonctions
```javascript
// Déclaration classique (hoisted)
function addition(a, b) {
    return a + b;
}

// Expression de fonction (non hoisted)
const soustraction = function(a, b) {
    return a - b;
};

// Fonction fléchée (arrow function)
const multiplication = (a, b) => {
    return a * b;
};

// Fonction fléchée avec retour implicite
const division = (a, b) => a / b;

// Paramètres par défaut et rest parameters
function logger(prefix = "LOG:", ...messages) {
    console.log(prefix, ...messages);
}
```

### 5.2 Classes et Prototypes
```javascript
// Déclaration de classe
class Animal {
    // Propriétés privées (nouveau en JS)
    #age = 0;
    
    // Constructeur
    constructor(nom) {
        this.nom = nom;
    }
    
    // Méthode d'instance
    parler() {
        return `${this.nom} fait un bruit`;
    }
    
    // Getter
    get age() {
        return this.#age;
    }
    
    // Méthode statique
    static créerAnimaux(...noms) {
        return noms.map(nom => new Animal(nom));
    }
}

// Héritage
class Chat extends Animal {
    constructor(nom) {
        super(nom);  // Appel du constructeur parent
    }
    
    parler() {
        return `${super.parler()} - Miaou!`;
    }
}
```

## 6. Gestion des Erreurs

### 6.1 Try-Catch
```javascript
try {
    // Code susceptible de générer une erreur
    throw new Error("Oups!");
} catch (erreur) {
    // Gestion de l'erreur
    console.error(erreur.message);
} finally {
    // S'exécute toujours
    console.log("Nettoyage");
}

// Erreurs personnalisées
class MonErreur extends Error {
    constructor(message) {
        super(message);
        this.name = "MonErreur";
    }
}
```

## 7. Modules

### 7.1 Import/Export
```javascript
// fichier: math.js
export const PI = 3.14159;
export function carre(x) {
    return x * x;
}
export default class Calculator {
    add(a, b) { return a + b; }
}

// fichier: main.js
import Calculator, { PI, carre } from './math.js';
import * as Math from './math.js';
```

## 8. Asynchrone

### 8.1 Promesses et Async/Await
```javascript
// Création d'une promesse
const maPromesse = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Succès!");
        // ou
        // reject(new Error("Échec!"));
    }, 1000);
});

// Utilisation avec .then()
maPromesse
    .then(resultat => console.log(resultat))
    .catch(erreur => console.error(erreur));

// Utilisation avec async/await
async function fonctionAsynchrone() {
    try {
        const resultat = await maPromesse;
        console.log(resultat);
    } catch (erreur) {
        console.error(erreur);
    }
}
```

## 🎓 Points Clés à Retenir

1. La syntaxe JavaScript est flexible mais nécessite de la rigueur
2. Toujours utiliser les comparaisons strictes (===)
3. Préférer const et let à var
4. Utiliser les fonctions fléchées pour les callbacks
5. La gestion des erreurs est importante
6. L'asynchrone est fondamental en JavaScript

## 📚 Pour Aller Plus Loin

- Étudier les patterns de conception
- Explorer l'API du DOM
- Comprendre l'event loop
- Maîtriser les closures
- Découvrir les nouveautés ECMAScript
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
