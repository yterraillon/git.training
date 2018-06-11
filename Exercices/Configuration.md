# Configuration de Git

*durée: 5 min*

Avant de démarrer quoi que ce soit, quelques réglages à faire pour travailler plus confortablement. 
Depuis Git Bash, taper `git config --list` pour voir la liste des configurations existantes dans git. 

Définition de quelques alias pour travailler plus facilement : 

- status (st) : `git config --global alias.st status`
- checkout (co) : `git config --global alias.co checkout`
- commit (ci) : `git config --global alias.ci commit`
- see last commit (last) : `git config --global alias.last 'log -1 HEAD'`

Les alias ne sont qu'un raccourci, il est important de ne pas oublier ce qu'ils signifient à la base :)

Refaire un `git config --list` et noter que les alias sont à présent visibles dans les configs. 

### Pour en savoir plus : 

Exemple de configuration plus poussée sur git : (paragraphe git-config(1))
https://nuclearsquid.com/writings/git-tricks-tips-workflows/