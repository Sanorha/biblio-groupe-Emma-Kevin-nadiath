# ADR 0003 : Requêtes SQL paramétrées obligatoires
- Statut : proposé 
- Date : 2026-10-06
- Décideurs : @Sanorha, @nadiatynov, @emmadarmon3-boop

## Contexte
La concaténation directe de la saisie utilisateur (WHERE title LIKE '%" + text + "%') crée une faille critique d'injection SQL et fait planter la recherche sur des mots avec apostrophe (ex: L'Étranger). La sécurisation de l'accès aux données est donc obligatoire.

## Options envisagées

1. Option A: Nettoyage manuel du texte saisi
Pour : Garde une construction de requête dynamique par concaténation.
Contre : Solution très faillible (risque d'oubli), complexe à maintenir et casse les recherches contenant des apostrophes légitimes.

2. Option B: Paramètres (?) Requêtes paramétrées
 Pour : Sécurise complètement les requêtes contre les injections SQL et gère automatiquement l'échappement des caractères spéciaux.
 Contre : Impose une syntaxe plus stricte (passage des arguments sous forme de tuple) et ne permet pas de dynamiser les noms de tables ou de colonnes.

## Décision
 Nous choisissons d'utiliser systématiquement le paramètre ? pour toutes les requêtes SQL comportant des variables utilisateur.
 
## Conséquences
Ce qui devient plus facile : La gestion de la sécurité de l'application et le traitement sans erreur des saisies contenant des apostrophes ou des caractères spéciaux.   
Ce qui devient plus difficile : L'écriture de requêtes dont la structure même (noms de tables ou de colonnes) doit varier dynamiquement à l'exécution.  
