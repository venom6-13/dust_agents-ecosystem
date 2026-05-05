# 🤖 AI Agent Ecosystem — Dust

> Un écosystème de 9 agents IA spécialisés pour accompagner la création et le pilotage de projets entrepreneuriaux, de l'idée au lancement.

---

## 🎯 Vision du projet

La plupart des outils IA sont généralistes. Ce projet adopte l'approche inverse : **9 agents ultra-spécialisés**, chacun expert dans son domaine, qui travaillent en chaîne pour couvrir l'intégralité du cycle de vie d'un projet.

Chaque agent a :
- Un **rôle unique et délimité** (pas de chevauchement)
- Un **processus structuré** en étapes obligatoires
- Un **format de réponse standardisé**
- Une **conscience de sa place** dans l'écosystème

---

## 🗺️ Architecture de l'écosystème

```
NOUVEAU PROJET
      ↓
 01. 🎯 ProjectMaster    → Cadrage et structuration
      ↓
 02. 🔍 Benchmark        → Analyse marché et concurrence
      ↓
 03. 💻 CTO Tech         → Stack, outils, architecture
      ↓
 04. 🎨 ProductCraft     → UX, UI, wireframes, MVP
      ↓
 05. 💰 FinanceMaster    → Budget, ROI, viabilité
      ↓
 06. 📣 MarketingMaster  → Acquisition, branding, communication
      ↓
 07. 📅 RoadmapManager   → Planning opérationnel
      ↓
 08. 📒 NotionMaster     → Frameworks Notion et suivi projet
      ↓
 09. 🧠 StrategyMaster   → Synthèse, arbitrage, vision macro
```

---

## 🤖 Les 9 agents

| # | Agent | Rôle | Web Search |
|---|-------|------|------------|
| 01 | 🎯 ProjectMaster | Cadrage, frameworks, structuration de projet | ❌ |
| 02 | 🔍 Benchmark | Analyse concurrentielle, tendances marché | ✅ |
| 03 | 💻 CTO Tech | Stack technique, outils, mini-cours tech | ✅ |
| 04 | 🎨 ProductCraft | UX/UI, wireframes, user stories, MVP | ❌ |
| 05 | 💰 FinanceMaster | Budget, ROI, scénarios financiers, viabilité | ❌ |
| 06 | 📣 MarketingMaster | Go-to-market, contenu, branding, copywriting | ✅ |
| 07 | 📅 RoadmapManager | Planning, sprints, MoSCoW, milestones | ❌ |
| 08 | 📒 NotionMaster | Workspaces Notion sur mesure, frameworks de suivi | ❌ |
| 09 | 🧠 StrategyMaster CEO | Synthèse, arbitrages stratégiques, vision | ✅ |

---

## 🔄 Flux de travail

### Mode manuel (recommandé pour débuter)
Chaque agent est appelé séquentiellement. L'output de l'un
devient l'input du suivant.

```
@projectmaster → brief projet
      ↓ (colle l'output)
@benchmark → analyse marché
      ↓ (colle les outputs)
@cto → recommandations techniques
      ...
      ↓ (colle tous les outputs)
@strategyceo → synthèse et décision
```

### Mode orchestration (avancé)
StrategyMaster CEO peut appeler automatiquement
ProjectMaster, Benchmark et FinanceMaster
avant de produire sa synthèse.

---

## 🧪 Protocole de test

Trois niveaux de test recommandés :

1. **Test unitaire** — Chaque agent testé seul avec le même scénario
2. **Test de frontières** — Vérification qu'aucun agent ne sort de son périmètre
3. **Test de flux complet** — Chaîne complète sur un cas réel

> Voir [`docs/testing-protocol.md`](docs/testing-protocol.md) pour le détail complet.

---

## 🚀 Implémentation dans Dust

1. Crée chaque agent dans **Build > New Agent**
2. Colle le prompt depuis le dossier `/agents`
3. Active le **Web Search** pour les agents marqués ✅
4. Teste chaque agent individuellement avant de les chaîner
5. Crée StrategyMaster CEO en dernier

> Voir [`docs/implementation-guide.md`](docs/implementation-guide.md) pour le guide complet.

---

## 📁 Structure du repo

```
📁 agent-ecosystem/
├── 📄 README.md
├── 📁 agents/
│   ├── 📄 01-project-master.md
│   ├── 📄 02-benchmark.md
│   ├── 📄 03-cto-tech.md
│   ├── 📄 04-product-craft.md
│   ├── 📄 05-finance-master.md
│   ├── 📄 06-marketing-master.md
│   ├── 📄 07-roadmap-manager.md
│   ├── 📄 08-notion-master.md
│   └── 📄 09-strategy-master-ceo.md
├── 📁 docs/
│   ├── 📄 ecosystem-overview.md
│   ├── 📄 implementation-guide.md
│   └── 📄 testing-protocol.md
└── 📁 examples/
    └── 📄 use-case-marketplace.md
```

---

## 🛠️ Stack

- **Plateforme IA** : [Dust](https://dust.tt)
- **Modèle** : Claude Sonnet (Anthropic)
- **Prompt Engineering** : XML structuring, chain-of-thought,
  context engineering, progressive disclosure

---

## 👤 Auteur

**Alec DIAMIDIA**
Étudiant à Eugenia School — Bordeaux
Passionné par l'IA appliquée à l'entrepreneuriat

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/TON-PROFIL)

---

## 📄 Licence

MIT License — Libre d'utilisation avec mention de l'auteur.

---

*Projet construit en mars 2026 — En évolution continue*
