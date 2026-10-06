# Biblio
Biblio est le gestionnaire de prêts de livres d'une association.

## Prérequis

Assurez-vous d'avoir les éléments suivants avant de commencer :

* **Système d'exploitation** : Windows, macOS ou Linux
* **Python** : `>= 3.12` (ou [Python 3.12.3](https://www.python.org/))
* **Base de données** : [SQLite 3](https://www.sqlite.org/)
* **Dépendances système** :
  * `git` (pour cloner et synchroniser le dépôt)
* **Environnement de dev (IDE)** : [VS Code](https://code.visualstudio.com/) ou [PyCharm](https://www.jetbrains.com/pycharm/)

## Installation et Configuration

 ## 1. Clonage du projet

Ouvrez le terminal de votre IDE (ou le terminal système) et lancez ces commandes pour vérifier que vos outils sont bien prêts :

```bash
# Vérifier Python (selon votre OS) :
python --version   # Windows / Linux / macOS
python3 --version  # Alternative sous Linux / macOS
py --version       # Alternative sous Windows

# Vérifier Git et SQLite :
git --version     #Vérifie que Git est disponible
sqlite3 --version # Vérifie l'installation de SQLite
```

Une fois la vérification et les mises à jour effectuées, lancez les commandes suivantes pour cloner le dépôt et vous placer dans le projet :

```bash
   git clone [https://github.com/Sanorhabiblio-groupe-Emma-Kevin-nadiath.git]
   (https://github.com/Sanorha/biblio-groupe-Emma-Kevin-nadiath.git)
   cd biblio-groupe-Emma-Kevin-nadiath  
```

## 2. Création de l'environnement virtuel Python

Une fois à l'intérieur du dossier du projet, créez l'environnement virtuel Python :

```bash
python -m venv venv
# Ou sous Linux/macOS si vous utilisez python3 :
# python3 -m venv venv
```

## 3. Activation de l'environnement virtuel 

Activez l'environnement selon votre système d'exploitation :

Windows (PowerShell):  

```powershell
.\venv\Scripts\Activate.ps1
```

Windows (Invite de commandes/CMD): 

```cmd
venv\Scripts\activate.bat
```

Linux/macOS: 

```bash
source venv/bin/activate
```


## Vérification

 Une fois activé, le préfixe (venv) doit apparaître au début de la ligne de votre terminal.


## 4. Installation des dépendances

Avec l'environnement virtuel activé, installez l'ensemble des bibliothèques nécessaires au projet :

```bash
pip install -r requirements.txt
```
Note : Le fichier requirements.txt contient la liste de toutes les bibliothèques Python nécessaires au projet.

## ⚠️ Rappel important
Pensez à vérifier que votre fichier `.gitignore` contient bien la ligne `venv/` afin d'éviter de pousser votre environnement virtuel local sur GitHub.


## Utilisation
**Initialisation :**
```bash
python biblio.py init
```
```text
output : 
Base initialisee : 6 livres, 3 membres.
```
<br>
<br>

**Voir les Livres :**
```bash
python biblio.py livres
```

```text
output:
[1] L'Etranger (Albert Camus) : disponible
[2] Dune (Frank Herbert) : emprunte
[3] Le Petit Prince (Antoine de Saint-Exupery) : disponible
[4] Fondation (Isaac Asimov) : disponible
[5] Les Miserables (Victor Hugo) : disponible
[6] Neuromancien (William Gibson) : disponible
```
<br>
<br>

**Recherche :**
```bash
python biblio.py chercher <texte>
```
exmple avec recherche dune : 
```text
python biblio.py chercher dune

output :
[2] Dune (Frank Herbert)
```
<br>
<br>

**Emprunter un livre :**
```bash
python biblio.py emprunter <id_livre> <id_membre>
```
Exemple d'emprunt livre 1 pour le membre 2:
```text
python biblio.py emprunter 1 2

output :
Emprunt enregistre : livre 1, membre 2.
```
<br>
<br>

**Rendre un livre :**
```bash
python biblio.py rendre <id_livre>
```
Exemple de rendu pour le livre 1:
```text
python biblio.py rendre 1

output :
Retour enregistre pour le livre 1.
```

<br>
<br>

**Voir les retards de rendu :**
```bash
python biblio.py retards
```
```text
output :
Dune, emprunte par Alice Martin : 254 jours de retard
```
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
