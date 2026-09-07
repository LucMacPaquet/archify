# Traduction française — Archify

Ce dépôt est une **branche de traduction française dérivée** du dépôt original :

```text
https://github.com/tt-a1i/archify
```

Le dépôt personnel privé qui héberge cette branche est :

```text
https://github.com/LucMacPaquet/archify
```

Branche : `lucpaquet/archify-francais`.

## Règles de contribution

1. Préserver le comportement fonctionnel de l’original.
2. Limiter les changements aux traductions, à la documentation française et aux tests de localisation, sauf décision documentée.
3. Conserver les identifiants techniques, noms de produits, API, protocoles et commandes.
4. Ajouter toute nouvelle chaîne Viewer au catalogue français.
5. Vérifier qu’aucune chaîne française ne retombe silencieusement en anglais lorsqu’une traduction est attendue.
6. Valider les diagrammes avec les mêmes contrôles que l’original.

## Stratégie i18n

La source i18n actuelle utilise des paires de messages dans `archify/renderers/shared/i18n.mjs`, avec les locales `en` et `zh-CN`. La branche française doit ajouter `fr` au catalogue source, puis compléter les tests associés.

La localisation doit couvrir au minimum :

- titre de page, descriptions et légende;
- types de nœuds et états;
- barre d’outils, thèmes et styles;
- export et cartes de partage;
- vues guidées, parcours et étapes;
- lentille sémantique, radar et passeport;
- messages d’erreur, d’état et d’accessibilité.

## Relation avec l’original

Les commits importés de `origin/main` demeurent la référence fonctionnelle. Les commits de traduction française doivent être facilement distinguables et ne doivent pas réécrire l’historique de l’original.

La licence MIT et les mentions de tiers du projet original restent applicables.
