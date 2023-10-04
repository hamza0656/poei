# Exercices !

Réalisez les exercices ci-dessous.

Dans tous les cas, les steps devront retourner un simple message.

## 1 : Issues

Créez un workflow qui se lance lorsqu'une issue est ouverte

Elle enverra un message 'issue créée'

### Aides du poulet

- Aucune difficulté ici !

### Aides du poussin

- Le trigger donc vous avez besoin est `issue`
- Il prend en attribut `types` un tableau de types d'évènements (ici `opened`)

## 2 : Pull requests

Créez un workflow qui se lance lorsqu'une PR est fermée, et qui affichera un message uniquement si la PR est mergée

### Aides du poulet

- Vous devrez ajouter sur le job une condifiont `if`
- Elle vérifiera que l'attribut `merged` de la PR est à `true`
- Vous devez rechercher l'évènement `merged` de `pull_request`, qui est un `event` du contexte `github`

### Aides du poussin

- Le trigger donc vous avez besoin est `pull_request`, avec pour type `closed`
- Concernant la vérification, elle ressemble à ceci : `if: github.event_name == 'pull_request'`

## 3 : Next One

Créez un workflow qui se lancera lorsque celui de l'exercice précédent est terminé

Il affichera également un message

### Aides du poulet

- Vous aurez besoin de `workflow_run`, et de son attribut `workflows`
- N'oubliez pas de donner un nom à votre workflow précédent, sinon vous aurez du mal à l'espionner !

### Aides du poussin

- Vous devrez ajouter à `workflow_run` un attribut `workflows` qui contient le nom du workflow à exécuter
- Vous devrez ajouter à `workflow_run` un attribut `types` qui contient le type d'évènement à vérifier. Ici : `completed`

## 4 : Workflow depends

Créez un workflow qui contiendra deux jobs :

- Le premier devra être lancé manuellement
- Le second se lancera uniquement lorsque le précédent aura été exécuté

Dans les deux cas, envoyez un message

### Aides du poulet

- Vous aurez besoin de `workflow_dispatch`

### Aides du poussin

- L'attribut `needs` devra être ajouté sur le second job. Il contiendra le nom du workflow précédent
