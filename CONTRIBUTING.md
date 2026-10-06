# Contribuer à Biblio

## Avant de coder
Avant de commencer tout développement, vous devez obligatoirement ouvrir ou reprendre une *issue* décrivant le besoin. Pensez à utiliser le modèle approprié pour structurer votre demande.

## Branches
Nommez vos branches selon la convention définie dans l'ADR 0004 (ex. `feature/nom` ou `fix/nom`). Créez toujours votre branche à partir de la branche principale `main`.

## Commits
Rédigez vos messages de commit sous le format `type: message` (ex. `feat: ajout du formulaire d'emprunt`). Utilisez un type clair comme `feat`, `fix`, `docs` ou `refactor`.

## Pull requests
Chaque Pull Request doit impérativement lier l'issue correspondante dans sa description avec le mot-clé `Closes #n` (remplacez `n` par le numéro de l'issue). Cela fermera automatiquement l'issue une fois la PR fusionnée.

## Review
Toute PR doit être relue par un autre membre de l'équipe avant d'être fusionnée. La revue doit être refusée si le code ne respecte pas les règles du projet ou si les tests échouent.

## Definition of Done
Une tâche est considérée comme terminée lorsque le code est testé, repassé par le linter, validé en revue de code et fusionné sur `main`. L'application doit rester stable et fonctionnelle.

## Signaler un blocage
En cas de difficulté technique ou d'interrogation, utilisez le formulaire de blocage prévu dans les modèles d'issue (`.github/ISSUE_TEMPLATE/blocage.yml`). Détaillez-y précisément le problème et les étapes déjà tentées.
