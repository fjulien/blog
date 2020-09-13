# Return THIS!

La petite astuce du jour est sur ce fameux THIS! Dans une class, qu'est ce qu'il se passe quand on retourne THIS?

```javascript
class InspectorGadget {
  
  static goGoGadgetHelicopter(){
    console.log("start");
    return this;
  }
  static goGoGadgetDecodeURI(url){
    console.log(decodeURIComponent(url));
    return this;
  }
  static goGoGadgetUmbrella(){
    console.log("showWindow");
    return this;
  }
}

const URL = "https%3A%2F%2Ffr.wikipedia.org%2Fwiki%2FInspecteur_Gadget_(s%25C3%25A9rie_t%25C3%25A9l%25C3%25A9vis%25C3%25A9e_d%2527animation%2C_1983)"

InspectorGadget.goGoGadgetDecodeURI(URL).goGoGadgetHelicopter().goGoGadgetUmbrella();

```
