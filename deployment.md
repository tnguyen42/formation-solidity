# Votre contrat
Félicitation, votre contrat est désormais terminé !
Voici ci-dessous une des implémentations possible de ce contrat:

> Require ne permettant pour le moment pas de retourner de message d'erreur, dans le cas ou c'est bien le propriétaire du contrat, j'ai décidé de renvoyer un message d'erreur au lieu de juste faire un require

```javascript
pragma solidity ^0.4.24;

contract CapsuleTemporelle {
    string message;
    address owner;
    uint creationtime;


    constructor(string _message) public {
        message = _message;
        owner = msg.sender;
        creationtime = block.timestamp;
    }

    function getMessage() public view returns (string) {
        require(owner == msg.sender);
        if (now > creationtime + 365 * 1 days) {
            return message;
        } else {
            return "Vous ne pouvez pas lire le message avant 1 an !";
        }
    }

}
```


# Déploiement du contrat

Actuellement sur https://remix.ethereum.org/ nous avons utilisé les paramètres par défault, sois la VM javascript pour faire nos tests. Nous n'avons pas directement publié le contrat sur la blockchain. C'est donc le moment de le faire !

# Créer une adresse ethereum

Pour intéragir avec la blockchain il vous faut une adresse ethereum.
Nous allons utiliser métamask pour la creer, et pour intéragir avec ethereum depuis votre navigateur,: https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn

Aprés l'installation, cliquez sur l'icone de métamask en haut a droite de votre navigateur, acceptez les conditions d'utilisations et définissez un mot de passe.

