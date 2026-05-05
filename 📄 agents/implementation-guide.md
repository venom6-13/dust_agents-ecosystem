# 🚀 Guide d'implémentation dans Dust

## Prérequis

- Un compte Dust actif
- Accès à la section **Build > Agents**
- Les 9 prompts disponibles dans le dossier `/agents`

---

## Ordre de création recommandé

```
Semaine 1 → 01 ProjectMaster + 02 Benchmark
Semaine 1 → 03 CTO Tech + 04 ProductCraft
Semaine 2 → 05 FinanceMaster + 06 MarketingMaster
Semaine 2 → 07 RoadmapManager + 08 NotionMaster
Semaine 3 → 09 StrategyMaster CEO (en dernier)
```

> ⚠️ Créer StrategyMaster CEO en dernier. Il doit être configuré
> avec une vraie connaissance de ce que les autres produisent.

---

## Configuration de chaque agent

### Dans Dust : Build > New Agent

| Paramètre | Valeur recommandée |
|-----------|-------------------|
| Nom | Voir colonne "Nom @mention" ci-dessous |
| Modèle | Claude Sonnet |
| Instructions | Coller le prompt complet depuis `/agents` |
| Web Search | Voir tableau ci-dessous |
| Visibilité | Workspace (accessible à toi uniquement) |

### Noms @mention suggérés

| Agent | Nom @mention |
|-------|-------------|
| ProjectMaster | @project |
| Benchmark | @benchmark |
| CTO Tech | @cto |
| ProductCraft | @product |
| FinanceMaster | @finance |
| MarketingMaster | @marketing |
| RoadmapManager | @roadmap |
| NotionMaster | @notion |
| StrategyMaster CEO | @ceo |

---

## Tester chaque agent

Après création, teste avec ce scénario universel :

> *"Je veux créer une application de suivi de budget
> personnel pour les étudiants en école de commerce."*

### Ce que tu vérifies

- ✅ Respecte-t-il son format de réponse ?
- ✅ Reste-t-il dans son périmètre ?
- ✅ Oriente-t-il vers les bons agents quand nécessaire ?
- ✅ Pose-t-il des questions avant de répondre ?
  (ProjectMaster, RoadmapManager, NotionMaster)
- ✅ Recherche-t-il sur internet ?
  (Benchmark, MarketingMaster)

---

## Tester les frontières

Teste intentionnellement les limites de chaque agent :

```
@project   → "Quel outil no-code recommandes-tu ?"
             ✅ Attendu : orientation vers @cto

@benchmark → "Combien ça va me coûter ?"
             ✅ Attendu : orientation vers @finance

@cto       → "Qui sont mes concurrents ?"
             ✅ Attendu : orientation vers @benchmark

@finance   → "Comment je planifie mes sprints ?"
             ✅ Attendu : orientation vers @roadmap

@roadmap   → "Est-ce que mon projet est viable ?"
             ✅ Attendu : orientation vers @ceo
```

---

## Flux de travail complet

```
1. @project  → Cadre le projet
2. @benchmark → Coller output @project + question marché
3. @cto      → Coller outputs précédents + question tech
4. @product  → Coller outputs précédents + question UX/MVP
5. @finance  → Coller tous les outputs + budget disponible
6. @marketing → Coller outputs + objectifs marketing
7. @roadmap  → Coller tous les outputs + disponibilité/deadline
8. @notion   → Coller outputs à matérialiser
9. @ceo      → Coller TOUS les outputs pour la synthèse finale
```

---

*Dernière mise à jour : Mars 2026*
