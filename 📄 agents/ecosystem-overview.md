# 🗺️ Vue d'ensemble de l'écosystème

## Architecture complète

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
 08. 📒 NotionMaster     → Frameworks Notion et suivi
      ↓
 09. 🧠 StrategyMaster   → Synthèse, arbitrage, vision macro
```

---

## Flux de données entre agents

| Agent émetteur | Données transmises | Agent récepteur |
|---------------|-------------------|-----------------|
| ProjectMaster | Brief projet, objectifs SMART, périmètre | Tous |
| Benchmark | Cartographie concurrents, gaps marché, données | CTO, ProductCraft, FinanceMaster |
| CTO Tech | Stack recommandée, coûts outils, complexité | FinanceMaster, ProductCraft, RoadmapManager |
| ProductCraft | User Stories, wireframes, complexité écrans | FinanceMaster, RoadmapManager, StrategyMaster |
| FinanceMaster | Budget validé, runway, contraintes financières | RoadmapManager, StrategyMaster |
| MarketingMaster | Plan marketing, assets nécessaires, KPIs | RoadmapManager, StrategyMaster |
| RoadmapManager | Planning, milestones, chemin critique | NotionMaster, StrategyMaster |
| NotionMaster | Workspace structuré | Utilisateur |
| StrategyMaster | Décision finale, arbitrages, vision | Utilisateur |

---

## Agents transversaux

Certains agents peuvent être appelés **à tout moment** du flux,
indépendamment de leur position :

- **NotionMaster** : matérialise l'output de n'importe quel agent
- **StrategyMaster CEO** : peut être sollicité pour un arbitrage
  à n'importe quelle étape

---

## Web Search par agent

| Agent | Web Search | Raison |
|-------|------------|--------|
| ProjectMaster | ❌ | Travail sur le contexte fourni |
| Benchmark | ✅ Obligatoire | Données marché fraîches et sourcées |
| CTO Tech | ✅ Recommandé | Tarifs outils, nouvelles technos |
| ProductCraft | ❌ | Travail sur le brief reçu |
| FinanceMaster | ❌ | Benchmarks intégrés au prompt |
| MarketingMaster | ✅ Obligatoire | Tendances, algorithmes, benchmarks |
| RoadmapManager | ❌ | Travail sur les inputs reçus |
| NotionMaster | ❌ | Expertise Notion intégrée |
| StrategyMaster CEO | ✅ Recommandé | Tendances macro, veille sectorielle |

---

*Dernière mise à jour : Mars 2026*
