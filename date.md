# Dates

Pour pouvoir limiter l'acces à 1 an, il nous faut en premier enregistrer la date de création du contrat.
Pour cela vous pouvez utiliser le mot clé 'now' au moment de la création du contrat.
La variable now (maintenant) va retourner l'horodatage actuel unix (le nombre seconde écoulées depuis le 1er janvier 1970).

# Unités de temps
Solidity fourni nativement des unités pour gérer le temps.

Solidity a des unités de temps seconds (secondes), minutes, hours (heures), days (jours) et weeks (semaine). Ils vont se convertir en un uint correspondant au nombre de seconde de ce temps. Donc 1 minutes est 60, 1 hours est 3600 (60 secondes x 60 minutes), 1 days est 86400 (24 heures x 60 minutes x 60 seconds), etc.

Voici un exemple montrant l'utilité de ces unités de temps :

```javascript
uint lastUpdated;

// Défini `lastUpdated` à `now`
function updateTimestamp() public {
  lastUpdated = now;
}

// Retournera `true` si 5 minutes se sont écoulées
// depuis que `updateTimestamp` a été appelé, `false`
// si 5 minutes ne se sont pas passées
function fiveMinutesHavePassed() public view returns (bool) {
  return (now >= (lastUpdated + 5 minutes));
}
```

# A vous de jouer :
> Initialiser votre variable creationTime à now dans votre constructeur