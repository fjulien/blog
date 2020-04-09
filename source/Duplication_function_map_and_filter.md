# Duplication function map and filter for test callback

## Creation class to duplicate classic array 

```javascript
class DuplicationArrayClass{
  constructor(arrayOfNumber) {
      this.arrayOfNumber = arrayOfNumber;
    }
  
  /*
  Function filter of JS
  */
  filterByMe(conditionFiltered){
    let result = [];
    for(let i = 0 ; i<this.arrayOfNumber.length ; i++){
        if (conditionFiltered(this.arrayOfNumber[i])) result.push(this.arrayOfNumber[i]);
    }
    return result;
  }
  
  /*
  Function map of JS
  */
  mapByMe(updaterOfElement){
    let result = []
    for(let i = 0 ; i<this.arrayOfNumber.length ; i++){
        result.push(updaterOfElement(this.arrayOfNumber[i]));
    }
    return result;
  }
}
```

## Add map

```javascript
class DuplicationArrayClass{
  constructor(arrayOfNumber) {
      this.arrayOfNumber = arrayOfNumber;
    }
  
  // Function map of JS
  mapByMe(updaterOfElement){
    let result = []
    for(let i = 0 ; i<this.arrayOfNumber.length ; i++){
        result.push(updaterOfElement(this.arrayOfNumber[i]));
    }
    return result;
  }
}
```

## Add filter

```javascript
class DuplicationArrayClass{
  constructor(arrayOfNumber) {
      this.arrayOfNumber = arrayOfNumber;
    }
  
  // Function filter of JS
  filterByMe(conditionFiltered){
    let result = [];
    for(let i = 0 ; i<this.arrayOfNumber.length ; i++){
        if (conditionFiltered(this.arrayOfNumber[i])) result.push(this.arrayOfNumber[i]);
    }
    return result;
  }
  
  // Function map of JS
  mapByMe(updaterOfElement){
    let result = []
    for(let i = 0 ; i<this.arrayOfNumber.length ; i++){
        result.push(updaterOfElement(this.arrayOfNumber[i]));
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
