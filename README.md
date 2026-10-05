# Biblio
Biblio est le gestionnaire de prêts de livres pour une association.

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
## Tests
## Structure du projet
## Contribuer
## Auteurs
