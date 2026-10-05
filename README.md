# Biblio
## Prérequis
## Installation
## Utilisation
## Tests
### Tests automatiques
```bash
python3 -m unittest

Résultat attendu : `OK`.

### Test manuel : un livre déjà prêté ne peut pas être réemprunté

```bash
python3 biblio.py init
python3 biblio.py emprunter 2 3   # refusé : livre 2 déjà emprunté
python3 biblio.py emprunter 1 3   # accepté : livre disponible
python3 biblio.py emprunter 1 2   # refusé : livre 1 vient d'être prêté
python3 biblio.py emprunter 4 3   # accepté : livre rendu, de nouveau disponible
```
## Structure du projet

```
biblio-groupe-Emma-Kevin-nadiath/
├── .github/        # configuration GitHub : modèles d'issues, de PR, tests automatiques (CI)
├── docs/           # documentation du projet 
├── exercices/      # consignes des TP 
├── tests/          # tests automatiques (lancés avec python3 -m unittest)
├── .gitignore      # fichiers que git doit ignorer (biblio.db, __pycache__)
├── biblio.py       # le programme : toutes les commandes et l'accès à la base
└── README.md       # ce fichier
```

`biblio.db` (la base SQLite) et `__pycache__/` (le cache Python) sont générés automatiquement. Ils ne sont pas versionnés.

### Où se trouve quoi ?

 Comprendre une commande (`emprunter`, `rendre`, `retards`…)  `biblio.py` : fonctions `borrow_book`, `return_book`, `late`… 
 Changer la durée de prêt  `biblio.py` : constante `LOAN_DAYS` 
Changer l'emplacement de la base  variable d'environnement `BIBLIO_DB` (défaut : `biblio.db`) 
 Lancer ou ajouter des tests  dossier `tests/` 
 Signaler un bug ou proposer une évolution  onglet **Issues** sur GitHub (modèles dans `.github/`) 
 Lire les consignes dossier `exercices/` 

## Contribuer
### 1. Ouvrir une issue

Avant de coder, ouvrez une issue dans l'onglet **Issues** avec le bon modèle :
 Biblio ne fait pas ce qu'il devrait faire  **Signaler un bug** 
 Biblio fonctionne, mais on voudrait autre chose ou plus  **Proposer une évolution** 
Vous ne savez pas si le comportement est normal  **Poser une question** 

Notez le numéro de l'issue (par ex. `#4`).

### 2. Créer une branche depuis `main`

```bash
git checkout main
git pull
git checkout -b fix/<n°issue>-mot-cle      # ex. fix/4-double-emprunt
```
Préfixes : `fix/` (bug), `feat/` (évolution), `docs/` (documentation).

### 3. Coder et tester

Partez toujours d'une base propre :

```bash
python3 biblio.py init
python3 -m unittest        # doit afficher OK
```

Testez aussi à la main la commande que vous avez modifiée.

### 4. Commit et push

```bash
git add <fichiers modifiés>
git commit -m "fix: refuse l'emprunt d'un livre deja prete"
git push -u origin HEAD
```

Message de commit : `type: ce que fait le changement` (`fix:`, `feat:`, `docs:`).

### 5. Ouvrir une Pull Request

- Base : `main` de **ce dépôt**.
- Remplissez le modèle : **Contexte** (avec `Closes #n`), **Changements**, **Impact**, **Comment tester**, **Checklist**.
- Choisissez au moins un **reviewer**.

### 6. Review et merge

- Le reviewer teste la PR, commente, puis choisit **Approve** ou **Request changes**.
- Si des changements sont demandés : corrigez **sur la même branche**, faites `git push`, répondez aux commentaires, puis cliquez sur **Resolve conversation**.
- Une fois la PR approuvée : **Merge pull request**, puis **Delete branch**. L'issue se ferme automatiquement grâce à `Closes #n`.

### 7. Règles

- **Une PR = un seul sujet.**
- **Aucun secret dans le code** 
- **Requêtes SQL paramétrées** avec `?`
- **On ne merge pas sa propre PR sans review.**

## Auteurs

- Kevin Harel
- Nadiath Karimou
- Emma Darmon
