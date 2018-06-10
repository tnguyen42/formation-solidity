# Require

Maintenant que nous avons enregistré notre propriétaire, il faut limitier l'accès.
En solidity, il faut utiliser le mot clé require qui va faire en sorte que la fonction s’arrête et renvoie une erreur si certaines conditions ne sont pas respectées :

```javascript
pragma solidity ^0.4.24;
contract Example {

	function olderThan21 (uint _age) public {
		require(_age > 21);
		// do your stuff
	}
}
```
Si la personne à moins de 21 ans, la fonction s'arrete immédiatement et rembourse le gas restant à l'utilisateur.

# A vous de jouer :
> * Limiter l'accés à votre fonction get() pour n'autoriser que le propriétaire
> * Limiter l'accés à votre fonction get() pour ne pas renvoyer le message avant 1 an
