# Cherry-pick

*durée: 15 / 20 min*

## Définition 

Le cherry-pick permet de récupérer un commit spécifique depuis une branch pour l'appliquer en tant que dernier commit d'une autre.


## En pratique:

Depuis master, créer et atteindre une branche 'cherry-pick-me'

A l'aide d'un éditeur de fichier, insérer dans Config.cs : 
`/// a config file`

Commiter ce changement avec le message "Modif Config.cs". 

A présent modifier le contenu du fichier Settings.cs et y insérer en haut du fichier
`/// settings 1`

Commiter ce changement avec le message "Modif Settings.cs". 

__2 commits distincts doivent être visibles dans l'historique__

Afficher le log de la branche et repérer les lignes décrivant les commits. Elles doivent ressembler à ceci : 

`commit __433411e842d6c46658982b74625b1ff5f64e7da2__
Author: Yann TERRAILLON <yann.terraillon@seloger.com>
Date:   Mon Jun 11 18:20:39 2018 +0200
	Modif Config.cs
`

Double-cliquer sur le hash du commit "Modif Config.cs" (en gras dans l'exemple précédent) pour le copier. 

Retourner sur la branche master et afficher l'historique avec un `git log`. 

Jouer la commande `git cherry-pick __433411e842d6c46658982b74625b1ff5f64e7da2__ `

Regarder à nouveau l'historique du master.


## En cas de conflit:

Depuis master créer et atteindre une branche 'cherry-pick-issue'

Modifier le contenu du fichier Settings.cs et y insérer en haut du fichier
`/// settings 2`

Commiter ce changement avec le message "Modif Settings.cs for conflict". 

Cherry-picker le commit "Modif Settings.cs" depuis la branche 'cherry-pick-me'

Un message similaire à celui-ci apparait : 

`$ git cherry-pick 33db9aed04b88e26f464ad06e47ef97d495f1964`
`error: could not apply 33db9ae... temp`
`hint: after resolving the conflicts, mark the corrected paths`
`hint: with 'git add <paths>' or 'git rm <paths>'`
`hint: and commit the result with 'git commit'`

Les modifications sont en conflit, car le même fichier est modifié par 2 commits incompatibles. Afficher le statut nous donne plus d'informations : 

`On branch cherry-pick-issue`
`You are currently cherry-picking commit 33db9ae.`
`(fix conflicts and run "git cherry-pick --continue")`
`(use "git cherry-pick --abort" to cancel the cherry-pick operation)`

`Unmerged paths:`
`(use "git add <file>..." to mark resolution)`

`both modified:   Training.Git/Settings.cs`

`no changes added to commit (use "git add" and/or "git commit -a")`

Pour résoudre le conflit, plusieurs façons sont possibles. Nous le ferons à la main dans le cadre de cet exercice. 

Ouvrir le fichier Settings.cs. Les lignes conflictuelles sont marquées par des chevrons : <<<<<<< et >>>>>>>>

`<<<<<<< HEAD`
`/// settings 2`
`=======`
`/// settings 1`
`>>>>>>> 33db9ae... cherry-pick-me`

Dans le cadre de cet exercice nous allons conserver les 2 modifications. Editer le fichier pour supprimer les lignes suivantes : 
`<<<<<<< HEAD`
`=======`
`>>>>>>> 33db9ae... cherry-pick-me`

Dans git bash marquer le conflit comme résolu en faisant un `git add Training.Git/Settings.cs` ou un `git add`. __Attention__ le git add . va marquer tous les fichiers comme résolus. 
Il faut donc s'assurer que les conflits sont effectivement bien résolus avant. 

Une fois les conflits marqués comme résolus, on va continuer le cherry-pick (qui s'était mis en pause pour la résolution du conflit.)

`git cherry-pick --continue`

A noter que l'on peut aussi arrêter l'opération et revenir à l'état d'avant d'avoir démarré le cherry-pick en faisant un `git cherry-pick --abort`