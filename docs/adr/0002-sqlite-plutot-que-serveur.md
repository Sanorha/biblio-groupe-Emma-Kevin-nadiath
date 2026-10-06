# ADR 0002 : sqlite-plutot-que-serveur.md 

- Statut : validé
- Date : 2026-10-06
- Décideurs : Sanorha, nadiatynov, emmadarmon3-boop

## Contexte
Besoin d'une base de donnée mais sans budget.

## Options envisagées
1. SQLite -> gratuit, simple de maintenance
2. serveur PostgreSQL -> payant et besoin d'un adminstrateur
3. fichier JSON -> gratuit mais problème d'accéssibilité et moins fiable en cas de crash pc (corrompu)


## Décision
On opte pour SQLite

## Conséquences
Facilité : 
- Déploiement et installation simple
- Maintenance et sauvegardes simple
- Fiabilité des données

Difficulté :
- Écritures simultanées limitées
- Gestion des accès et de la sécurité
