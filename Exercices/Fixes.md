# Fix it, Patch it, clean it

## durée: 10 min

## Revert

Crée un commit qui est l'exact inverse de celui précisé en paramètre.

### Revert - En pratique

Créer une branche 'fixes' depuis le master et l'atteindre.

Modifier le fichier Error.html en y ajoutant la ligne
`<!--Error-->`

Commiter ce changement avec le message "Error".

Pusher.

Faire un revert du dernier commit (remplacer COMMITHASH par le hash du commit à reverter) `git revert COMMITHASH`

Observer le résultat dans l'historique.
Pusher et observer les fichiers modifiés sur git.  

## Reset

supprimer le(s) dernier(s) commit(s) (mets les changements dudit commit comme non commités et en non prêts (stagés) pour le commit)
`git reset HEAD~1` où 1 est le nombre de commits depuis le dernier à supprimer.

### Reset -En pratique

Depuis la branche 'fixes', jouer un `git reset HEAD~1` pour supprimer le commit de revert.

Observer le statut des fichiers, et le log.

## Clean

Supprime les fichiers et répertoires non traqués.
`git clean -df` -d pour effacer les répertoires, -f pour effacer les fichiers.

### Clean - En pratique

Depuis la branche 'fixes' Ajouter un nouveau fichier nommé "Exception.cs"

Observer le statut des fichiers.

Supprimer le fichier avec un `git clean -df`
Observer le statut des fichiers, et le log.

Vérifier que le fichier Exception.cs n'est plus présent.

## Checkout

Supprime les changements apportés à un fichier.

`git checkout -- FILENAME` pour ne supprimer les changements que dans un seul fichier.
`git checkout -- .` pour supprimer tous les changements.

Note : ceci n'affecte pas les fichiers non inclus dans l'index git. (ceux-ci nécessitent un clean)

### Checkout - En pratique

Supprimer les changements qui ont été induits par le reset.

Observer le statut des fichiers, et le log.

## Amend

Change le dernier message de commit

### Amend - En pratique

Taper `git commit --amend` puis changer le message de commit. A noter : si le commit a déja été pushé, cela change l'historique, et implique donc un push force

## Blame

Permet de savoir qui a modifié quelle ligne dans un fichier.

### Blame - En pratique

Faire un `git blame Startup.cs` et observer le résultat.

## Problèmes rencontrés fréquemment

Mon git est dans un état bizarre :

- Checker avec un git status
- Regarder dans la ligne de commande si on est pas dans un état de merge ou de rebase (auquel cas : git rebase --abort ou git merge --abort)

Les tags de validation de SL :

- Pb de validation/ push d'un commit cherry pické
- Reset de la branche et recommit pour mettre un tag correct
