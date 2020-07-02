# Fonction d'ordre supérieur

Définition:

Une fonction d'ordre supérieur c'est tout simplement une fonction qui reçoit une fonction en paramètre où retourne une fonction.

## Avec une fonction en paramètre - Le nouveau filter

Je vais prendre un exemple avec une fonction filter bien connut, au lieu de retourné un table qui retounée les élèments vrai, elle va retourner les deux tableaux. La nous sommes dans le cas ou la fonction va prendre en parametre une autre fonction.

```javascript
function myFilter(arr, func){
  const result = [[], []]; // index 0 pour retours faux et index 1 pour les retour vrai
  for (let element of arr){
    func(element)? result[1].push(element) : result[0].push(element);
  }
  return result;
}

//!\ Zone de test /!\
const listNumbers = [1,2,3,4,5,6,7,8,9];
let isFalseList, isTrueList;

function isEvenNumber(nb){
  return nb%2 === 0
}
[isFalseList, isTrueList] = myFilter(listNumbers, isEvenNumber);

[isFalseList, isTrueList] = myFilter(listNumbers, nb => nb%2 === 0);
console.log(isFalseList);
console.log(isTrueList);
```
## Avec une fonction retourné - Le créateur d'opérations

Maintenant je vais créer une function qui va permetre de retourner une nouvelle fonction pour créer une opération mathématique simple.

```javascript
const operations = ["+", "-", "/", "*"]; // Liste des opérations que j'authorise
function operationMaker(type){ 
  if(operations.some(el=> el === type )) return (nb1 ,nb2) => eval(nb1 + type + nb2); // Si on selection la bonne opération, la fonction nous retoune une nouvelle fonction
  throw("Error type");
}

//!\ Zone de test /!\
const subtraction = operationMaker("-"); // Ici on retourne une soustraction à la variable "subtraction" qu'on peut utilisé plus loin comme fonction
console.log( subtraction(7,5));
// D'autre exemples
const multiplying = operationMaker("*");
console.log(multiplying(7,5));
const adding = operationMaker("+");
console.log(adding (7,5));
const dividing = operationMaker("/");
console.log(dividing(7,5));

console.log(operationMaker("*")(7,3)); // Pour ce cas on n'affecte pas la fonction retournée mais on l'exectue directement, d'ou la syntaxe function()();
```
## Conclution

Ce n'est pas très compliqué finalement!
