# Fonction d'ordre supérieur

Définition:

C'est une fonction qui reçoit une fonction en paramètre où retourne une nouvelle fonction.

## Fonction en paramètre - Le nouveau filter

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
## Fonction en sortie - Le créateur d'opérations

Maintenant je vais créer une function qui va permetre de retourner une nouvelle fonction pour créer une opération que l'on souhaite.

```javascript
const operations = ["+", "-", "/", "*"];
function operationMaker(type){ 
  if(operations.some(el=> el === type )) return (nb1 ,nb2) => eval(nb1 + type + nb2); 
  throw("Error type");
}

//!\ Zone de test /!\
const  subtraction = operationMaker("-");
console.log( subtraction(7,5));
const multiplying = operationMaker("*");
console.log(multiplying(7,5));
const adding = operationMaker("+");
console.log(adding (7,5));
const dividing = operationMaker("/");
console.log(dividing(7,5));
const dividing = operationMaker("ici");

console.log(operationMaker("*")(7,3));
```
