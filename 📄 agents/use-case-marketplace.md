# 🏋️ Cas d'usage — CoachConnect

> Flux complet de l'écosystème appliqué à la création
> d'une marketplace de coachs sportifs indépendants.
>
> **Contexte :** Solo founder, 8 000€ de budget,
> 15h/semaine disponibles, zéro compétence technique.

---

## 📋 Résumé du projet

| Paramètre | Valeur |
|-----------|--------|
| Projet | Marketplace coachs sportifs ↔ particuliers |
| Budget | 8 000€ |
| Disponibilité | 15h/semaine |
| Délai visé | 3 mois |
| Niveau technique | Débutant |
| Modèle | Commission sur chaque transaction |

---

## 🎯 Agent 01 — ProjectMaster

### Input
> "Je veux lancer une plateforme qui met en relation
> des coachs sportifs indépendants avec des particuliers.
> J'ai 8 000€ de budget, je suis seul, 15h/semaine,
> sans compétences techniques."

### Output

**Problème identifié :**
Les particuliers peinent à trouver un coach sportif
de confiance, disponible et adapté à leur niveau.
Les coachs indépendants perdent 30% de leur temps
à chercher des clients sans outil dédié.

**Objectif SMART :**
Permettre à 50 particuliers de réserver leur première
session avec un coach certifié en moins de 5 minutes,
d'ici le 30 juin 2026.

**Périmètre MVP :**
- ✅ IN : Profils coachs, recherche/filtres, réservation, paiement
- ❌ OUT : Blog, app native iOS/Android, programme d'entraînement

**Méthodologie recommandée :** Lean Startup
- Validation avant développement
- MVP testable en 8 semaines
- Itérations basées sur les retours utilisateurs

**Prochaine action :**
Réaliser 5 entretiens avec des particuliers cette semaine.
Question clé : "Comment avez-vous trouvé votre dernier
coach sportif ? Qu'est-ce qui a failli vous faire abandonner ?"

---

## 🔍 Agent 02 — Benchmark

### Input
> Brief ProjectMaster + "Analyse le marché des marketplaces
> de coachs sportifs en France"

### Output

**Contexte de marché :**
Le marché du coaching sportif en France représente
1,2Md€ en 2025 (+18%/an). 73% des coachs sont
indépendants et sans plateforme dédiée (Sport&Co, 2025).

**Cartographie des acteurs :**
| Acteur | Positionnement | Points forts | Points faibles |
|--------|---------------|--------------|----------------|
| Superprof | Généraliste (sport + cours) | Volume, notoriété | Pas de réservation intégrée |
| Urban Sports Club | Abonnement multi-activités | UX, réseau | Pas de coach perso |
| Coachd | Coaching en ligne | Digital-native | Pas de proximité géo |
| Coach Avenue | Premium B2B | Qualité | Trop cher pour particuliers |

**Gap identifié :**
Aucun acteur ne combine : coach certifié + proximité
géographique + réservation + paiement intégré
+ accessible < 50€/session.

**Opportunité de différenciation :**
Se positionner sur la **confiance et la certification** :
chaque coach vérifié, chaque avis authentifié.

**Erreurs à éviter :**
Superprof a perdu la confiance des utilisateurs
sur la qualité des profils non vérifiés.
Ne jamais laisser un coach non certifié sur la plateforme.

---

## 💻 Agent 03 — CTO Tech

### Input
> Outputs ProjectMaster + Benchmark + "Quelle stack
> pour une marketplace avec mon profil débutant ?"

### Output

**Option A — Rapide & Accessible (recommandée)**
| Outil | Rôle | Coût/mois |
|-------|------|-----------|
| Bubble | Frontend + Backend + DB | 29€ |
| Stripe | Paiements + commission | 0€ + 1.4% |
| Postmark | Emails transactionnels | 0€ (< 100/mois) |
| Crisp | Chat support | 0€ |
| **TOTAL** | | **~30€/mois** |

**Option B — Robuste (si compétences acquises)**
Next.js + Supabase + Stripe + Vercel (~45€/mois)

**Architecture Option A :**
```
Utilisateur → Bubble (profil + recherche + réservation)
            → Stripe (paiement sécurisé)
            → Postmark (confirmation email)
            → Bubble (dashboard vendeur/acheteur)
```

**Points de vigilance :**
- Créer le compte Stripe dès jour 1 (validation 48-72h)
- RGPD : mentions légales + CGU obligatoires avant lancement
- Scalabilité Bubble : suffisant jusqu'à 10k users actifs

---

## 🎨 Agent 04 — ProductCraft

### Input
> Tous les outputs précédents + "Conçois le MVP"

### Output

**Persona :**
Lucas, 28 ans, salarié, veut reprendre le sport
mais manque de régularité seul. Cherche un coach
de confiance, proche de chez lui, < 50€/session.

**Architecture MVP — 5 écrans :**
```
Onboarding → Recherche → Profil Coach → Réservation → Dashboard
```

**Wireframe — Écran Recherche :**
```
┌─────────────────────────────┐
│ 🔍 [Recherche par ville]    │
│ [Sport ▼] [Prix ▼] [Dispo ▼]│
├─────────────────────────────┤
│ CARD — Sophie M.            │
│ 🏃 Running · Paris 11e      │
│ ⭐ 4.9 · 2.1km · Dès 45€/h  │
│ ✅ Certifiée BPJEPS         │
│ [Voir le profil →]          │
├─────────────────────────────┤
│ CARD — Marc D.              │
│ 💪 Musculation · Paris 12e  │
│ ⭐ 4.7 · 3.4km · Dès 35€/h  │
│ ✅ Certifié BPJEPS           │
│ [Voir le profil →]          │
└─────────────────────────────┘
```

**User Stories MVP prioritaires :**
| ID | Story | Priorité |
|----|-------|----------|
| US-01 | En tant que Lucas, je veux filtrer par sport et ville | MUST |
| US-02 | En tant que Lucas, je veux voir la certification du coach | MUST |
| US-03 | En tant que Lucas, je veux réserver en 3 clics max | MUST |
| US-04 | En tant que Lucas, je veux lire les avis authentifiés | MUST |
| US-05 | En tant que coach, je veux gérer mes disponibilités | MUST |

**Brief @cto :**
5 écrans Bubble. Données dynamiques : liste coachs
(filtrée), disponibilités (calendrier), paiement Stripe.
Composant Card réutilisable. État vide si 0 résultat.

---

## 💰 Agent 05 — FinanceMaster

### Input
> Tous les outputs précédents + "Budget 8 000€"

### Output

**Structure des coûts :**
| Poste | Type | Coût estimé |
|-------|------|-------------|
| Développement Bubble | One-shot | 0€ (self-build) |
| Design UI (Figma) | One-shot | 500€ |
| Frais légaux (CGU/RGPD) | One-shot | 600€ |
| Certification coachs | Récurrent | 0€ (badge manuel) |
| Bubble Pro | Récurrent | 29€/mois |
| Marketing lancement | One-shot | 1 000€ |
| Buffer imprévus (20%) | One-shot | 426€ |
| **TOTAL LANCEMENT** | | **~2 555€** |
| **RUNWAY** | | **~18 mois** |

**Projections de revenus (commission 15%) :**
| Scénario | Transactions/mois | Panier moyen | Revenus/mois |
|----------|------------------|--------------|--------------|
| Pessimiste | 20 | 40€ | 120€ |
| Réaliste | 50 | 45€ | 337€ |
| Optimiste | 150 | 50€ | 1 125€ |

**Indicateurs clés :**
- Point mort : 45 transactions/mois (~337€)
- Runway : 18 mois avec 8 000€
- ROI : scénario réaliste atteint à mois 6-8

**Verdict : ✅ Viable**
Budget largement suffisant pour un MVP Bubble.
Risque principal : acquisition clients lente si
stratégie organique insuffisante.
Consulter @marketing avant tout paid advertising.

---

## 📣 Agent 06 — MarketingMaster

### Input
> Tous les outputs précédents + "0€ budget marketing,
> 3h/semaine disponibles"

### Output

**Positionnement :**
- Value Prop : "Le seul endroit où trouver un coach
  certifié, près de chez toi, en moins de 5 minutes."
- Tagline : "Ton coach. Certifié. À deux pas."
- Ton : Rassurant / Motivant / Authentique

**Stratégie d'acquisition :**

Canal principal — LinkedIn (acquisition coachs)
- 3 posts/semaine : coulisses du projet, tips pour coachs
- DMs personnalisés : 5 coachs/semaine
- Budget : 0€ / 1h30/semaine

Canal secondaire — Instagram (acquisition clients)
- 3 posts/semaine : témoignages, tips fitness, before/after
- Hashtags : #coachsportif + [ville] + discipline
- Budget : 0€ / 1h30/semaine

**Copywriting prêt à l'emploi :**

Post LinkedIn (acquisition coachs) :
> "En tant que coach sportif indépendant, combien
> d'heures par semaine passes-tu à chercher des clients ?
> On construit une plateforme pour que les clients
> viennent à toi.
> 20 coachs fondateurs recherchés — 0% commission
> les 3 premiers mois.
> Intéressé ? Commente COACH 👇"

Email d'onboarding (premier client) :
> Objet : "Bienvenue sur CoachConnect 🏋️"
> "Ton premier coach certifié est à 2 minutes de chez toi.
> [Bouton] Trouver mon coach →"

---

## 📅 Agent 07 — RoadmapManager

### Input
> Tous les outputs précédents + "15h/semaine, deadline 3 mois"

### Output

**Priorisation MoSCoW :**
| Tâche | Catégorie |
|-------|-----------|
| Profils coachs + recherche | MUST |
| Système de réservation | MUST |
| Paiement Stripe | MUST |
| Système d'avis | SHOULD |
| Messagerie interne | COULD |
| Blog / SEO | WON'T |

**Roadmap :**

Phase 0 — Setup [2 semaines / 30h]
- [ ] Compte Bubble + configuration (3h)
- [ ] Compte Stripe + validation (2h) ← Faire JOUR 1
- [ ] Base de données Bubble (5h) ← Chemin critique
- [ ] Wireframes Figma des 5 écrans (8h)
- [ ] CGU + mentions légales (4h)
Livrable : Environnement opérationnel + wireframes validés

Phase 1 — MVP [5 semaines / 75h]
- [ ] Pages profils coachs (10h) ← Chemin critique
- [ ] Système recherche + filtres (12h)
- [ ] Intégration Stripe (8h)
- [ ] Page réservation (8h)
- [ ] Emails Postmark (3h)
- [ ] Tests internes (10h)
Livrable : MVP testable par 10 coachs + 10 clients pilotes
Critère : 5 transactions complètes sans bug bloquant

Phase 2 — V1 [4 semaines / 60h]
- [ ] Système d'avis (8h)
- [ ] Dashboard coach (10h)
- [ ] Onboarding optimisé (5h)
- [ ] Corrections bugs pilotes (10h)
Livrable : Plateforme prête au lancement public

**Risques calendaires :**
| Risque | Probabilité | Mitigation |
|--------|-------------|------------|
| Validation Stripe (délais) | Haute | Créer le compte semaine 1 |
| Bubble sous-estimé | Haute | +20% sur chaque estimation |
| 0 coach au lancement | Moyenne | Recruter 20 coachs avant la V1 |

**Prochaine action :**
Créer le compte Stripe aujourd'hui.
Délai : 48h pour validation. Sans ça, pas de paiement au lancement.

---

## 📒 Agent 08 — NotionMaster

### Input
> Roadmap RoadmapManager + "Crée un workspace de suivi
> pour ce projet"

### Output

**Architecture :**
```
📁 COACHCONNECT WORKSPACE
├── 🏠 Dashboard
├── 📋 Gestion de Projet
│   ├── 🗃️ DB Tâches
│   └── 🗃️ DB Sprints
├── 👥 Coachs & Clients
│   ├── 🗃️ DB Coachs (pipeline onboarding)
│   └── 🗃️ DB Clients (early adopters)
├── 💰 Finance
│   └── 🗃️ DB Budget
└── 📣 Marketing
    └── 🗃️ DB Calendrier Éditorial
```

**Dashboard — Vue d'ensemble :**
```
🏠 COACHCONNECT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📌 FOCUS SEMAINE
[Callout jaune : Objectif en cours]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[Col. gauche]              [Col. droite]
🔥 MES TÂCHES DU JOUR     👥 PIPELINE COACHS
[Linked View Tâches]      [Linked View DB Coachs]
Filtre: Aujourd'hui        Vue: Board (statut)

📊 BUDGET RESTANT          📣 CONTENU DU JOUR
[Linked View Budget]       [Linked View Calendrier]
Vue: Résumé                Filtre: Aujourd'hui
```

---

## 🧠 Agent 09 — StrategyMaster CEO

### Input
> Tous les outputs des 8 agents

### Output

**Contradictions identifiées :**
- Benchmark recommande la niche "coachs IA" mais
  le brief ProjectMaster vise tous les sports.
  → À arbitrer avant de développer.
- FinanceMaster indique un point mort à 45 transactions
  mais MarketingMaster n'a que 3h/semaine.
  → Rythme d'acquisition à challenger.

**Analyse stratégique :**

Court terme (0-3 mois) :
L'enjeu n'est pas de coder — c'est de recruter
20 coachs fondateurs AVANT le lancement.
Une plateforme vide le jour J = mort immédiate.
Priorité absolue : côté offre avant côté demande.

Moyen terme (3-12 mois) :
Le point mort à 45 transactions/mois suppose
une acquisition organique efficace.
Avec 3h/semaine, LinkedIn est le seul canal
réaliste pour atteindre les coachs rapidement.

Long terme (1-3 ans) :
Le vrai moat (avantage défensif) n'est pas
la plateforme — c'est la base de coachs certifiés
et les avis authentifiés. Construire ça dès le MVP.

**Arbitrage clé — Généraliste vs Niche :**
| Option | Impact | Risque | Ressources |
|--------|--------|--------|------------|
| Généraliste (tous sports) | Marché large | Concurrence forte | Élevées |
| Niche (running + musculation) | Focus exécutable | Marché restreint | Faibles |

✅ **Recommandation : Niche running + musculation**
Ces 2 disciplines représentent 68% des recherches
de coachs en France (Statista, 2025).
Dominer 2 niches vaut mieux qu'être invisible sur tout.

⚠️ Condition de pivot : si moins de 10 coachs
running + musculation recrutés en 4 semaines
→ élargir à tous les sports.

**Angle mort critique :**
Personne n'a adressé la **vérification des certifications**.
C'est le différenciateur #1 vs Superprof.
À construire dès le MVP : badge BPJEPS visible
sur chaque profil, vérifié manuellement avant publication.

**Optimisation de l'écosystème :**
- 💡 Nouvel agent suggéré : **GrowthHacker**
  Spécialisé acquisition early-stage et community building.
  Le point mort à 45 transactions nécessite une stratégie
  go-to-market dédiée qu'aucun agent actuel ne couvre assez.
- 🔧 Amélioration : Ajouter à RoadmapManager une
  phase "recrutement coachs" avant Phase 1 MVP.

**Décision prioritaire :**
Avant de créer quoi que ce soit sur Bubble :
contacter 10 coachs sportifs cette semaine via LinkedIn.
Objectif : 3 accords de principe pour rejoindre la beta.
Critère go/no-go : 3 OUI → on construit.
Moins de 3 → on pivote sur la niche ou le modèle.
Deadline : vendredi.

---

## 📊 Synthèse du flux complet

| Agent | Livrable clé | Temps |
|-------|-------------|-------|
| ProjectMaster | Brief + Objectif SMART + Périmètre MVP | ~15 min |
| Benchmark | Gap marché + 4 concurrents analysés + Opportunité | ~20 min |
| CTO Tech | Stack Bubble + Stripe + Architecture | ~15 min |
| ProductCraft | 5 wireframes + User Stories + Brief dev | ~20 min |
| FinanceMaster | Budget 2 555€ + Runway 18 mois + Verdict ✅ | ~15 min |
| MarketingMaster | Positionnement + 2 canaux + Copywriting | ~20 min |
| RoadmapManager | 3 phases + 12 semaines + Chemin critique | ~15 min |
| NotionMaster | Workspace complet prêt à l'emploi | ~20 min |
| StrategyMaster | Synthèse + Arbitrage niche + Décision GO | ~15 min |
| **TOTAL** | **Plan complet de lancement** | **~2h35** |

---

> 💡 Ce cas d'usage a été réalisé en utilisant les 9 agents
> en séquence manuelle. Chaque output a été collé comme
> contexte pour l'agent suivant.
>
> Résultat : en moins de 3 heures, un plan complet de
> lancement d'une marketplace, couvrant le cadrage,
> le marché, la tech, le design, les finances, le marketing,
> le planning, l'organisation Notion et la stratégie.

---

*Cas d'usage réalisé en mars 2026 — CoachConnect (projet fictif)*
