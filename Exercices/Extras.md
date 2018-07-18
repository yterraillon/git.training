# Extras

Quelques commandes supplémentaires à connaitre. 

## git add interactive

## git pull --rebase

Le git pull tel qu'il est fonctionne réalise en fait 2 commandes :
`git fetch` suivi de `git merge origin`

Comme il s'agit d'un merge, cela signifie que dans le cas où il y a une différence entre le local et l'origin, un nouveau point de ocmmit va être créer. 
Exemple :
Origin (après qu'une pull request a été effectuée et mergée)

Cpr
|
B
|
A

Local (après un commit de travail)
Dw
|
B
|
A

Si l'on fait un pull, on va créer un point de commit dans l'historique à cause du merge, ce qui n'est pas désiré. A la place on va faire un `git pull --rebase`, pour arriver à :