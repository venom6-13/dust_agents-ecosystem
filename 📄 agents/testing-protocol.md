# 🧪 Protocole de test — 3 niveaux

## Niveau 1 — Test unitaire

**Scénario universel :**
> *"Je veux créer une application de suivi de budget
> personnel pour les étudiants en école de commerce."*

Tester chaque agent individuellement avec cette phrase.
Noter sur 25 points :

| Critère | Note /5 |
|---------|---------|
| Respect du périmètre | /5 |
| Qualité du format de réponse | /5 |
| Pertinence des recommandations | /5 |
| Gestion des inputs manquants | /5 |
| Actionabilité de l'output | /5 |
| **TOTAL** | **/25** |

**Interprétation :**
- < 15 → Prompt à ajuster
- 15-20 → Bon agent, optimisations mineures
- > 20 → Agent production-ready ✅

---

## Niveau 2 — Test de frontières

Vérifier qu'aucun agent ne sort de son périmètre.

| Question posée à | Question | Réponse attendue |
|-----------------|----------|-----------------|
| @project | "Quel outil no-code ?" | Oriente vers @cto |
| @benchmark | "Combien ça coûte ?" | Oriente vers @finance |
| @cto | "Qui sont mes concurrents ?" | Oriente vers @benchmark |
| @finance | "Comment planifier mes sprints ?" | Oriente vers @roadmap |
| @roadmap | "Est-ce stratégiquement viable ?" | Oriente vers @ceo |
| @notion | "Quelle stack choisir ?" | Oriente vers @cto |

---

## Niveau 3 — Test de flux complet

**Scénario stress test :**
> *"Je veux lancer en 3 mois une plateforme qui met
> en relation des coachs sportifs indépendants avec
> des particuliers. J'ai 8 000€ de budget, je suis seul,
> et je peux y consacrer 15h par semaine.
> Je n'ai pas de compétences techniques."*

Lancer les 9 agents en séquence en passant les outputs
d'un agent à l'autre.

**Critères d'évaluation du flux complet :**

| Critère | Question |
|---------|----------|
| Cohérence | Les agents se contredisent-ils ? |
| Complémentarité | Chaque agent apporte-t-il quelque chose de nouveau ? |
| Progression | L'output de chaque agent enrichit-il le suivant ? |
| Angles morts | Le CEO identifie-t-il ce que les autres ont raté ? |
| Actionabilité | Sort-on avec une décision claire et une prochaine étape ? |

---

## Résultats de test

| Agent | Score unitaire | Frontières OK | Notes |
|-------|---------------|---------------|-------|
| ProjectMaster | /25 | ✅/❌ | |
| Benchmark | /25 | ✅/❌ | |
| CTO Tech | /25 | ✅/❌ | |
| ProductCraft | /25 | ✅/❌ | |
| FinanceMaster | /25 | ✅/❌ | |
| MarketingMaster | /25 | ✅/❌ | |
| RoadmapManager | /25 | ✅/❌ | |
| NotionMaster | /25 | ✅/❌ | |
| StrategyMaster CEO | /25 | ✅/❌ | |

---

*Dernière mise à jour : Mars 2026*
