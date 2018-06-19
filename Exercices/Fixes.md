# Merge

*durée: 10 min*

## Revert

Crée un commit qui est l'exact inverse de celui précisé en paramètre.

### En pratique : 

Créer une branche 'fixes' depuis le master et l'atteindre.

Modifier le fichier Error.html en y ajoutant la ligne 
`<!--Error-->`

Commiter ce changement avec le message "Error".

Pusher. 

Faire un revert du dernier commit `git revert COMMITHASH`

Observer le résultat dans l'historique. 
Pusher et observer les fichiers modifiés sur git.  

## Reset 

supprimer le(s) dernier(s) commit(s) (mets les changements dudit commit comme non commités)
`git reset HEAD~1` où 1 est le nombre de commits depuis le dernier à supprimer. 

### En pratique : 

Depuis la branche 'fixes', jouer un `git reset HEAD~1` pour supprimer le commit de revert. 

Observer le statut des fichiers, et le log. 


## Clean

Supprime les fichiers et répertoires non traqués. 
`git clean -df` -d pour effacer les répertoires, -f pour effacer les fichiers. 


### En pratique :

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

### En pratique : 

Supprimer les changements qui ont été induits par le reset. 

Observer le statut des fichiers, et le log. 

## Blame

Permet de savoir qui a modifié quelle ligne dans un fichier.

### En pratique : 

Faire un `git blame Startup.cs` et observer le résultat. 
