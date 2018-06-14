# Working with Git

*durée: 15 / 20 min*

Créer une branche "work", et l'atteindre.

Tout d'abord regardons l'état de la branche avec un `git status` 
Ou avec un alias `git st`

Et l'historique existant avec un `git log`.


## Changements dans les fichiers : 

Ouvrir le fichier Program.cs avec un éditeur, et supprimer les lignes suivantes : 
`using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Threading.Tasks;`

Sauvegarder et fermer le fichier. 

Ouvrir le fichier Startup.cs avec un éditeur, et ajouter la ligne suivante : 

`__services.AddMemoryCache();__

services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);`

Sauvegarder et fermer le fichier. 

Observer les changements avec un `git status`, et l'historique avec un `git log`.

Les fichiers sont modifiés, mais non commités encore. On va corriger cela en faisant un `git commit -am "Mon premier commit"`

-a indique que l'on commite tous les fichiers 
-m "mon message" indique le message de commit

-am est la concaténation des 2 commandes. 

Observer les changements avec un `git status`, et l'historique avec un `git log`.
Afficher le dernier commit avec un `git last`

Pusher les fichiers sur l'origin (créer l'upstream si besoin).

## Ajouts de fichiers

Dans le répertoire de travail, ajouter les fichiers vides suivants (à coté de Startup.cs et Program.cs): 
`Config.cs`
`Settings.cs`
`Filter.cs`

Observer les changements avec un `git status`, et l'historique avec un `git log`.

Commiter les fichiers et observer le statut avec un `git status`. Les fichiers ajoutés ne sont pas encore inclus dans l'index git! 
On va donc devoir les y ajouter. Faire un `git add Training.Git/Config.cs`et observer les changements avec un `git status`.

Il est aussi possible, et plus pratique, d'ajouter les fichiers par lot avec un `git add .`

Maintenant que les fichiers sont ajoutés, on peut les commiter. 
Faire un `git status` et noter qu'il est précisé que le local est "1 commit ahead of origin".

Pusher les fichiers sur l'origin.

## Retour au master

__ La partie se déroulant sur github n'est pas développée ici. __
Atteindre la page https://github.com/YOURUSERNAME/git-training/branches.
Cliquer sur le bouton "New Pull request" à coté du nom de la branch récemment pushée, puis "Create Pull Request"
Enfin Merger la pull request depuis l'onglet "Conversation".

Retourner sur Git bash, et atteindre le master. 
Faire un `git fetch`, puis un `git status`. Pour le moment nous n'avons pas récupéré les changements distants.

On va le faire en faisant un `git pull`. Puis faire un `git log` pour observer les changements. 
