# Fonctions
Maintenant que nous pouvons stocker notre message, nous devons initialiser celui-ci.
Mais avant tout, voyons comment fonctionne les fonctions en Solidity :


Une fonction qui prend en paramètre un string, qui retourne également un string et dont corps de la fonction est vide pour l'instant :
```javascript
function myFunction(string _name) {

}
```


# Fonctions privées / publiques

En Solidity, les fonctions sont publiques par défaut. Il est cependant recommandé de toujours préciser le type de votre fonction, même si celle-ci est publique. Cela signifie que n'importe qui (ou n'importe quel contrat) peut appeler la fonction de votre contrat et exécuter son code.

Évidemment, ce n'est pas toujours ce que l'on veut, cela pourrait rendre votre contrat vulnérable aux attaques. Il est donc recommandé de marquer vos fonctions comme private (privées) par défaut, puis de ne rendre public (publiques) seulement les fonctions que vous voulez exposer à tout le monde.

Voici comment déclarer une fonction privée :

```javascript
function _myFunction() private {

}
```
Comme vous pouvez le voir, nous avons utilisé le mot-clé private après le nom de la fonction.
Cela veut dire que seulement les autres fonctions de notre contrat pourront appeler cette fonction.

# Valeurs retournées
Pour retourner une valeur à partir d'une fonction, cela ressemble à ça :
```javascript
function myFunction() public returns (string) {

}
```
En Solidity, une déclaration de fonction indique le type de la valeur retournée (dans ce cas string).

## Modificateurs de fonction
```javascript
string greeting = "What's up dog";

function sayHello() public returns (string) {
  return greeting;
}
```
La fonction ci-dessus ne change pas un état en Solidity - c.-à-d. elle ne change pas une valeur et n'écrit rien.

Dans ce cas là, nous pouvons la déclarer comme une fonction view (vue), cela veut dire qu'elle va seulement voir des données sans les modifier :
```javascript
function sayHello() public view returns (string) {}
```
Solidity a aussi des fonctions pure, cela veut dire que vous n'avez même pas accès à des données de l'application. Par exemple :
```javascript
function _multiply(uint a, uint b) private pure returns (uint) {
  return a * b;
}
```
Cette fonction ne lit aucune donnée du contrat - elle retourne une valeur qui dépend seulement de ses arguments. Dans ce cas là, nous déclarerons la fonction comme pure.

> Remarque: Il peut être difficile de se rappeler quand marquer les fonctions comme étant pure/view. Heureusement, le compilateur Solidity est bon pour vous avertir quand vous devriez utiliser l'un ou l'autre de ces modificateurs.

# Constructeur

Le constructeur est une fonction qui à la particularité de n'être appelé qu'une seule fois lors de la création du contrat

Voici comment déclarer un constructeur :
```javascript
constructor(string _age) public {

}
```
> À noter : un constructeur peut recevoir des arguments mais ne peut pas retourner de valeurs.

# A vous de jouer :

> * Au moment de déployer votre contrat vous devez initialiser votre message
> * Créer une fonction permettant de retourner votre message (sans restriction pour l'instant)