## Bonnes pratiques 

En vrac, voici une liste non exhaustives de bonnes pratiques sur Git : 

- Naming des branches : 

Les branches doivent toujours avoir un nom permettrant de savoir ce qui est fait dans la branche. (pas de "temp", "branch1" etc..)
Les branches doivent correspondre à une tâche unique. 
De préférence, le nom de la branche doit démarrer par le numéro du ticket (sldiap-38-formation-git)
Avoir une cohérence sur la casse dans les noms de branche (de préférence : tout en minuscule, séparé par des -)

- Cleaning local et distant régulier

Supprimer régulièrement les branches déjà mergées ou obsolètes. Elles n'ont plus d'usage. Ce travail se fait localement et sur le server distant. 

- Cleaning des stashs régulier

Supprimer régulièrement les stashs trop vieux. S'ils n'ont pas été appliqués, il s'agit de code mort ou inutilisé, donc potentiellement source d'erreurs si appliqué par erreur. 

- Commiter régulierement. 

Pour chaque petite étape : un commit, avec un message clair. Cela permet de faciliter la recherche dans l'historique. 

- no-ff par défaut. 
Il est plus pratique d'avoir un commit spécifique à chaque merge pour pouvoir s'y retrouver plus facilement. Il est donc préférable de forcer le no-ff par défaut dans la config pour travailer sereinement. 

- historique de master/develop propre
L'historique de master et develop devrait dans l'idéal permettre de retrouver facilement les changements faits par une story. 
Il est vivement recommandé de squasher / merger (sans Fast Forward) pour le clarifier au maximum. 
De même, il ne devrait pas comporter de commits non associés à une story.

- pas de push force sur master/develop
Les origins de master et develop comportent l'historique de tout le projet. Il ne faut jamais les écraser ou les modifier. 
Il est vivement recommandé de bloquer cette possibilité directement dans les settings du repo distant. 

- useful commit messages
Même si l'on a tendance à moins les développer lorsque l'on travaille sur sa story, essayer autant que possible d'avoir des messages de commits qui permettent de s'y retrouver.
[XKCD](https://imgs.xkcd.com/comics/git_commit.png)

- ne pas commiter les fichiers de configuration
Sinon les mots de passes sont visibles à toute personne qui a accès au repo. 