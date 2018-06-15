# Merge

*durée: 10 min*

## Définition 

Une merge fusionne deux historiques ensemble. 

## Avant de démarrer 

Regarder la config de git, et repérer la ligne `merge.ff= XXXX` (true ou false)
Si elle est à false, on va la passer à true. 

`git config merge.ff true`

## En pratique

Créer et atteindre une branche 'a-merger' depuis le master.
Modifier le fichier Index.html en y ajoutant la ligne:
`<!--Index-->`

Commiter ce changement avec le message "Index"

Atteindre le master, et de là créer et atteindre une branche "cible-merge". 
Vérifier que la branche ne comporte pas le commit "Index" dans son historique. 

Modifier le fichier Error.html en y ajoutant la ligne 
`<!--Error-->`

Commiter ce changement avec le message "Error". 


On va à présent merger la branche "a-merger" dans la branche "cible-merge". 
Observer l'historique de la branche "cible-merge". 

Jouer la commande `git merge a-merger`


