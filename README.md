![Aperçu du produit Archify](docs/assets/archify-readme-hero.png)

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

**Aucun dépôt n’est requis :** décrivez simplement le système dans une conversation avec votre agent.

L’artefact généré est un fichier HTML autonome avec SVG intégré, thèmes clair/sombre, navigation, export et validation déterministe.

- **Présenter et explorer** — cinq types de diagrammes, quatre styles visuels, thèmes clair/sombre, marques intégrées et animation finie;
- **Comparer des changements d’architecture** — comparaison de deux instantanés validés avant / delta / après;
- **Garder chaque interaction fondée sur les faits** — recherche, parcours de relations, routes exactes et vues guidées sans inventer de topologie;
- **Intégration multi-agents** — Cursor, Claude Code, Codex CLI et OpenCode utilisent la même compétence Archify;
- **Déploiement déterministe** — les extrémités automatiques partagées se déploient de manière déterministe au lieu d’empiler les flèches;
- **Partager un seul fichier** — JSON typé et contrôles déterministes produisant du HTML autonome ainsi que des exports PNG, SVG, WebM et carte de partage 1200×630.

![Licence](https://img.shields.io/badge/licence-MIT-22c55e?style=flat-square)
![Compétence agent](https://img.shields.io/badge/Agent-Skill-7C3AED?style=flat-square)
![Version de développement](https://img.shields.io/badge/version-2.17.0--dev.1-0891b2?style=flat-square)

**Version de développement actuelle :** `v2.17.0-dev.1`. Voir le [journal des changements](CHANGELOG.md#unreleased).

## Archify en action

Les éléments suivants sont des artefacts Archify générés, et non des maquettes :

Consultez la [galerie interactive](https://tt-a1i.github.io/archify/gallery.html) pour les scénarios vérifiés.

Pour une installation explicite dans Cursor :

```bash
npx -y skills add tt-a1i/archify --skill archify --agent cursor --global --copy --yes
```

![Preuve animée Archify](docs/assets/archify-live-proof.gif)

| Récit guidé | Parcours | Lentille sémantique |
|---|---|---|
| [![Workflow guidé](docs/assets/archify-demo-story.png)](https://tt-a1i.github.io/archify/gallery/artifacts/agent-tool-call.workflow.html?theme=dark&present=1&play=1#view=happy-path) | [![Parcours après défaut de cache](docs/assets/archify-demo-route.png)](https://tt-a1i.github.io/archify/gallery/artifacts/cache-miss.sequence.html?theme=dark&present=1#route=web~db) | [![Lentille architecture](docs/assets/archify-demo-lens.png)](https://tt-a1i.github.io/archify/gallery/artifacts/production-deployment.architecture.html?theme=dark&present=1#lens=backend~database) |

### Un dépôt réel cartographié depuis ses sources

![Carte de partage de l’architecture MCO](docs/assets/mco-runtime-share-card.png)

Archify a analysé [`mco-org/mco`](https://github.com/mco-org/mco) à la révision `9f1a1cf`. Voir le [diagramme](https://tt-a1i.github.io/archify/cases/mco-runtime.architecture.html?theme=dark&present=1#view=dispatch-path) ou sa [source typée](docs/cases/mco-runtime.architecture.json).

La [carte de partage de portée (Reach Share Card)](docs/assets/mco-runtime-reach-share-card.png) conserve le diagramme complet et la portée relationnelle explicitement parcourue.

## Aperçu

| Thème sombre | Thème clair |
|---|---|
| ![Thème sombre](docs/assets/archify-dark.png) | ![Thème clair](docs/assets/archify-light.png) |

![Menu d’exportation](docs/assets/archify-menu.png)

Les diagrammes d’exemple couvrent les workflows, les séquences, les flux de données et les cycles de vie :

![Exemple de workflow](docs/assets/archify-workflow.png)
![Exemple de séquence](docs/assets/archify-sequence.png)
![Exemple de flux de données](docs/assets/archify-dataflow.png)
![Exemple de cycle de vie](docs/assets/archify-lifecycle.png)

## Démarrage rapide

### 1. Installation

```bash
npx skills add tt-a1i/archify --skill archify --agent opencode --global --copy --yes
node archify/bin/archify.mjs doctor
```

Pour essayer sans installer :

```bash
npx skills use tt-a1i/archify@archify --agent codex
```

| Surface | Installation | Capacité |
|---|---|---|
| **Raven** | Archive ZIP manuelle dans `~/.raven/workspace/skills`, qui produit `~/.raven/workspace/skills/archify` | Rendu et validation complets |
| **Claude Code** | `~/.claude/skills/` ou `.claude/skills/` | Rendu et validation complets |
| **Codex CLI** | `~/.agents/skills/` ou `.agents/skills/` | Rendu et validation complets |
| **OpenCode** | `~/.config/opencode/skills/`, `.opencode/skills/` ou `.agents/skills/` | Rendu et validation complets |
| **DeepSeek Harness** | `dsh plugin --profile web add @tt-a1i/archify-dsh@0.1.0` | Intégration communautaire facultative; Node `^22.19.0 \|\| >=24.0.0` |

### 2. Commencer avec une description

```text
Utilise Archify pour représenter : Navigateur → API → cache Redis → PostgreSQL.
```

Pour une architecture issue d’un dépôt :

```text
Analyse ce dépôt, puis utilise Archify pour créer un diagramme d’architecture d’exécution de haut niveau. Montre les composants principaux, le parcours principal, les dépendances externes et les frontières de confiance.
```

### 3. Valider et livrer

```bash
node archify/bin/archify.mjs validate architecture exemple.json --quality showcase --json
node archify/bin/archify.mjs deliver architecture exemple.json diagramme.html --quality showcase --json
node archify/bin/archify.mjs visual-check diagramme.html --json
```

### Prévisualisation locale facultative

```bash
node archify/bin/archify.mjs preview workflow exemples/agent-tool-call.workflow.json /tmp/workflow.html --quality showcase --no-open
```

La prévisualisation est une boucle locale réservée au bureau, sur `127.0.0.1`. Elle conserve le dernier artefact vérifié à l’écran et s’arrête avec `Ctrl-C`; elle ne fait jamais partie de l’artefact généré ni des exports.

## Exploration et partage

La **Carte de partage (Share Card)** facultative produit une image PNG 1200×630. La **Carte de partage de portée (Reach Share Card)** représente uniquement la portée relationnelle explicitement écrite dans le diagramme; elle ne prétend pas montrer un impact d’exécution, une causalité ou une panne.

![Carte de partage de portée](docs/assets/mco-runtime-reach-share-card.png)

## Référence et périmètre

- [Référence des schémas](archify/schemas/README.md) · [Skill](archify/SKILL.md) · [Exemples](archify/examples/) · [Guide de rédaction](docs/authoring-cookbook.md)
- [Journal des changements](CHANGELOG.md)
- [Feuille de route](ROADMAP.md)

Les noms de produits, API, protocoles, identifiants et commandes restent inchangés. Les diagrammes et contenus rédigés par l’utilisateur ne sont pas traduits automatiquement par Archify.

## Provenance et licence

Cette branche conserve la licence et les mentions de tiers du projet original. Voir [LICENSE](LICENSE) et [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

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

## Contribution

Les problèmes, demandes de fusion et diagrammes réels sont bienvenus. Consultez le [guide de contribution](CONTRIBUTING.md) et fournissez une reproduction déterministe ainsi que les preuves nécessaires.

Les propositions de diagrammes peuvent être soumises via le [formulaire de présentation communautaire](https://github.com/tt-a1i/archify/issues/new?template=showcase.yml).

## Historique des étoiles

<p align="center"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/tt-a1i/archify/star-history/assets/star-history-dark.svg" /><img alt="Historique des étoiles" src="https://raw.githubusercontent.com/tt-a1i/archify/star-history/assets/star-history-light.svg" /></picture></p>
