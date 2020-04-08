# Duplication function map and filter for test callback

```javascript
class DuplicationMethod{
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

const arrayNumbers = [1,2,3,4,5,6,7,8,9];
const duplication = new DuplicationMethod(arrayNumbers);
const condition = number => number === 5 || number === 4;
const edit = number => "Hello word! : " + (number + 1000);

/*
Tests
*/
console.log(duplication.filterByMe(condition).join("") === arrayNumbers.filter(condition).join(""));
console.log(duplication.mapByMe(edit).join("") === arrayNumbers.map(edit).join(""));

/*
Examples
*/
console.log(duplication.filterByMe(condition));
console.log(duplication.mapByMe(edit));
```
