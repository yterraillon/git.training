# Extras

Quelques commandes supplémentaires à connaitre.

## git add interactive

Après un travail qui implique des modifications et l'ajout de nombreux fichiers, on va parfois vouloir choisir finement les fichiers qui seront inclus dans le commit, et ceux qui n'y seront pas. Pour éviter de faire un git add de chaque fichier, on va utiliser un `git add -i`.

Un menu similaire va apparaitre :

```bash
           staged     unstaged path
  1:    unchanged        +2/-0 Exercices/Extras.md
  2:    unchanged        +4/-1 Exercices/WorkingWithGit.md

*** Commands ***
  1: [s]tatus     2: [u]pdate     3: [r]evert     4: [a]dd untracked
  5: [p]atch      6: [d]iff   7: [q]uit   8: [h]elp

```

Nous ne détaillerons ici que l'update et le add untracked. Pour creuser :

- <https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging>
- <https://coderwall.com/p/u4vjkw/git-add-interactive-or-how-to-make-amazing-commits>

Taper 'u' dans le menu choisit le menu 'update. Il faut ensuite sélection les fichiers qui seront inclus, précisés par leur numéro et séparés par une virgule. Il est possible de le faire en plusieurs fois. Une fois tous les fichiers sélectionnés (marqués d'une * dans la liste). Laisser vider et appuyer sur la touche entrée pour les passer en "staged for commit".

La commande 'a' (pour add untracked) va afficher les fichiers non indexés par git et propose de les sélectionner de la même façon que précédemment.

Il est possible d'utiliser la commade s (status) pour voir l'état actuel des opérations. Quitter et observer le résultat avec un git status.

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

Dw
|
Cpr
|
B
|
A

A noter : cela peut être fait automatiquement via la config de git : pull.rebase=true