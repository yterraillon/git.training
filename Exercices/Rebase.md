# Rebase

*durée: 15 min*

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

On va à présent rebaser la branche 'cible-rebase' sur la branche 'nouvel-historique'
Dans la branche courante, jouer la commande `git rebase nouvel-historique`

Observer le résultat dans l'historique de la branche. 

A noter : aucun nouveau commit n'a été créé.

## En cas de conflit :

En changeant l'historique, des conflits peuvent arriver de la même façon que lors d'un cherry-pick.
Ils se résolvent aussi de la même façon. 
La différence sera dans les commandes à jouer après résolution : 

`git rebase --continue` pour poursuivre le rebase 
`git rebase --abort` pour revenir à l'état d'avant rebase


## Rebase interactive : 

Il est possible de profiter du rebase pour regrouper ("squasher") des commits. 


