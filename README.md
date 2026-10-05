# Biblio
## Prérequis
## Installation
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

**Rendre un livre :**
```bash
python biblio.py retards
```
```text
output :
Dune, emprunte par Alice Martin : 254 jours de retard
```
## Tests
## Structure du projet
## Contribuer
## Auteurs
