# Cherry-pick

*durée: 15 / 20 min*

## Définition 

Le cherry-pick permet de récupérer un commit spécifique depuis une branch pour l'appliquer en tant que dernier commit d'une autre.


## En pratique:

Depuis master, créer et atteindre une branche 'cherry-pick-me'

A l'aide d'un éditeur de fichier, insérer dans Config.cs : 
`/// a config file`

Commiter ce changement avec le message "Modif Config.cs". 

A présent modifier le contenu du fichier Settings.cs et y insérer 
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

Jouer la commande `git cherry-pick __433411e842d6c46658982b74625b1ff5f64e7da2__`

Regarder à nouveau l'historique du master.


## En cas de conflit:

Depuis master créer et atteindre une branche 'cherry-pick-issue'

Modifier le contenu du fichier Settings.cs et y insérer 
`/// settings 2`

Commiter ce changement avec le message "Modif Settings.cs for conflict". 

Cherry-picker le commit "Modif Settings.cs" depuis la branche 'cherry-pick-me'