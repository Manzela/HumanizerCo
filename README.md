# HumanizerCo — Web Architecture & Technical Specification

> This repository is a home assignment submission. It contains three growth tasks — a landing page, a set of A/B tests, and ad creatives — each in its own folder with the deliverables, a short write-up, and the raw AI session transcript behind it. The sections below document HumanizerCo as if it were a real product, which is the lens I used to approach the work. See [How I worked](#how-i-worked) for the process and [Repository Structure](#repository-structure) for the layout.

> **Live Application Website**: [https://humanizerco.web.app/](https://humanizerco.web.app/)

HumanizerCo is a lightweight, high-performance web application designed to rephrase and humanize machine-generated text. Operating entirely within the browser sandbox, the engine applies structural, syntactic, and lexical transformations to reduce predictability metrics commonly flagged by statistical AI detectors.

---

## Technical Overview

Modern AI text detectors rely on two primary metrics to identify machine-generated text:
1. **Perplexity**: A measurement of randomness and word-choice predictability.
2. **Burstiness**: Variations in sentence structure, clause length, and syntactic rhythm.

HumanizerCo implements a multi-stage text transformation engine that modifies text structure along both axes while preserving core semantic meaning.

### Architectural Guarantees

* **Zero-Network Client Execution**: Text transformations and scoring routines run completely client-side. User input is never transmitted to remote servers, providing total data privacy.
* **Zero-Dependency Production Build**: Built using standard Web APIs without external framework overhead or external bundle dependencies.
* **Deterministic Transformation Pipeline**: Implements safe, phonetically aware lexical replacements and clause restructuring to maintain grammatical accuracy.

---

## Core Engine Architecture

The core processing pipeline executes sequential transformations over input strings:

```
+------------------+     +-----------------------+     +-----------------------+     +--------------------+
|  Input Ingestion | --> |  Lexical Substitution | --> |  Clause Restructuring | --> | Phonetic Cleaning  |
+------------------+     +-----------------------+     +-----------------------+     +--------------------+
                                                                                                |
                                                                                                v
+------------------+     +-----------------------+                                   +--------------------+
| Unlocked Output  | <-- |  Access Gating Check  | <-------------------------------- | Scoring & Analysis |
+------------------+     +-----------------------+                                   +--------------------+
```

### Transformation Stages

1. **Lexical & Idiomatic Substitution**
   Replaces high-frequency statistical tokens and overused AI transition phrases with varied human equivalents based on selected intensity modes (`Basic` vs. `Strong`).

2. **Clause Restructuring (Burstiness Generation)**
   Analyzes complex sentence structures and applies targeted clause splitting and conjunction variation to inject natural rhythm variations.

3. **Phonetic & Indefinite Article Realignment**
   Performs context-aware post-processing on modified text to fix indefinite article agreements (e.g., correcting sound-based mismatches like *a hour* or *an university*).

4. **Statistical Score Estimation**
   Calculates an estimated human-similarity score using heuristic analysis of vocabulary distribution, sentence length variance, and structural markers.

---

## Operational Modes & Access Model

HumanizerCo provides two operational modes tailored to user needs:

| Mode | Target Use Case | Transformation Profile |
| :--- | :--- | :--- |
| **Basic** | Light editing & academic clarity | Subtle vocabulary shifts, structural cleanup, low risk of semantic drift. |
| **Strong** | Heavily templated, uniform text | Full sentence restructuring, wider synonym mapping, higher burstiness. |

### Access Control & Usage Limits

* **Free Tier Allowance**: Up to 250 words per execution in Basic mode without authentication.
* **Authentication Gating**: Accessing Strong mode or processing inputs over 250 words requires a free account.
* **Hard Limits**: System enforces a hard input cap of 20,000 words to ensure optimal browser performance during real-time processing.

---

## Performance & Accessibility

* **Accessibility (WCAG 2.2 AA)**: Built with native dynamic regions (`aria-live`), full keyboard focus trapping for modal dialogs, and minimum interactive target sizes (>=44px).
* **Motion & UX Constraints**: Respects operating system preferences (`prefers-reduced-motion`) to skip score animations when requested.
* **Analytics & Privacy**: Telemetry events strictly strip PII and raw text inputs prior to dispatch, ensuring compliance with data handling standards.

---

## Repository Structure

```text
Assignment 1/   index.html (the landing page) + Assignment-1-Deliverable-1.md (write-up)
Assignment 2/   variant1.html, variant2.html, variant3.html (A/B tests) + Assignment-2-Deliverable-1.md
Assignment 3/   ad_creatives/ (three PNG mockups) + Assignment-3-Deliverable-1.md
docs/           Reference screenshots
```

The work is split into three assignment folders, each holding its deliverables and a short write-up explaining the reasoning. Assignment 1 is the landing page itself — a single self-contained `index.html` that runs the full humanizer in the browser. Assignment 2 builds on that page with three A/B test variants, each changing one thing against the baseline so the result is measurable. Assignment 3 is the paid-acquisition layer: three ad creatives (a 320×50 banner, a 250×250 square, and a 1080×1920 full-screen mobile) sized to drive traffic to the landing page. Each folder also includes a `Claude Code/` subfolder with the raw AI session transcript for that assignment. Hosting configuration (`firebase.json`) and governance files (`CONTRIBUTING.md`, `SECURITY.md`, `CODE_OF_CONDUCT.md`, `LICENSE`) live at the repository root.

---

## How I worked

I work AI-assisted, and I built each assignment around a simple idea: decide everything before the model starts producing. For every task I first wrote and locked the full scope — the requirements, what counts as done, and the checks that prove it — and only then let the session run against that plan. Long AI sessions drift when you let them improvise; locking the scope upfront keeps the execution following the plan instead of the model's best guess halfway through.

That is why the session transcripts read the way they do. The short "Proceed" replies you'll see from me are sign-offs on a phase that already passed its checks, not me skimming and waving things through. The thinking happens earlier, when the scope is written and pressure-tested; the build phase is mostly enforcement.

I also treated the repository as if it were a real product rather than a test submission — hence the production README, the hosting setup, and the governance files. Internal build notes were cleaned out before publishing, the same way you'd prep any repo for release. The raw transcripts in each `Claude Code/` folder are the unedited record of how the work actually happened, kept exactly as they were so the reasoning is fully visible.

---

## Local Development & Deployment

The application is a single, self-contained HTML document — `Assignment 1/index.html`. No build step and no dependencies.

### Running Locally

Open the file directly:
```bash
open "Assignment 1/index.html"
```

Or serve over HTTP (recommended, so the clipboard and history APIs behave as in production):
```bash
python3 -m http.server 8000
# then visit http://localhost:8000/Assignment%201/
```

### Production Deployment

The live site is hosted on **Firebase Hosting** (project `humanizerco`, configured in `firebase.json`):

* **Live application**: [https://humanizerco.web.app/](https://humanizerco.web.app/)

Because the app is a single self-contained document, it runs on any static host that serves the HTML at its web root (Firebase Hosting, Cloudflare Pages, NGINX, etc.) — no compilation step is required.


---

## Open Source & Governance

HumanizerCo is maintained as an open-source project. We encourage community involvement, bug reports, and pull requests.

* **[Contributing Guidelines](CONTRIBUTING.md)**: Details on development workflow, code formatting, and pull request procedures.
* **[Security Policy](SECURITY.md)**: Information on vulnerability reporting and privacy guarantees.
* **[Code of Conduct](CODE_OF_CONDUCT.md)**: Standards for fostering an inclusive, welcoming community.
* **[License](LICENSE)**: Licensed under the MIT License.

