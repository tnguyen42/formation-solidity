# Propriétaire

Maintenant que nous enregistrons et récupérons notre message, il ne faudrais pas que n'importe qui puisse le lire ! Il nous faut donc enregistrer et vérifier qui est le propriétaire de ce message

# msg.sender
En Solidity, il existe des variables globales accessibles à toutes les fonctions. L'une d'elles est msg.sender, qui fait référence à l'address de la personne (ou du smart contract) qui a appelée la fonction actuelle.

> Remarque : En Solidity, l'exécution d'une fonction nécessite obligatoirement un appel extérieur. Un contrat va juste rester là dans la blockchain à ne rien faire jusqu'à ce que quelqu'un appelle un de ses fonctions. Il y aura toujours un msg.sender.

Utiliser msg.sender apporte de la sécurité à la blockchain Ethereum - la seule manière pour quelqu'un de modifier les données d'un autre serait de lui voler sa clé privée associée à son adresse Ethereum.

```javascript
constructor() public {
  // vous pouvez utiliser la variable msg.sender
}
function myFunction() public {
  // vous pouvez utiliser la variable msg.sender
}
```

Pour déterminer le propriétaire nous allons récuperer son adresse au moment de la création du contrat, dans le constructor, et l'enregistrer dans la variable 'owner'

# A vous de jouer :
> Dans le constructor, enregistrer l'adresse du propriétaire
