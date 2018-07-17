# Résumé des commandes Git

## Catégories

- **[Setup](#Setup)**
- **[Repository](#Repository)**
- **[Branch Management](#branch-Management)**
- **[Working](#Working)**
- **[Advanced](#advanced)**
- **[Done](#done)**
- **[Fix](#fix)**

## Setup

Définir les alias:

- status (st) : `git config --global alias.st status`
- checkout (co) : `git config --global alias.co checkout`
- commit (ci) : `git config --global alias.ci commit`
- see last commit (last) : `git config --global alias.last 'log -1 HEAD'`

Git config:

- `git config --list`

## Repository

- démarrer un répertoire git localement : `git init`
- définir l'origin d'un répertoire local nouvellement créé : `git remote add origin REPOSITORYURL` (le répertoire ne doit pas être déjà présent sur git)
- cloner un répertoire distant sur le local : `git clone REPOSITORYURL`

## Branch Management

- créer une branche BRANCHNAME: `git branch BRANCHNAME`
- changer la branche de travail pour que ça soit BRANCHNAME: `git checkout BRANCHNAME` ou avec un alias: `git co BRANCHNAME`
- créer une branche BRANCHNAME et y accéder de suite: `git checkout -b BRANCHNAME` ou avec un alias : `git co -b BRANCHNAME`
- récupérer les branches de l'origin: `git fetch`
- lister les branches locales: `git branch`
- lister les branches distantes (sur origin): `git branch -r`
- lister toutes les branches: `git branch -a`
- effacer une branche: `git branch -D BRANCHNAME`
- effacer une branche distante : `git push origin --delete BRANCHNAME`
- revenir ? la branche précédente: `git checkout -` ou avec un alias: `git co -`

## Working

- voir l'état des fichiers : `git status` ou avec un alias `git st`
- ajouter un nouveau fichier ? l'index git `git add FILENAME`
- ajouter tous les nouveaux fichiers ? l'index git `git add .`
- commiter un fichiers modifié : `git commit FILENAME`
- commiter tous les fichiers modifiés et spécifier un message de commit COMMITMESSAGE `git commit -am "COMMITMESSAGE"`
- afficher l'historique des commits locaux : `git log`
- afficher l'historique des commits distants : `git log origin/BRANCHNAME`
- afficher le dernier commit (alias) : `git last`
- envoyer les changements ? l'origin : `git push`
- récupérer les derniers changements de l'origin `git pull`

## Advanced

- récupérer un commit d'une autre branche par son hash COMMITHASH et en faire le dernier commit sur la branche courante : `git cherry-pick COMMITHASH`

- mettre de coté les changements actuels `git stash`
- appliquer les changements mis de coté `git stash apply`
- voir la liste des changements mis de coté `git stash list`
- supprimer le dernier stash `git stash drop`

## Merge and Rebase

- merger la branch BRANCHNAME dans la branche actuelle : `git merge BRANCHNAME`
- merger la branch BRANCHNAME dans la branche actuelle et forcer la création du commit de merge `git merge --no-ff BRANCHNAME`

- remplacer l'historique des commits de la branche par ceux de la branche BRANCHNAME : `git rebase BRANCHNAME`
- remplacer l'historique des commits de la branche par ceux de la branche BRANCHNAME de façon interactive : `git rebase -i BRANCHNAME`

- forcer le push (pas recommandé, mais ? utiliser si l'historique local et celui d'origin sont différents) : `git push --force`

## Fix

- créer un commit qui est l'exact inverse du précédent : `git revert COMMITHASH`
- supprimer le dernier commit (mets les changements dudit commit comme non commités): `git reset HEAD~1`
- changer le message du dernier commit: `git commit --amend`
- annuler les changements du fichier FILENAME: `git checkout -- FILENAME`
- annuler les changements de tous les fichiers: `git checkout -- .`
- supprimer les fichiers et dossiers non ajoutés ? l'index de git `git clean -df`
- trouver qui doit ?tre blamé pour la modif sur un fichier : `git blame FILENAME`