# Cherry-pick

*durée: 10 min*

## Définition 

Le stash permet de "remiser" un travail en cours (= non commité) dans une pile pour pouvoir le reprendre plus tard. 
Une fois les modifications stashées, il est possible toutes les opérations habituelles de git sont possibles. 


## En pratique

Depuis master, créer et atteindre une branche "stash"

Ajouter une fichier "MiddleWare.cs" dans le répertoire de la solution. 
Modifier le fichier "Filter.cs" et y ajouter la ligne 
`/// Stash comment`

Observer les changements avec un `git status`, et l'historique avec un `git log`.
Les fichiers ne sont actuellement ni commités, ni même dans l'index git (dans le cas de Middleware.cs).

Jouer la commande `git stash`, et observer à nouveau le statut et l'historique. 

Atteindre la branche master. Puis revenir à la branche "stash"
Modifier le fichier Config.cs et y ajouter la ligne 
`/// another change`

Observer les changements mis de coté avec la commande `git stash list` et appliquer ceux-ci avec `git stash apply`


Effectuer à nouveau des modifications sur les fichiers, les stasher à nouveau, mais cette fois les supprimer avec `git stash drop`