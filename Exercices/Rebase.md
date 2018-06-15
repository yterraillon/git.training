# Rebase

*durée: 15/20 min*

## Définition 

Un rebase d'une branche A sur une branche B va appliquer tous les commits de la branche A sur l'historique de la branche B.

Exemple avec 2 historiques : 

branche A : A-B-C-X-Y-Z  (X, Y, Z sont les commits qui ont été créés sur la branche)
branche B : A-B-C-D

depuis la branche A, `git rebase B` va changer l'historique de A par celui de B et appliquer les commits dessus. Elle devient ainsi : 

branche A : A-B-C-D-X-Y-Z

## En Pratique

Depuis le master créer une branche 'nouvel-historique'

Modifier le fichier Contact.html en y ajoutant la ligne:
`<!--Contact-->`

Commiter ce changement avec le message "Contact"

Atteindre le master, et de là créer et atteindre une branche "cible-rebase". 
Vérifier que la branche ne comporte pas le commit "Contact" dans son historique. 

Modifier le fichier About.html en y ajoutant la ligne 
`<!--About-->`

Commiter ce changement avec le message "About". 
Pusher ces changements sur l'origin.

On va à présent rebaser la branche 'cible-rebase' sur la branche 'nouvel-historique'
Dans la branche courante, jouer la commande `git rebase nouvel-historique`

Observer le résultat dans l'historique de la branche. 

A noter : aucun nouveau commit n'a été créé.

Observer à présent le statut dans lequel on se trouve : il y est possible de faire un pull depuis l'origin. Si on pushe, le push va être rejeté. 
Pourquoi : l'historique de l'origin et celui du local sont différents. Il faut les resynchroniser. 
On va donc faire un `push --force` pour forcer le local sur l'origin. 

A noter : il est hautement recommandé de vérifier 2 fois avant de faire un push force, sous peine de perdre son historique de travail. 


## En cas de conflit :

En changeant l'historique, des conflits peuvent arriver de la même façon que lors d'un cherry-pick.
Ils se résolvent aussi de la même façon. 
La différence sera dans les commandes à jouer après résolution : 

`git rebase --continue` pour poursuivre le rebase 
`git rebase --abort` pour revenir à l'état d'avant rebase


## Rebase interactive : 

Il est possible de profiter du rebase pour regrouper ("squasher") des commits. 

Depuis le master créer une branche 'rebase-interactive'

Modifier le fichier Contact.html en y ajoutant la ligne:
`<!--Contact-->`

Commiter ce changement avec le message "Contact"

Modifier le fichier About.html en y ajoutant la ligne 
`<!--About-->`

Commiter ce changement avec le message "About"

Jouer la commande `git rebase master -i` (-i pour interactive). 

Git propose d'abord de sélectionner les commits qui vont être retenus (via le même éditeur qu'on a déjà rencontré.)

Vocabulaire : 
'push' pour conserver le commit (p)
'squash' pour merger le commit avec le précédent (s)

__le premier commit de la liste sera toujours à laiser en push__

Dans notre cas nous allons squasher le 2eme commit. 
Aller au début de sa ligne avec le curseur, appuyer sur la touche S une fois, puis suppr jusqu'à avoir supprimer le mot 'push'. Taper 'squash' à la place, 
puis ctrl+c, et enfin 'wq'

Git va alors appliquer les commits, puis proposer de définir un nouveau message pour celui qui va être un nouveau commit (car il est devenu une combinaison de 2 commits)

L'édition des messages se fait de la même façon que la sélection des commits. Sinon il est possible de supprimer une ligne directement en appuyant 2 fois sur 'd'

Une fois le squash terminé, observer l'historique des commits.
