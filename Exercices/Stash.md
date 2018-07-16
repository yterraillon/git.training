# Stash

## durée: 10 min

Documentation : <https://git-scm.com/docs/git-stash>

## Définition

Le stash permet de "remiser" un travail en cours (= non commité) dans une pile pour pouvoir le reprendre plus tard.
Une fois les modifications stashées, toutes les opérations habituelles de git sont possibles.

## En pratique

Depuis master, créer et atteindre une branche "stash"

Ajouter un fichier "MiddleWare.cs" dans le répertoire de la solution.
Modifier le fichier "Filter.cs" et y ajouter la ligne
`/// Stash comment`

Observer les changements avec un `git status`, et l'historique avec un `git log`.
Les fichiers ne sont actuellement ni commités, ni même dans l'index git (dans le cas de Middleware.cs).

Jouer la commande `git stash`, et observer à nouveau le statut et l'historique.

Atteindre la branche master. Puis revenir à la branche "stash"
Modifier le fichier Config.cs et y ajouter la ligne
`/// another change`

Observer les changements mis de coté avec la commande `git stash list` et appliquer ceux-ci avec `git stash apply`

Effectuer à nouveau des modifications sur les fichiers, les stasher à nouveau en utilisant la commande `git stash hello world`
Observer la stash list à nouveau. Observer le diff du stash en jouant un `git stash show`

Cette fois, supprimer le dernier stash avec `git stash drop`

Pour terminer, supprimer le fichier MiddleWare.cs depuis l'explorateur