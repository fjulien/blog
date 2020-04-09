# Duplication function map and filter for test callback

## Creation class to duplicate classic array 

```javascript
class DuplicationArrayClass{
  constructor(arrayDuplication) {
      this.arrayDuplication = arrayDuplication;
    }
}
```

## Add map method

```javascript
class DuplicationArrayClass{
  constructor(arrayDuplication) {
      this.arrayDuplication = arrayDuplication;
    }
  
  // Function map of JS
  mapByMe(updaterOfElement){
    let result = []
    for(let i = 0 ; i<this.arrayDuplication.length ; i++){
        result.push(updaterOfElement(this.arrayDuplication[i]));
    }
    return result;
  }
}
```

## Add filter method

```javascript
class DuplicationArrayClass{
  constructor(arrayDuplication) {
      this.arrayDuplication = arrayDuplication;
    }
  
  // Function filter of JS
  filterByMe(conditionFiltered){
    let result = [];
    for(let i = 0 ; i<this.arrayDuplication.length ; i++){
        if (conditionFiltered(this.arrayDuplication[i])) result.push(this.arrayDuplication[i]);
    }
    return result;
  }
  
  // Function map of JS
  mapByMe(updaterOfElement){
    let result = []
    for(let i = 0 ; i<this.arrayDuplication.length ; i++){
        result.push(updaterOfElement(this.arrayDuplication[i]));
    }
    return result;
  }
}
```
## Full code with test

```javascript
class DuplicationArrayClass{
  constructor(arrayDuplication) {
      this.arrayDuplication = arrayDuplication;
    }
  
  // Function filter of JS
  filterByMe(conditionFiltered){
    let result = [];
    for(let i = 0 ; i<this.arrayDuplication.length ; i++){
        if (conditionFiltered(this.arrayDuplication[i])) result.push(this.arrayDuplication[i]);
    }
    return result;
  }
  
  // Function map of JS
  mapByMe(updaterOfElement){
    let result = []
    for(let i = 0 ; i<this.arrayDuplication.length ; i++){
        result.push(updaterOfElement(this.arrayDuplication[i]));
    }
    return result;
  }
}

const arrayNumbers = [1,2,3,4,5,6,7,8,9];
const duplicationArrayClass = new DuplicationArrayClass(arrayNumbers);
const condition = number => number === 5 || number === 4;
const edit = number => "Hello word! : " + (number + 1000);

/*
Tests
*/
const isFiltred = duplicationArrayClass.filterByMe(condition).join("") === arrayNumbers.filter(condition).join("");
const isMaped = duplicationArrayClass.mapByMe(edit).join("") === arrayNumbers.map(edit).join("");

if(isFiltred) console.log("Duplication filter success");
if(isMaped) console.log("Duplication map success");
```
