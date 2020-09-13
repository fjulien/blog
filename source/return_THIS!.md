# Return THIS!

La petite astuce du jour est sur ce fameux THIS! Dans une class, qu'est ce qu'il se passe quand on retourne THIS?

```javascript
class InspectorGadget {
  name = "Super Computer";
  
  goGoGadgetHelicopter(){
    console.log("start");
    return this;
  }
  goGoGadgetDecodeURI(url){
    console.log(decodeURIComponent(url));
    return this;
  }
    goGoGadgetUmbrella(){
    console.log("showWindow");
    return this;
  }
}
const URL = "https%3A%2F%2Ffr.wikipedia.org%2Fwiki%2FInspecteur_Gadget_(s%25C3%25A9rie_t%25C3%25A9l%25C3%25A9vis%25C3%25A9e_d%2527animation%2C_1983)
Decoded URI: https://fr.wikipedia.org/wiki/Inspecteur_Gadget_(s%C3%A9rie_t%C3%A9l%C3%A9vis%C3%A9e_d%27animation,_1983)";

InspectorGadget().goGoGadgetDecodeURI().goGoGadgetHelicopter()goGoGadgetUmbrella();

```
