# AI Growth Specialist Home Assignment — Submission Package

**Applicant**: Daniel Manzela  
**Target Project**: HumanizerCo  
**Live Production URL**: [https://humanizerco.web.app](https://humanizerco.web.app) / [https://manzela.github.io/HumanizerCo/](https://manzela.github.io/HumanizerCo/)  
**GitHub Repository**: [https://github.com/Manzela/HumanizerCo](https://github.com/Manzela/HumanizerCo)  

---

## Assignment #1: LP Conversion Optimization for HumanizerCo

### Deliverable #1: Strategic Design & Conversion Rationale (1-Page Summary)

#### 1. Strategic Concept & Positioning
HumanizerCo enters the competitive AI text transformation market targeting high-intent Google Search traffic (`"free ai humanizer"`). Because the brand has zero initial equity or domain authority, the landing page is engineered around **Instant Value Demonstration (Taste-Then-Gate)**. Rather than forcing users to register before testing the product, users receive an immediate, zero-friction interactive demo upon arrival.

#### 2. Visual Hierarchy & Above-The-Fold Layout
* **Fold Engineering (1280×720 & Mobile)**: Designed using CSS Grid (`grid-template-areas`) ensuring the input panel, output transformation window, and primary CTA are 100% visible above the fold without forced vertical scrolling.
* **Color Psychology & Action Hierarchy**: Utilizes an enterprise dark/light slate palette (`#0B1220` ink) paired with a high-contrast Indigo action accent (`#4F46E5`, 6.3:1 AA contrast). Semantic green (`#16A34A`) is strictly reserved for "Safe / 100% Human" status indicators.
* **Zero Emoji Standard**: Replaced amateur emoji icons with clean, inline vector SVGs (lock, shield, checkmark, wave) to convey enterprise-grade security and reliability.

#### 3. Copy & Friction Reduction Strategy
* **Headline**: *"Free AI Humanizer — Make Your AI Text Sound 100% Human"* matches exact search intent while establishing clear value.
* **Privacy Guarantee**: Highlighting *"Processed entirely in your browser — text is never uploaded"* addresses enterprise and academic data leakage concerns upfront.
* **Progressive Gating (250-Word Allowance)**: Users can process up to 250 words instantly in Basic mode. Accessing Strong mode or expanding beyond 250 words triggers a sleek, dismissible auth modal (`Google One-Click SSO` and `Email Signup`), capturing user intent at peak motivation.

#### Deliverable #2: Functional HTML Application
* Live Baseline LP: [index.html](https://humanizerco.web.app/index.html)

---

## Assignment #2: A/B Test Ideation for HumanizerCo

### Deliverable #1: Test Hypotheses & KPI Framework

#### Test 1: Problem-Centric vs. Baseline Headline (Variant 1)
* **Hypothesis**: Replacing generic benefit copy with explicit detector-bypass messaging (*"Bypass AI Detectors Instantly — Make Your Text 100% Undetectable"*) directly targets academic and professional pain points, increasing signup intent.
* **Target KPIs**: **Primary**: Signup CVR ($\frac{\text{Signups}}{\text{Page Visits}}$). **Secondary**: Humanize Button CTR, Gate Modal Conversion Rate.
* **Functional Variant**: [variant1.html](https://humanizerco.web.app/variant1.html)

#### Test 2: 100-Word vs. 250-Word Free Allowance Gate Threshold (Variant 2)
* **Hypothesis**: Lowering the free trial threshold from 250 words to 100 words increases gate modal trigger frequency, testing whether tighter usage boundaries drive higher signup velocity without increasing bounce rates.
* **Target KPIs**: **Primary**: Signup CVR. **Secondary**: Gate View Rate, Gate Dismissal Rate.
* **Functional Variant**: [variant2.html](https://humanizerco.web.app/variant2.html)

#### Test 3: Social Proof & Detector Compatibility Strip (Variant 3)
* **Hypothesis**: Displaying explicit compatibility badges (*Turnitin, GPTZero, Originality.ai, CopyLeaks*) directly above the hero tool builds immediate credibility for cold ad traffic, reducing bounce rate and boosting signup conversion.
* **Target KPIs**: **Primary**: Signup CVR. **Secondary**: Scroll Depth, Session Duration.
* **Functional Variant**: [variant3.html](https://humanizerco.web.app/variant3.html)

---

## Assignment #3: Creative Design Challenge

### Deliverable #1: Ad Creative Strategy & Concepts

#### Creative 1: 320px × 50px Mobile Leaderboard Banner
* **Rationale**: Designed for ultra-compact mobile ad placements. Features high-contrast dark indigo backdrop, concise bold copy (*"Bypass AI Detectors Instantly"*), and an explicit green verification badge to drive immediate tap-through CTR from mobile readers.

#### Creative 2: 250px × 250px Square Display Banner
* **Rationale**: Optimized for sidebar and inline content placements. Displays a visual before/after score gauge graphic (50% AI $\rightarrow$ 100% Human) proving functional efficacy, paired with a prominent indigo CTA button (*"Humanize Text Free"*).

#### Creative 3: 1080px × 1920px Full-Screen Vertical Story Ad
* **Rationale**: Engineered for full-screen vertical social and mobile channels (Instagram Stories, TikTok, Mobile Apps). Features a high-fidelity mockup of the HumanizerCo mobile interface in action, demonstrating 1-click text transformation with an intuitive swipe-up action prompt.

#### Deliverable #2: Generated Creative Assets
* Assets saved in repository under `docs/screenshots/ad_creatives/`.

---

## AI Work Transcripts & SDLC Transparency

In accordance with submission requirements, all AI pairing transcripts, trajectory logs, and agent execution paths have been compiled and exported.

* **GitHub Repository Workspace**: [https://github.com/Manzela/HumanizerCo](https://github.com/Manzela/HumanizerCo)
* **Local Agent Trajectory Logs**: Stored under `.system_generated/logs/transcript.jsonl`.
