# Archify — traduction française

> **Cette branche est une traduction française dérivée du projet original [tt-a1i/archify](https://github.com/tt-a1i/archify).**
>
> Elle ne constitue pas un fork indépendant ni une nouvelle implémentation. Le code, l’architecture, les schémas, les tests et la licence proviennent du dépôt original. Les changements de cette branche visent principalement la localisation française de l’interface, de la documentation et des exemples.

## Dépôts

- Original : https://github.com/tt-a1i/archify
- Traduction française personnelle : https://github.com/LucMacPaquet/archify
- Branche de traduction : `lucpaquet/archify-francais`

## Archify

Archify transforme une description de système ou un dépôt de code en diagramme interactif, vérifiable et partageable. Il prend en charge les architectures, workflows, séquences, flux de données et cycles de vie.

L’artefact généré est un fichier HTML autonome avec SVG intégré, thèmes clair/sombre, navigation, export et validation déterministe.

## Statut de la traduction

- Traduction française en cours.
- L’interface française doit couvrir les libellés, la légende, les vues guidées, l’exploration sémantique, les exports, les messages d’erreur et l’accessibilité.
- Les noms de produits, API, protocoles, identifiants et commandes restent inchangés.
- Les diagrammes et contenus rédigés par l’utilisateur ne sont pas traduits automatiquement par Archify.

## Installation

```bash
npx skills add tt-a1i/archify --skill archify --agent opencode --global --copy --yes
```

Pour vérifier l’installation :

```bash
node archify/bin/archify.mjs doctor
```

## Utilisation rapide

```text
Utilise Archify pour représenter : Navigateur → API → cache Redis → PostgreSQL.
```

Pour une architecture issue d’un dépôt :

```text
Analyse ce dépôt, puis utilise Archify pour créer un diagramme d’architecture d’exécution de haut niveau. Montre les composants principaux, le parcours principal, les dépendances externes et les frontières de confiance.
```

## Validation et livraison

```bash
node archify/bin/archify.mjs validate architecture exemple.json --quality showcase --json
node archify/bin/archify.mjs deliver architecture exemple.json diagramme.html --quality showcase --json
node archify/bin/archify.mjs visual-check diagramme.html --json
```

## Provenance et licence

Cette branche conserve la licence et les mentions de tiers du projet original. Voir [[LICENSE]] et [[THIRD_PARTY_NOTICES.md]] dans ce dépôt.

Toute redistribution doit conserver les mentions de copyright et la licence MIT du projet original.

## Synchronisation avec l’original

Le dépôt original est configuré comme remote `origin`. Le dépôt personnel privé est configuré comme remote `personal`.

```bash
git fetch origin
git log --oneline origin/main..lucpaquet/archify-francais
git push personal lucpaquet/archify-francais
```

Avant toute mise à jour importante, comparer les changements de `origin/main` et préserver explicitement les traductions françaises.

## Avertissement

Cette traduction est maintenue par Luc Pâquet dans un dépôt personnel privé. Elle n’est pas une publication officielle de l’auteur d’Archify et ne doit pas être présentée comme telle.
