# MergeOrRebase

Il s'agit d'un sujet très discuté vis-à-vis de Git. Il y a des défenseurs des 2 cotés. Certains défendent le merge, d'autres les rebases, certains mixent. Le rebase est régulièrement banni de certaines politiques d'entreprise.

Parmi les arguments : 

- le rebase change l'historique et oblige à un push --force, donc est potentiellement dangereux. 
- le merge va créer un point de commit pas forcément désiré, surtout dans l'historique de la branche de travail.
- le merge peut se comporter comme un rebase dans le cas d'un fast-forward (mais sans changement d'historique)

Plus de détails sur les pours et contre ici : https://www.atlassian.com/git/articles/git-team-workflows-merge-or-rebase

## Personnellement : 

J'ai une préférence pour l'usage du rebase dans le cadre du travail sur la branche. 
Le dev fait ses commits et rebase régulièrement sur develop pour être à jour. 

Il push force sur l'origin de sa branche si besoin, mais il sait (normalement) ce qu'il fait et dispose ainsi de l'historique de son travail.

Une fois qu'il a terminé sa feature, il rebase et squashe son travail en un unique commit qui va être reviewé. (l'historique du travail n'intéresse normalement pas le reviewer)
Cela assure aussi que le dev est reponsable de la mergeabilité de se branche. 

Le reviewer sera par contre responsable de rapatrier la branche dans le dévelop. On va donc préférer un merge de la branche dans develop, pour disposer d'un historique clair, et ne pas altérer l'historique.
