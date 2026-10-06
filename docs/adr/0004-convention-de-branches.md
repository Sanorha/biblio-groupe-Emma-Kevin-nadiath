# ADR 0004 : convention de nommage des branches

- Statut : proposé
- Date : 2026-10-06
- Décideurs : @emmadarmon3-boop

## Contexte
<!-- La situation et la contrainte qui imposent de choisir. -->
Plusieurs personnes contribuent à Biblio en même temps : les membres du groupe, des bénévoles de l'association et des nouveaux venus comme Sam. Chacun crée ses propres branches, et rien n'impose comment les nommer.

En lisant la liste des branches (`git branch -a`), on ne sait donc pas ce que fait chaque branche ni à quelle issue elle correspond. Par exemple, `sam/export-csv` dit qui travaille, mais pas s'il s'agit d'une correction ou d'une nouveauté, ni quelle issue elle traite. Les relecteurs perdent du temps et le suivi du travail devient difficile.

Il faut donc choisir une règle commune de nommage.

## Options envisagées
 **Nom libre** (ex. `test`, `ma-branche`, `correction2`)
   - Pour : aucune règle à apprendre, rapide pour un débutant.
   - Contre : impossible de savoir ce que fait la branche ou de retrouver l'issue liée ; risque de noms en double ou incompréhensibles.

2. **`prenom/sujet`** (ex. `sam/export-csv`)
   - Pour : on sait qui travaille sur la branche.
   - Contre : pas de type de changement ni de lien vers l'issue ; l'auteur est déjà visible dans l'historique git.

3. **`type/n°issue-mots-cles`** (ex. `fix/4-double-emprunt`, `docs/10-readme`)
   - Pour : le type est visible (`fix` = correction, `feat` = évolution, `docs` = documentation), le numéro mène directement à l'issue, les mots-clés résument le sujet ; cohérent avec les messages de commit (`fix: ...`).
   - Contre : une règle à apprendre et à respecter ; il faut créer l'issue avant la branche.


## Décision
<!-- L'option retenue, formulée clairement. -->
Toute branche est nommée `type/n°issue-mots-cles`, avec `type` parmi `fix`, `feat` ou `docs`.


## Conséquences
<!-- Ce que la décision rend plus facile, et ce qu'elle rend plus difficile. -->
Ce qui devient plus facile :
- retrouver l'issue liée à une branche grâce à son numéro ;
- comprendre le travail en cours en lisant seulement `git branch -a` ;
- savoir avant d'ouvrir une PR s'il s'agit d'une correction, d'une évolution ou de documentation.

Ce qui devient plus difficile :
- il faut toujours ouvrir une issue avant de coder, même pour un petit changement ;
- les nouveaux contributeurs doivent apprendre la règle (à expliquer dans le README, section Contribuer) ;
- rien ne vérifie automatiquement le nom : une branche mal nommée passe si le relecteur ne la remarque pas. Piste : un contrôle automatique dans `.github/workflows/` qui refuse une PR dont la branche ne respecte pas le format.
