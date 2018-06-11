# Jouons avec les Branches

*durée: 10 / 15 min*

La branche actuelle est `master`. Pour créer une branch basée sur master, taper `git branch another-branch-from-master`

La branche est alors créée, mais on peut constater que git bash indique toujours `/c/Projects/git-training (master)`. 
Il faut atteindre cette nouvelle branche avec `git checkout branch-from-master`. 
Ou avec un alias: `git co branch-from-master`

A présent, revenir à la branche master. On va créer une branche 'another-branch-from-master' et y accéder en une seule commande : 
`git checkout -b another-branch-from-master` 
Ou avec un alias : `git co -b another-branch-from-master`

Faire un `git push` sur cette branche. Noter que la commande échoue. En effet, l'upstream n'est pas défini. Mais git bash fourni la ligne de commande correcte. La copier et la coller (shift + inser).
L'upstream est alors créé. 

- Lister les branches locales avec `git branch`
- Lister les branches distantes (sur origin): `git branch -r`
- lister toutes les branches: `git branch -a`

Retourner sur master. On va effacer la branche 'another-branch-from-master'. 

Avec la commande `git branch -D another-branch-from-master`, on effacae la branche localement.
Avec la commande `git push origin --delete another-branch-from-master` on efface la branche distante. 

Lister à nouveau les branches locales et distantes.

Faire un checkout de la branche `another-branch-from-master`.
Revenir à la branche précédente avec `git checkout - ` 
Ou avec un alias: `git co -`

Rejouer cette commande. 