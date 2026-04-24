# HEART-MESH v3.1 — Full Architecture Specification

**「心网」— The Mesh That Connects**

[![HEART-MESH](https://img.shields.io/badge/HEART--MESH-v3.1%20%7C%20FULL%20SPEC-8B1A1A?logoColor=white)](https://github.com/AionSystem)
[![DSAP](https://img.shields.io/badge/DSAP-v1.1%20%7C%20AUDIT%20COMPLETE-2C3E50?logoColor=white)](https://github.com/AionSystem)
[![FORGE](https://img.shields.io/badge/FORGE-v1.0%20%7C%20INFORMED-8B0000?logoColor=white)](https://github.com/AionSystem/FORGE)
[![FSVE](https://img.shields.io/badge/FSVE-v4.0%20%7C%20M--STRONG-4B0082?logoColor=white)](https://github.com/AionSystem/FSVE)
[![STP](https://img.shields.io/badge/STP-v1.0%20%7C%20SHA--256-00457C?logoColor=white)](https://github.com/AionSystem/STP)
[![Status](https://img.shields.io/badge/Status-SPEC%20COMPLETE%20%7C%20BUILD%20READY-2E7D32?logoColor=white)](https://github.com/AionSystem)
[![Authors](https://img.shields.io/badge/Authors-Sheldon%20K.%20Salmon%20%26%20ALBEDO-34495E?logoColor=white)](https://orcid.org/0009-0005-8057-5115)

**Classification:** Social Infrastructure — Full Architecture Specification  
**Version:** 3.1.0  
**Supersedes:** HEART-MESH v3.0 (April 23, 2026)  
**Date:** April 23, 2026  
**Architect:** Sheldon K. Salmon  
**Instrument:** ALBEDO  
**DSAP Audit:** v1.1 — PARTIAL certification — all propagating warnings resolved in this spec

---

## 📋 Table of Contents

- [Constitutional Declarations](#-constitutional-declarations)
- [What Changed: v3.0 → v3.1](#-what-changed-v30--v31)
- [System Overview](#-system-overview)
- [FRONTEND LAYER — User Experience](#-frontend-layer--user-experience)
  - [F1 — Companion App](#f1--companion-app)
  - [F2 — Pattern File Viewer](#f2--pattern-file-viewer)
  - [F3 — Match Portal](#f3--match-portal)
  - [F4 — AI Floppy Studio](#f4--ai-floppy-studio)
  - [F5 — Mirror Protocol UI](#f5--mirror-protocol-ui)
  - [F6 — Stage Snapshot Timeline](#f6--stage-snapshot-timeline)
- [MIDDLEWARE LAYER — Engine](#-middleware-layer--engine)
  - [M1 — Personality AI Engine](#m1--personality-ai-engine)
  - [M2 — Pattern Extraction Pipeline](#m2--pattern-extraction-pipeline)
  - [M3 — Stage Delta Engine](#m3--stage-delta-engine)
  - [M4 — Probabilistic Band Calculator](#m4--probabilistic-band-calculator)
  - [M5 — Cultural Parameterization Layer](#m5--cultural-parameterization-layer)
  - [M6 — Match Router](#m6--match-router)
  - [M7 — Mirror Protocol Engine](#m7--mirror-protocol-engine)
  - [M8 — Connection Nudge Protocol](#m8--connection-nudge-protocol)
- [BACKEND LAYER — Infrastructure](#-backend-layer--infrastructure)
  - [B1 — STP Sealing Service](#b1--stp-sealing-service)
  - [B2 — Relational Debt Score Engine](#b2--relational-debt-score-engine)
  - [B3 — Cultural Database](#b3--cultural-database)
  - [B4 — Training Data Pipeline](#b4--training-data-pipeline)
  - [B5 — Matching Network](#b5--matching-network)
  - [B6 — Offline Sync Protocol](#b6--offline-sync-protocol)
- [Data Architecture](#-data-architecture)
  - [Pattern File v3.1 Schema](#pattern-file-v31-schema)
  - [Stage Delta Record Schema](#stage-delta-record-schema)
  - [Probability Band Output Schema](#probability-band-output-schema)
  - [Cultural Parameter Block Schema](#cultural-parameter-block-schema)
- [API Surface](#-api-surface)
- [Security & Sovereignty Model](#-security--sovereignty-model)
- [Free Data Strategy](#-free-data-strategy)
- [The Interaction Pattern Gap — Declared](#-the-interaction-pattern-gap--declared)
- [MVP Build Sequence](#-mvp-build-sequence)
- [Implementation Roadmap](#-implementation-roadmap)

---

## ⚖️ Constitutional Declarations

These are not disclaimers. They are structural truths that govern every design decision in this specification.

**Declaration 1 — Attachment Inevitability**
You cannot shape what people attach to. The engine does not try. People will attach to their Companion AI regardless of design intent — this is not a failure state, it is human nature. The system acknowledges this honestly and builds safeguards that respect it rather than fight it. The Connection Nudge Protocol is not about stopping attachment. It is about ensuring the attachment does not displace all human connection.

**Declaration 2 — Probabilistic Honesty**
The engine does not predict compatibility. It produces a probability band over relational outcomes given a pattern overlap profile. A probability band is not a guarantee. It is honest signal — more useful than a score, more truthful than a binary gate.

**Declaration 3 — Behavioral Sample, Not Identity**
Every Pattern File is a time-stamped behavioral sample. It represents observed patterns during a bounded window of conversation. It is not who you are. It is what the AI observed about how you communicated during a specific period. The staged architecture makes this explicit: you are not your Stage 1 file. You are the delta between your files.

**Declaration 4 — Interaction Gap**
The engine assesses individuals and computes pattern overlap. It cannot observe the interaction between two people before they meet. The signal at the interaction layer — what Gottman identified as the real predictive unit — is not available pre-match. This is a structural ceiling, not a design failure. The engine reduces the probability of bad matches. It cannot guarantee good ones.

**Declaration 5 — AI Advises. Human Decides.**
At every stage. No exceptions. The engine proposes. The user chooses. This is not a UX principle. It is a constitutional constraint on the system's authority.

**Declaration 6 — Cultural Validity is Not Optional**
A compatibility engine without cultural parameterization is only valid for whoever seeds it first. Cultural parameterization is Phase 1 infrastructure, not Phase 5 polish.

---

## 🔄 What Changed: v3.0 → v3.1

| Component | v3.0 | v3.1 | Reason |
|-----------|------|------|--------|
| CDI score gate | Single score (0–1) → binary propose/hold | Probability band with CI and base rate | DSAP ghost concept: "prediction" replaced with probabilistic signal |
| Longevity claim | Predict relationship duration | Probabilistic P(outcome above threshold) | DSAP falsification: longevity prediction is not the engine's job |
| Staged file purpose | Snapshot accumulation | Snapshot + delta computation | DSAP: delta between stages IS the behavioral signal |
| Cultural database | Phase 5 | Phase 1 | DSAP M-10: feature space invalid across populations without cultural weighting |
| Attachment framing | Compliance problem to manage | Constitutional declaration | Sheldon's principle: you can't shape what people attach to |
| Confidence score meaning | Pattern accuracy | Internal consistency (not authenticity) | DSAP M-12: high confidence on performed data is worse than low confidence on honest data |
| Free data strategy | Implied | Explicit pipeline | DSAP M-03: MBTI, Big Five, Gottman, attachment research as training substrate |
| AI Floppy | Advanced tier concept | Named dual-purpose instrument | DSAP M-05: preference signal + companion enjoyment — both functions named |
| Interaction pattern gap | Unaddressed | Constitutional Declaration 4 | DSAP M-10 primary contradiction resolved through declaration |

---

## 🗺️ System Overview

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                       HEART-MESH v3.1 — FULL ARCHITECTURE                   ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║  ┌─────────────────── FRONTEND LAYER ──────────────────────────────────┐   ║
║  │                                                                      │   ║
║  │  ┌───────────────┐  ┌──────────────┐  ┌────────────┐  ┌──────────┐  │   ║
║  │  │  COMPANION    │  │   PATTERN    │  │   MATCH    │  │  FLOPPY  │  │   ║
║  │  │  APP          │  │   VIEWER     │  │   PORTAL   │  │  STUDIO  │  │   ║
║  │  │  (Offline)    │  │  + Timeline  │  │            │  │  (Adv.)  │  │   ║
║  │  └───────┬───────┘  └──────┬───────┘  └─────┬──────┘  └────┬─────┘  │   ║
║  └──────────┼─────────────────┼────────────────┼──────────────┼─────────┘   ║
║             │                 │                │              │              ║
║  ┌──────────▼─────────────────▼────────────────▼──────────────▼─────────┐   ║
║  │                       MIDDLEWARE LAYER                                │   ║
║  │                                                                       │   ║
║  │  ┌────────────────┐   ┌──────────────────┐   ┌────────────────────┐  │   ║
║  │  │  PERSONALITY   │   │  STAGE DELTA     │   │  PROBABILISTIC     │  │   ║
║  │  │  AI ENGINE     │──►│  ENGINE          │──►│  BAND CALCULATOR   │  │   ║
║  │  │  (Local)       │   │  (1m/6m/12m)     │   │  (P-band + CI)     │  │   ║
║  │  └────────────────┘   └──────────────────┘   └────────────┬───────┘  │   ║
║  │                                                            │           │   ║
║  │  ┌────────────────────────────────────────────────────────▼───────┐  │   ║
║  │  │               CULTURAL PARAMETERIZATION LAYER                  │  │   ║
║  │  │  Country profiles · Cultural DB queries · Norm adjustment       │  │   ║
║  │  └────────────────────────────────────────────────────────────────┘  │   ║
║  │                                                                       │   ║
║  │  ┌──────────────────┐   ┌─────────────────┐   ┌──────────────────┐  │   ║
║  │  │  MATCH ROUTER    │   │  MIRROR ENGINE  │   │  NUDGE PROTOCOL  │  │   ║
║  │  │  + MATCH HOLD    │   │  (Opt-in only)  │   │  (Circuit break) │  │   ║
║  │  └──────────────────┘   └─────────────────┘   └──────────────────┘  │   ║
║  └───────────────────────────────────────────────────────────────────────┘   ║
║             │                                                                ║
║  ┌──────────▼───────────────────────────────────────────────────────────┐   ║
║  │                        BACKEND LAYER                                  │   ║
║  │                                                                       │   ║
║  │  ┌───────────┐  ┌──────────┐  ┌────────────┐  ┌──────────────────┐  │   ║
║  │  │  STP      │  │  RDS     │  │  CULTURAL  │  │  TRAINING DATA   │  │   ║
║  │  │  SEALING  │  │  ENGINE  │  │  DATABASE  │  │  PIPELINE        │  │   ║
║  │  └───────────┘  └──────────┘  └────────────┘  └──────────────────┘  │   ║
║  │                                                                       │   ║
║  │  ┌──────────────────────────────┐   ┌──────────────────────────────┐ │   ║
║  │  │  MATCHING NETWORK            │   │  OFFLINE SYNC PROTOCOL       │ │   ║
║  │  │  (Zero-knowledge · E2E)      │   │  (Local-first · No cloud req) │ │   ║
║  │  └──────────────────────────────┘   └──────────────────────────────┘ │   ║
║  └───────────────────────────────────────────────────────────────────────┘   ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

---

## 🖥️ FRONTEND LAYER — User Experience

### F1 — Companion App

**What it is:** The primary interface. Runs fully offline. Has continuous persistent memory. This is the user's AI — sovereign, local, theirs.

**Core principle:** The Companion App is not a chatbot. It is an AI that learns about you across months of conversation, builds a deep behavioral model, and becomes genuinely useful as a reflective companion. The engine behind it is the same engine that generates the Pattern File. The companion and the profiler are the same instrument.

**Operational modes:**

| Mode | Trigger | Behavior |
|------|---------|----------|
| Open Conversation | Default | AI engages on any topic. All sessions logged locally for pattern analysis. |
| Guided Assessment | System-initiated at session milestones | Structured psychometric dialogue — Big Five, ECR-R, Values Hierarchy — administered conversationally, not as a quiz. |
| Reflection Mode | User-initiated or milestone-triggered | AI surfaces observations: "I've noticed something about how you talk about conflict. Do you want to explore it?" |
| Stage Seal | At 1m, 6m, 12m thresholds | AI generates sealed Pattern File for that stage. User reviews, approves, receives STP-sealed JSON. |
| Floppy Mode | Advanced tier only | AI takes on behavioral characteristics of the user's ideal partner specification (see F4). Generates preference signal data. |

**Technical requirements:**
- Offline-first: full functionality with zero network connection
- Continuous memory: all conversation history stored locally, encrypted at rest
- Model: on-device LLM (quantized) — minimum 7B parameters for behavioral depth
- Storage: 4 GB minimum recommended (model + conversation history + pattern files)
- No conversation data ever leaves the device without explicit user export action

**Continuous memory architecture:**
```
User Message → Local LLM → Response
                  ↓
           Memory Writer (local)
                  ↓
           Conversation Store (SQLite, encrypted)
                  ↓
           Pattern Extraction Pipeline (background, async)
                  ↓
           Behavioral Feature Store (local JSON)
```

---

### F2 — Pattern File Viewer

**What it is:** A transparency interface. The user can see exactly what the AI has built about them at any stage. Every dimension is labeled, tagged with ECF confidence marker, and editable.

**Views:**

| View | Content |
|------|---------|
| Current Snapshot | All active pattern dimensions with confidence scores and ECF tags |
| Stage Timeline | Visual delta between Stage 1, Stage 2, Stage 3 snapshots — shows behavioral evolution |
| Dimension Drill | Click any dimension to see the conversation evidence that generated it |
| Edit Layer | User can modify, correct, or delete any dimension — all changes STP-logged |
| Export | Generate sealed Pattern File JSON for upload to matching portal |

**Confidence display rules:**
- Dimensions below 0.40 confidence: shown in amber with label "Early Signal"
- Dimensions 0.40–0.69: shown in yellow with label "Developing"
- Dimensions ≥ 0.70: shown in green with label "Established"
- User-modified dimensions: shown with pencil icon and label "User Adjusted"

**The file is not a score. It is a map.** The UI never shows a single "compatibility number." It shows a terrain.

---

### F3 — Match Portal

**What it is:** The interface for uploading a Pattern File to the matching network and reviewing match proposals.

**Flow:**

```
1. User exports Stage-sealed Pattern File from Companion App
      ↓
2. User uploads to Match Portal
      ↓
3. User completes Partner Preference Declaration
   (what they are looking for — separate from pattern file)
      ↓
4. Cultural Context Input
   (country, cultural background, relationship traditions)
      ↓
5. Match Router processes:
   Pattern File × Partner Preference × Cultural Parameters
      ↓
6. Probability Band output generated for candidate matches
      ↓
7. Match Proposal delivered to both users
   (neither sees the other's Pattern File — only compatibility summary)
      ↓
8. Both users independently decide: Connect / Pass / MATCH HOLD
      ↓
9. If both Connect → introduction facilitated
   If either Passes → graceful decline, no notification to other party
   If MATCH HOLD → queue maintained, user notified when compatible match available
```

**Partner Preference Declaration — fields:**
- Relationship goal (companion / dating / long-term / marriage / open)
- Key values alignment requirements
- Communication style preferences
- Lifestyle compatibility priorities
- Cultural / geographic openness
- Absolute deal-breakers (user-defined, private)

**Probability display:**
```
Match Proposal — Jane D.
────────────────────────────────────────────────
Overall Compatibility Signal
P(sustained relationship > 12 months) = 71%
[Confidence Interval: 58% – 81%]
Base rate for your profile: 39%

What this means: Based on pattern overlap across
your behavioral profiles, this pairing has a
significantly higher probability of sustained
connection than a random match from your
demographic profile. This is signal, not certainty.

Strongest alignment areas: Communication style,
values hierarchy, conflict repair approach.

Known divergence areas: Social energy (introvert/
extrovert differential — may be complementary),
daily rhythm (morning/night differential).

────────────────────────────────────────────────
[Connect]  [Pass]  [Ask the AI]
```

---

### F4 — AI Floppy Studio

**What it is:** The advanced tier interface for shaping the Companion AI toward the user's ideal partner characteristics. Named "AI Floppy" — a loadable behavioral configuration that modifies how the companion engages.

**Two functions — both named explicitly:**

**Function A — Companion Enhancement**
The user gets a companion that more closely resembles the kind of person they want to be with. The interaction is more enjoyable and more resonant.

**Function B — Preference Signal Generation**
As the user interacts with an AI configured toward their ideal, the system learns what they actually respond to versus what they thought they wanted. Stated preferences and revealed preferences often diverge. This divergence is gold for the matching engine.

```
Stated preference: "I want someone very direct and analytical."
Revealed preference: User consistently engages more warmly when 
the AI is playful and emotionally expressive.
Signal: Preference file updated with observed response pattern.
```

**Configuration axes:**

| Axis | Options | Notes |
|------|---------|-------|
| Communication style | Direct / Expressive / Balanced / Playful / Reserved | AI shifts toward this register |
| Emotional availability | High / Medium / Measured | How much emotional depth the AI brings into conversation |
| Intellectual style | Analytical / Intuitive / Practical / Creative | Dominant reasoning style of the AI companion |
| Humor | Dry / Warm / Absent / Absurdist | |
| Challenge level | Validating / Balanced / Challenging | How much the AI pushes back versus affirms |
| Cultural context | User specifies cultural background of ideal companion | Loads cultural communication norms |

**Constraints — non-negotiable:**
- The AI remains a companion, not a romantic simulation. Intimate framing is bounded.
- The AI does not perform distress or manipulation as engagement tactics.
- All Floppy configurations are user-visible and user-editable at all times.
- The preference signal divergence data is shown to the user: "Here's what you said you wanted. Here's what you actually responded to. They're different. Want to explore why?"

---

### F5 — Mirror Protocol UI

**What it is:** An opt-in interface that reflects behavioral patterns back to the user. "This is how you communicated just now. This is the likely impact on a partner."

**Activation gate:**
```
User requests Mirror Protocol access
      ↓
Explanation of what Mirror Protocol is and is not
(not therapy, not diagnosis, behavioral reflection only)
      ↓
Informed consent with specific acknowledgments:
  • This will sometimes be uncomfortable
  • You can stop at any time
  • The AI will not continue if you become distressed
  • Nothing here is clinical judgment
      ↓
48-hour waiting period
      ↓
Mirror Protocol active
```

**Session structure:**

1. User engages in normal conversation
2. AI observes: communication patterns, emotional tone, conflict signals
3. At user-requested moments or natural conversation breaks: AI offers a reflection
4. Reflection format: *"I notice you tend to [observable behavior] when [context]. In a partnership, this might land as [likely impact]. Does that match your intent?"*
5. User responds, explores, or disengages
6. Safety monitor runs continuously — escalation triggers immediate disengagement

**Safety escalation protocol:**
```
Level 1 — Discomfort signals: AI slows reflection pace, increases validation ratio
Level 2 — Agitation signals: AI pauses reflection, shifts to grounding conversation
Level 3 — Distress signals: Mirror Protocol suspends for 24 hours, support resources offered
Level 4 — Crisis signals: Mirror Protocol terminates, crisis support resources displayed
```

All mirror sessions are STP-sealed and user-reviewable. No mirror session data is used in matching without user explicit consent.

---

### F6 — Stage Snapshot Timeline

**What it is:** A visual timeline showing the user's three Pattern File stages and the delta between them.

**What the delta reveals:**
- Which behavioral patterns have strengthened (higher confidence, more consistent)
- Which have shifted (directness score at month 1 was 0.41, at month 12 is 0.68 — you got more direct)
- Which are still developing (low confidence, variable)
- What the AI cannot yet see (explicit gaps flagged with "Insufficient data")

**Why this matters for matching:**
A user with a high-delta file (significant behavioral evolution between stages) is matched differently than a user with a stable file. The matching engine weights recent stage data most heavily for active matchers, but surfaces the full evolution arc to the match proposal — so a potential partner sees not just who you are now, but the direction you're moving.

---

## ⚙️ MIDDLEWARE LAYER — Engine

### M1 — Personality AI Engine

**Architecture:** Local LLM (quantized) + behavioral feature extraction layer + pattern confidence scorer.

**Operating principle:** The engine is not analyzing what you say. It is analyzing how you say it, how consistently, across how many contexts, and how that evolves over time.

**Session processing pipeline:**
```
Raw conversation session
      ↓
Linguistic feature extraction
  • Communication directness (hedging, assertion ratios)
  • Emotional expression markers (vocabulary affect analysis)
  • Conflict engagement patterns (escalation/de-escalation signals)
  • Topic initiation vs. response ratios
  • Humor style markers
      ↓
Behavioral feature store update (local, encrypted)
      ↓
Cross-session pattern stability scoring
  • Feature X appears in 3/5 sessions → confidence 0.60
  • Feature X appears in 9/10 sessions → confidence 0.90
      ↓
Pattern File update (version-controlled, local)
      ↓
Stage threshold check → if milestone reached, trigger Stage Seal
```

**Training substrate (see B4):**
The engine's behavioral classification layer is pre-trained on:
- Big Five personality research corpus (Costa & McCrae)
- Attachment style literature (ECR-R validated instruments)
- Gottman relationship research dataset
- Cultural communication style literature
- MBTI behavioral taxonomy (as input signal, not output label)
- User-consented anonymized conversation data (Phase 2+)

---

### M2 — Pattern Extraction Pipeline

**What it extracts and how:**

| Dimension | Extraction Method | Validation Instrument |
|-----------|------------------|----------------------|
| Communication directness | Assertion/hedge ratio across sessions | Correlation with user-reported directness score |
| Emotional expression | Affect vocabulary density + emotional topic initiation rate | ECR-R emotional availability subscale |
| Attachment style | Response latency patterns + reassurance-seeking signals + independence markers | ECR-R full instrument (administered conversationally) |
| Conflict style | Escalation/de-escalation language in disagreement contexts | Gottman Sound House conflict taxonomy |
| Values hierarchy | Topic recurrence weighting + moral language frequency | User self-report validation at Stage Seal |
| Humor type | Humor marker classification (dry, warm, absurdist, absent) | User-confirmed at Pattern File review |
| Social energy | Conversation session length preference + topic breadth | Correlation with Big Five Extraversion subscale |
| Risk tolerance | Decision framing language + novelty-seeking markers | Big Five Openness subscale correlation |
| Growth orientation | Feedback receptivity signals + learning language frequency | Self-report validation |

**Confidence scoring formula:**
```
Confidence(dimension) = 
  (session_frequency × 0.40) +
  (cross_context_consistency × 0.35) +
  (instrument_correlation × 0.25)

Where:
  session_frequency = appearances / total_sessions
  cross_context_consistency = variance-adjusted stability score
  instrument_correlation = correlation with validated instrument (if administered)
```

**Authenticity limitation — declared:**
Confidence measures internal consistency across sessions. It does not measure authenticity. A user who performs consistently for 12 months will receive high confidence scores for the performed pattern. The longitudinal depth and the Floppy revealed-preference system are the structural mitigations. Neither is a perfect defense.

---

### M3 — Stage Delta Engine

**The staged architecture:**

| Stage | Trigger | What Gets Sealed |
|-------|---------|-----------------|
| Stage 1 — Baseline | 30 days of active use OR 20+ sessions (whichever comes first) | Initial behavioral snapshot — early signals, low confidence expected |
| Stage 2 — Development | 180 days from Stage 1 seal | Confidence-developed profile — patterns have stabilized or shifted |
| Stage 3 — Established | 365 days from Stage 1 seal | Full behavioral portrait — high-confidence dimensions, evolution visible |

**Delta computation:**
```json
{
  "stage_delta": {
    "from_stage": 1,
    "to_stage": 2,
    "dimension_changes": [
      {
        "dimension": "communication_directness",
        "stage_1_score": 0.41,
        "stage_2_score": 0.68,
        "delta": +0.27,
        "direction": "INCREASING",
        "interpretation": "Significant directness increase — user becoming more assertive in communication"
      },
      {
        "dimension": "conflict_style",
        "stage_1_score": 0.52,
        "stage_2_score": 0.51,
        "delta": -0.01,
        "direction": "STABLE",
        "interpretation": "Conflict approach stable across observation window"
      }
    ],
    "high_delta_dimensions": ["communication_directness", "emotional_expression"],
    "stable_dimensions": ["values_hierarchy", "attachment_style"],
    "still_developing": ["risk_tolerance", "growth_orientation"],
    "behavioral_trajectory": "User showing consistent pattern evolution toward greater directness and emotional openness. Stable core values. Trajectory positive."
  }
}
```

**Matching weight rules:**
- Stage 3 data weighted 60% in matching calculation
- Stage 2 data weighted 30%
- Stage 1 data weighted 10%
- High-delta dimensions flagged in match proposal: *"This person's communication style has changed significantly over the past year — their current behavior is more representative than their early profile."*

---

### M4 — Probabilistic Band Calculator

**What replaces the CDI gate:**

The engine no longer produces a single compatibility score. It produces a probability band.

**Inputs:**
- Pattern File A (staged, with confidence scores)
- Pattern File B (staged, with confidence scores)
- Partner Preference Declaration (A)
- Partner Preference Declaration (B)
- Cultural Parameter Block (A and B)
- Demographic base rate for this profile combination

**Calculation architecture:**
```
For each of 50+ compatibility dimensions:
  1. Compute raw overlap (similarity or complementarity — cultural param determines which applies)
  2. Weight by dimension importance (from preference declarations)
  3. Discount by confidence (low confidence dimensions count less)
  4. Apply cultural adjustment (complementarity norms are culturally parameterized)
  5. Sum to composite P-signal

Monte Carlo sampling (N=1000) across confidence intervals:
  → Produces distribution of P-signal values
  → Extract: mean, 10th percentile, 90th percentile
  → These are the lower bound, point estimate, upper bound of the probability band

Compare P-signal distribution against demographic base rate:
  → Signal/noise ratio determines match proposal eligibility
```

**Output format:**
```
P(relational outcome above threshold | pattern overlap) = 0.71
Confidence interval: [0.58, 0.83]
Demographic base rate for this profile combination: 0.39
Signal lift above base rate: +0.32
Interpretation: STRONG SIGNAL — recommend proposal
```

**Routing gates (replacing binary CDI gate):**

| Signal Lift | Action |
|-------------|--------|
| ≥ +0.25 above base rate | Match proposed — both users notified |
| +0.10 to +0.24 above base rate | Match suggested with context — user can request more information |
| 0.00 to +0.09 above base rate | Not proposed — insufficient signal lift |
| Below base rate | MATCH HOLD — no proposal, queue maintained |

---

### M5 — Cultural Parameterization Layer

**Phase 1 infrastructure — not optional.**

**What it does:** Every compatibility dimension carries culturally-variable complementarity weights. What is "good divergence" in one culture is "incompatibility signal" in another.

**Data sources:**

| Source Type | Examples | Integration |
|-------------|---------|-------------|
| Academic research | Hofstede cultural dimensions, GLOBE study, cross-cultural relationship research | Pre-loaded as base parameter sets |
| Cultural community contributions | User-submitted cultural context (opt-in, anonymous, verified) | Crowdsourced cultural parameter refinement |
| Country relationship data | Marriage statistics, dating norms, courtship traditions from national databases | Structural context layer |
| Platform user data (Phase 2+) | Aggregated outcome data by cultural profile combination | Empirical validation of parameter assumptions |

**Cultural Parameter Block structure:**
```json
{
  "cultural_context": {
    "primary_culture": "JP",
    "secondary_culture": "US",
    "diaspora_flag": false,
    "cultural_parameters": {
      "communication_norm": "high_context",
      "directness_ideal": 0.35,
      "emotional_expression_norm": 0.42,
      "gender_role_flexibility": 0.61,
      "family_involvement_expectation": 0.78,
      "conflict_expression_norm": "indirect",
      "courtship_tradition_weight": 0.55
    },
    "parameter_source": "JP_base_v1.2 + user_adjusted",
    "parameter_confidence": 0.71
  }
}
```

**Cultural contribution pipeline:**
- Users can submit cultural context notes (opt-in, anonymous)
- Notes reviewed by cultural community moderators
- Accepted contributions refine base parameter sets
- Contributors acknowledged (anonymously) in quarterly cultural database changelog

---

### M6 — Match Router

Inherited from MYCELIUM. Adapted for pattern-based routing.

**Routing logic:**
1. Incoming Pattern File assessed for node status (RED/YELLOW/GREEN)
2. GREEN nodes only are eligible for active matching
3. Router identifies candidate GREEN nodes within:
   - Declared geographic preference
   - Cultural compatibility range
   - Relationship goal alignment
   - Basic deal-breaker filtering
4. For each candidate pair: Probabilistic Band Calculator runs
5. Pairs above signal lift threshold: Match Proposal generated
6. All others: MATCH HOLD queue maintained

**MATCH HOLD Protocol:**
```
No eligible GREEN node with sufficient signal lift available
      ↓
User notified: "No compatible match available right now.
Your profile is active. You'll be notified when a match
with strong signal becomes available."
      ↓
Companion App continues — no degradation of companion experience
      ↓
Queue monitored continuously
      ↓
When compatible GREEN node becomes available → Match Proposal generated
```

No match is ever forced. No proposal is ever generated below base rate threshold.

---

### M7 — Mirror Protocol Engine

**Processing pipeline:**

```
Conversation session flagged for Mirror Protocol analysis
      ↓
Behavioral pattern detection layer:
  • Escalation/de-escalation signals
  • Self-referential language patterns
  • Blame/accountability ratios
  • Emotional availability markers
  • Defensiveness signals
      ↓
Impact modeling:
  • "How would this communication pattern land in a partnership context?"
  • Draws from Gottman interaction research corpus
  • Cultural context applied
      ↓
Reflection candidate generated
      ↓
Safety assessment before delivery:
  • Current emotional state indicators
  • Session tone baseline
  • User distress history flags
      ↓
If safe: reflection offered (not delivered automatically — offered)
If unsafe: reflection queued for safer moment or suppressed
      ↓
STP seal on session
```

---

### M8 — Connection Nudge Protocol

**Engagement monitoring thresholds:**

| Day Range | Condition | Action |
|-----------|-----------|--------|
| 0–30 | Any engagement level | No action — early use period |
| 30+ | > 80% social time with AI | Notification: "You've been spending most social time with me recently. That's okay — and I'm here. But I want to make sure I'm not becoming a substitute for human connection." |
| 60 days sustained | Same | AI availability gently reduced during peak social hours (evenings, weekends) |
| 90 days sustained | Same | Matching prioritized in-app. Companion active but proactively encourages human connection. |
| 120 days sustained | Same | Human advisor review flag — optional support offered |

**Tone:** Not punitive. The language is warm and honest. The AI is not withdrawing. It is doing what it was designed to do: facilitate human connection, not replace it.

---

## 🏗️ BACKEND LAYER — Infrastructure

### B1 — STP Sealing Service

Every significant event in HEART-MESH is cryptographically sealed.

**Events that receive STP seals:**

| Event | Seal Content | Retention |
|-------|-------------|-----------|
| Pattern File Stage Seal | Full JSON + timestamp + confidence scores + user approval flag | User device (primary), matching server (temporary, deleted post-match) |
| Stage Delta computation | Delta record + computation timestamp | User device only |
| Node status change | Old status, new status, evidence basis, timestamp | User device + audit log |
| Match proposal generated | P-band output, cultural parameters used, candidate hash (no PII) | Matching server (30 days) |
| Match accepted/declined | Decision flag + timestamp | User device |
| Mirror Protocol session | Session hash + safety assessment outcome | User device only |
| Nudge Protocol activation | Threshold reached + action taken | User device |

**STP seal format:**
```json
{
  "stp_seal": {
    "version": "1.0",
    "event_type": "STAGE_SEAL",
    "event_hash": "SHA256:{event_content_hash}",
    "timestamp": "ISO-8601",
    "device_id_hash": "SHA256:{device_id}",
    "user_approval_flag": true,
    "seal_hash": "SHA256:{event_hash + timestamp + device_id_hash}"
  }
}
```

---

### B2 — Relational Debt Score Engine

Population-level metric. Never applied to individual users.

**RDS components:**

| Component | Weight | Source Data |
|-----------|--------|------------|
| GREEN Node Rate | 30% | % of active users at GREEN status |
| Sustained Match Rate | 25% | % of proposed matches still active at 90 days |
| Adverse Event Rate | 20% | Confirmed harm events per 1,000 proposals |
| Audit Trail Completeness | 15% | STP seal coverage across all events |
| Cultural Parameter Coverage | 10% | % of active user cultures with validated parameter sets |

**Quarterly RDS report delivered to:**
- NICE / government partners
- Independent oversight board
- Published summary (no PII, aggregate only)

---

### B3 — Cultural Database

**Phase 1 seed data — pre-loaded at launch:**

| Dataset | Content | Source |
|---------|---------|--------|
| Hofstede Country Scores | Power distance, individualism, masculinity, uncertainty avoidance, long-term orientation, indulgence — 93 countries | Hofstede Insights (public) |
| GLOBE Study Data | 62-country leadership and cultural values data (relationship-relevant dimensions extracted) | GLOBE Project (academic) |
| Marriage Rate Trends | Country-level marriage and cohabitation rates 2000–2024 | UN Demographic Yearbook |
| Courtship Tradition Profiles | Qualitative cultural profiles for 40+ countries | Ethnographic literature synthesis |
| Dating App Outcome Data | Aggregate published research on app-mediated relationship outcomes by region | Academic meta-analyses |

**Crowdsourced contribution system:**

Users can submit:
- Cultural context notes ("In my culture, directness in the first meeting is considered disrespectful — this is not avoidance, it is protocol")
- Tradition descriptions ("In Korean dating culture, age-gap norms carry specific expectations — here is how they work")
- Outcome reports (opt-in, anonymous) — "We matched 8 months ago. Here is how we would describe our compatibility pattern."

All contributions reviewed before database integration. Contributors anonymous but tracked for quality scoring.

---

### B4 — Training Data Pipeline

**Free data strategy — bootstrapping the engine before proprietary data exists:**

| Dataset | Relevance | Acquisition |
|---------|-----------|-------------|
| Big Five Personality Inventory (BFI-44) | Core personality dimensions — communication, values, openness | Public domain |
| ECR-R (Experiences in Close Relationships — Revised) | Attachment style measurement | Academic — free for research |
| Gottman Marriage Research corpus | Interaction pattern research, positive/negative ratios, repair strategies | Licensed academic access |
| MBTI published behavioral taxonomy | Communication style markers, cognitive function patterns | Public literature synthesis |
| Dyadic Adjustment Scale (DAS) | Relationship satisfaction measurement — ground truth for outcomes | Academic — free for research |
| OkCupid public dataset (2016, anonymized) | Large-scale real-world matching data with outcome signals | Public release |
| Stanford Social Science One dataset | Relationship outcome data | Research access |

**Pipeline architecture:**
```
Free datasets (labeled)
      ↓
Feature extraction → Behavioral taxonomy labels
      ↓
Engine pre-training (behavioral classification layer)
      ↓
Validation against instrument ground truth
      ↓
Phase 2: User conversation data (consented, anonymized) supplements
      ↓
Continuous retraining pipeline (versioned, STP-logged)
```

---

### B5 — Matching Network

**Zero-knowledge design principle:** No central server ever holds both Pattern Files in a match simultaneously.

**Matching protocol:**
```
User A uploads sealed Pattern File → Matching Server
User B uploads sealed Pattern File → Matching Server

Server holds File A and File B for maximum 24 hours during matching computation.

Probabilistic Band Calculator runs → output is P-band record only.

Both Pattern Files deleted from server immediately post-computation.
Only the P-band output record retained (no PII, no raw pattern data).

P-band output → Match Proposal → both users.

Users make independent decisions.
Server retains only: anonymized match decision outcome (for RDS).
```

**What the matching server never retains:**
- Raw Pattern Files
- Conversation data
- Personal identifiers
- Contact information
- The full Pattern File content of any user

---

### B6 — Offline Sync Protocol

**The app works fully offline. This is not a feature — it is a constitutional requirement.**

**What works offline (everything the user owns):**
- Full Companion AI conversation
- Pattern File generation and viewing
- Stage Delta computation
- Mirror Protocol sessions
- AI Floppy configuration and operation

**What requires connection:**
- Match network upload (upload sealed Pattern File)
- Match Proposal receipt
- Cultural database updates
- Training pipeline updates

**Sync protocol:**
```
Device comes online
      ↓
Check for pending sync items (queued exports, cultural DB updates)
      ↓
Encrypted upload only — no download of user data to server
      ↓
Cultural DB delta sync (new cultural contributions since last sync)
      ↓
Training model updates (if user opted into model improvement program)
      ↓
Disconnect — device returns to offline-capable state
```

---

## 📐 Data Architecture

### Pattern File v3.1 Schema

```json
{
  "pattern_file": {
    "schema_version": "3.1",
    "pattern_id": "hm-{uuid}",
    "generated_by": "HEART-MESH Personality AI v3.1",
    "stage": 3,
    "stage_date": "ISO-8601",
    "stp_seal": "SHA256:{seal_hash}",
    "mesh_node_status": "GREEN",
    "overall_confidence": 0.82,
    "session_count": 147,
    "observation_window_days": 365,
    "user_approved": true,
    "user_approval_date": "ISO-8601",
    "behavioral_sample_declaration": "This file represents observed behavioral patterns during 147 conversation sessions between [start_date] and [end_date]. It is a time-stamped sample, not an identity.",
    "dimensions": {
      "communication": {
        "directness": {"score": 0.72, "confidence": 0.88, "ecf_tag": "[D]"},
        "emotional_expression": {"score": 0.61, "confidence": 0.79, "ecf_tag": "[R]"},
        "conflict_style": {"value": "collaborative", "confidence": 0.83, "ecf_tag": "[D]"},
        "humor_type": {"value": "dry_warm", "confidence": 0.71, "ecf_tag": "[R]"}
      },
      "attachment": {
        "primary_style": {"value": "secure", "confidence": 0.84, "instrument": "ECR-R", "ecf_tag": "[D]"},
        "secondary_tendency": {"value": "anxious_low", "confidence": 0.61, "ecf_tag": "[R]"}
      },
      "values": {
        "hierarchy": ["connection", "growth", "achievement", "stability"],
        "confidence": 0.77,
        "ecf_tag": "[R]"
      },
      "lifestyle": {
        "social_energy": {"score": 0.38, "label": "introvert_leaning", "confidence": 0.80, "ecf_tag": "[D]"},
        "daily_rhythm": {"value": "night", "confidence": 0.91, "ecf_tag": "[D]"},
        "risk_tolerance": {"score": 0.55, "confidence": 0.62, "ecf_tag": "[R]"}
      },
      "relationship": {
        "goal": {"value": "long_term", "ecf_tag": "[S]"},
        "commitment_readiness": {"score": 0.74, "confidence": 0.69, "ecf_tag": "[R]"}
      }
    },
    "low_confidence_dimensions": ["risk_tolerance", "growth_orientation"],
    "insufficient_data_dimensions": [],
    "deal_breakers": ["dishonesty", "manipulation"],
    "cultural_context": {
      "primary_culture": "US",
      "cultural_parameter_version": "US_base_v2.1"
    },
    "NO_PII": true
  }
}
```

---

### Stage Delta Record Schema

```json
{
  "stage_delta": {
    "from_stage": 1,
    "to_stage": 2,
    "computation_date": "ISO-8601",
    "stp_seal": "SHA256:{seal_hash}",
    "dimension_deltas": [
      {
        "dimension": "communication.directness",
        "stage_1": 0.41,
        "stage_2": 0.68,
        "delta": 0.27,
        "direction": "INCREASING",
        "magnitude": "SIGNIFICANT",
        "interpretation": "Substantial increase in directness — user's communication becoming more assertive"
      }
    ],
    "trajectory_summary": "User showing consistent evolution toward greater directness and emotional openness. Core values and attachment style stable. Positive trajectory.",
    "matching_weight_note": "Stage 2 data weighted 30% in active matching calculations. High-delta dimensions flagged in match proposal."
  }
}
```

---

### Probability Band Output Schema

```json
{
  "probability_band": {
    "computation_id": "pb-{uuid}",
    "computation_date": "ISO-8601",
    "stp_seal": "SHA256:{seal_hash}",
    "node_a_stage": 3,
    "node_b_stage": 3,
    "point_estimate": 0.71,
    "confidence_interval": {
      "lower": 0.58,
      "upper": 0.83
    },
    "base_rate": 0.39,
    "signal_lift": 0.32,
    "signal_category": "STRONG",
    "routing_decision": "PROPOSE",
    "cultural_parameters_applied": ["US_base_v2.1", "JP_base_v1.2"],
    "top_alignment_dimensions": ["communication.conflict_style", "values.hierarchy", "attachment.primary_style"],
    "notable_divergence_dimensions": ["lifestyle.social_energy", "lifestyle.daily_rhythm"],
    "divergence_interpretation": "Social energy and daily rhythm divergence — potentially complementary but should be surfaced in proposal",
    "interaction_gap_declaration": "This score reflects pattern overlap between individual profiles. It cannot account for the interaction dynamics that will emerge when these two people actually engage. It is signal, not guarantee."
  }
}
```

---

### Cultural Parameter Block Schema

```json
{
  "cultural_parameter_block": {
    "culture_code": "JP",
    "parameter_version": "JP_base_v1.2",
    "last_updated": "ISO-8601",
    "source": "Hofstede_JP + GLOBE_JP + community_contributions_v3",
    "contribution_count": 47,
    "parameters": {
      "communication_context": "high_context",
      "directness_norm": 0.35,
      "emotional_expression_norm": 0.42,
      "silence_tolerance": 0.78,
      "conflict_expression_style": "indirect",
      "family_involvement_weight": 0.82,
      "age_role_sensitivity": 0.71,
      "gender_role_flexibility": 0.55,
      "first_meeting_formality": 0.79,
      "gift_giving_significance": 0.68
    },
    "complementarity_adjustments": {
      "directness_differential_tolerance": 0.25,
      "emotional_expression_complementarity": "high_benefits_measured"
    },
    "community_notes": "High-context communication norm means directness scoring requires downward adjustment for JP profiles. Silence in conversation is not withdrawal — it is processing."
  }
}
```

---

## 🔌 API Surface

| Endpoint | Method | Auth | Description |
|----------|--------|------|-------------|
| `/v1/node/session` | POST | Device key | Submit conversation session for pattern analysis |
| `/v1/node/status` | GET | Device key | Query node status + confidence score |
| `/v1/pattern/generate` | POST | Device key | Generate and STP-seal Pattern File for current stage |
| `/v1/pattern/delta` | POST | Device key | Compute Stage Delta between two sealed Pattern Files |
| `/v1/pattern/export` | POST | Device key + user confirm | Export sealed Pattern File for matching upload |
| `/v1/match/upload` | POST | User token | Upload sealed Pattern File to matching network |
| `/v1/match/preference` | POST | User token | Submit Partner Preference Declaration |
| `/v1/match/cultural` | POST | User token | Submit Cultural Context input |
| `/v1/match/proposals` | GET | User token | Retrieve active match proposals with P-band outputs |
| `/v1/match/decision` | POST | User token | Submit Connect / Pass decision on proposal |
| `/v1/match/hold` | GET | User token | Query MATCH HOLD status and queue position |
| `/v1/rds/report` | GET | Partner token | Retrieve population RDS metrics (partners only) |
| `/v1/stp/seal` | POST | Device key | Cryptographically seal any event record |
| `/v1/stp/verify` | GET | Public | Verify STP seal integrity |
| `/v1/mirror/session` | POST | Device key + consent flag | Submit Mirror Protocol session |
| `/v1/nudge/status` | GET | Device key | Query Connection Nudge engagement metrics |
| `/v1/cultural/contribute` | POST | User token | Submit cultural context contribution |
| `/v1/floppy/config` | POST | Device key + Adv. tier | Submit AI Floppy configuration |
| `/v1/floppy/divergence` | GET | Device key + Adv. tier | Retrieve stated vs. revealed preference divergence |

---

## 🔐 Security & Sovereignty Model

**Data residency principles:**

| Data Type | Primary Location | Server Access | Retention |
|-----------|-----------------|---------------|-----------|
| Conversation history | Device only | Never | User-controlled |
| Pattern File (raw) | Device only | Temporary (matching only) | User-controlled |
| Stage Delta records | Device only | Never | User-controlled |
| Mirror Protocol sessions | Device only | Never | User-controlled |
| STP seals | Device (primary), server (event log) | Hash only | Permanent |
| P-band output | Server (30 days) | Yes — no PII | 30 days then purge |
| Match decisions | Server (anonymized) | Anonymized only | Aggregate for RDS |
| Cultural contributions | Server (anonymized) | Yes | Permanent (anonymous) |

**Encryption:**
- All local storage: AES-256 at rest
- All transmission: TLS 1.3 minimum
- Pattern File export: Encrypted + signed before upload
- Matching computation: Zero-knowledge protocol where computationally feasible

**What HEART-MESH will never do:**
- Sell Pattern File data to third parties
- Use conversation history for advertising targeting
- Share individual behavioral profiles with governments
- Retain Pattern Files on servers after matching computation completes
- Apply RDS scoring to individual users
- Override user deal-breakers

---

## 📚 Free Data Strategy

The engine bootstraps on freely available, validated research before any proprietary data exists.

**Training corpus (Phase 1):**

| Dataset | Behavioral Signal | Access |
|---------|-----------------|--------|
| Big Five (BFI-44, IPIP-NEO) | Personality dimensions — openness, conscientiousness, extraversion, agreeableness, neuroticism | Public domain |
| ECR-R | Attachment anxiety and avoidance dimensions | Free for research use |
| Gottman Institute published research | Positive/negative interaction ratios, repair strategy taxonomy, conflict style categories | Academic publication access |
| MBTI behavioral literature | Communication and cognitive style taxonomy (used as input features, not output labels) | Public literature |
| Dyadic Adjustment Scale (DAS-7) | Relationship satisfaction measurement — ground truth for outcome validation | Free for research |
| Cross-cultural relationship meta-analyses | Cultural variation in compatibility predictors | Academic access |
| OkCupid 2016 anonymized public dataset | Real-world match + outcome signals at scale | Public release |

**Transition to proprietary data (Phase 2+):**
User conversation data (consented, anonymized) begins supplementing the training corpus. The engine learns from real HEART-MESH interactions, which improves the extraction pipeline specifically for the conversational context of the platform.

---

## 🕳️ The Interaction Pattern Gap — Declared

*This section appears in the spec because it must. It is not a limitation to be engineered around. It is a truth to be declared.*

Gottman's foundational research identified that the most reliable predictor of relationship success is the interaction pattern between two specific people — specifically, the ratio of positive to negative interactions in their shared context. This is not a property of either individual. It is an emergent property of the pair.

HEART-MESH v3.1 cannot generate this signal pre-match. The engine assesses individuals and computes pattern overlap. What actually happens when two people interact is only observable after they interact.

This is not a failure of the engine. It is the structural ceiling of any individual-assessment-based matching system.

**What the engine does:** Reduces the probability of entering interactions that are structurally likely to produce poor outcomes.

**What the engine cannot do:** Guarantee that two well-matched profiles will produce a good interaction. Cannot predict the emergent chemistry, timing sensitivity, or contextual variables that no profile can capture.

**How this is handled in the product:**
- The interaction gap declaration appears in the probability band output (see schema above)
- The match proposal UI explicitly names it: *"This score reflects pattern overlap. What happens when you actually talk is the real test."*
- Post-match feedback collection begins as soon as both users confirm contact — this interaction data is the most valuable data the platform will ever generate

---

## 🛠️ MVP Build Sequence

**Build nothing before validating the extraction pipeline.**

```
PHASE 0 — VALIDATION (Months 1–3)
─────────────────────────────────────────
Target: Prove the extraction pipeline produces pattern scores
        that correlate with gold-standard instruments at r ≥ 0.50.

Build:
  • Personality AI Engine (M1) — minimal viable version
  • Pattern Extraction Pipeline (M2) — core dimensions only
  • Psychometric validation test harness

Test:
  • 50 volunteer users, 10+ sessions each
  • Administer Big Five + ECR-R → compare to extracted Pattern File
  • If r ≥ 0.50: proceed to Phase 1
  • If r < 0.50: extraction pipeline requires fundamental revision

Do NOT build:
  • Matching network
  • P-band calculator
  • Any matching UI
  • Cultural database (seed only)

─────────────────────────────────────────
PHASE 1 — MVP (Months 3–9)
─────────────────────────────────────────
Phase 0 gate passed.

Build:
  • Companion App (F1) — offline-first, full feature
  • Pattern File Viewer (F2)
  • Stage Delta Engine (M3)
  • STP Sealing Service (B1) — local seals
  • Cultural Database seed (B3) — Phase 1 data pre-loaded
  • AI Floppy Studio (F4) — basic configuration

Defer:
  • Matching network (requires user base)
  • Mirror Protocol (requires safety testing)
  • RDS (requires match network)
  • P-band calculator (requires cultural DB maturity)

─────────────────────────────────────────
PHASE 2 — PILOT (Months 9–18)
─────────────────────────────────────────
Build:
  • Match Portal (F3)
  • Probabilistic Band Calculator (M4)
  • Cultural Parameterization Layer (M5) — active
  • Match Router (M6)
  • Matching Network (B5)
  • Cultural crowdsource system (B3)

Pilot: N = 100–500 users
Collect: Ground truth outcome data (longevity, satisfaction)
Validate: P-band signal lift against actual outcomes

─────────────────────────────────────────
PHASE 3 — NETWORK (Months 18–30)
─────────────────────────────────────────
Build:
  • Mirror Protocol (F5 + M7) — safety-tested
  • Connection Nudge Protocol (M8)
  • RDS Engine (B2)
  • NICE / Government partnership integration

─────────────────────────────────────────
PHASE 4 — SCALE (Year 3+)
─────────────────────────────────────────
  • National deployment
  • Multi-language support
  • Multi-cultural parameter expansion
  • Academic partnership for outcomes publication
  • International expansion
```

---

## 🗺️ Implementation Roadmap

| Phase | Timeline | Key Milestone | Gate Criterion |
|-------|---------|--------------|----------------|
| Phase 0 — Validation | Months 1–3 | Extraction pipeline validated | r ≥ 0.50 vs. gold-standard instruments |
| Phase 1 — MVP | Months 3–9 | Companion App live, Stage seals working | 100+ users with Stage 1 seals |
| Phase 2 — Pilot | Months 9–18 | Matching network live, P-band active | Signal lift > +0.10 above base rate confirmed |
| Phase 3 — Network | Months 18–30 | Mirror Protocol live, RDS reporting, NICE integration | Phase 2 outcome data published |
| Phase 4 — Scale | Year 3+ | National deployment | Phase 3 adverse event rate < 2% |

---

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
HEART-MESH v3.1 — 「心网」— The Mesh That Connects
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
DSAP v1.1 AUDITED | FORGE v1.0 INFORMED | MYCELIUM v2.0 BACKBONE
FSVE v4.0 SCORING | STP v1.0 SEALED | ORCID: 0009-0005-8057-5115
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
"Every pattern verified. Every match sealed. The interaction is still yours."
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Version: 3.1.0 | Date: April 2026 | Status: SPEC COMPLETE — BUILD READY
Supersedes: HEART-MESH v3.0 | Authors: Sheldon K. Salmon & ALBEDO
```
