# Return THIS!

La petite astuce du jour est sur ce fameux THIS! Dans une class, qu'est ce qu'il se passe quand on retourne THIS?

```javascript
class Computer {
  name = "Super Computer";
  
  start(){
    console.log("start");
    return this;
  }
  showWindow(){
    console.log("showWindow");
    return this;
  }
}

const newComputer = new Computer();
newComputer.start().showWindow();

```
