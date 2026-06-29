# HumanizerCo — Web Architecture & Technical Specification

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
Assignment 1/   Landing page — the self-contained application (index.html) + reasoning write-up
Assignment 2/   A/B test variants (variant1–3.html) + reasoning write-up
Assignment 3/   Ad creatives (ad_creatives/*.png) + reasoning write-up
docs/           Reference screenshots
```

The runnable application is the single, self-contained document at `Assignment 1/index.html`. Hosting configuration (`firebase.json`, `.firebaserc`) and governance files (`CONTRIBUTING.md`, `SECURITY.md`, `CODE_OF_CONDUCT.md`, `LICENSE`) live at the repository root.

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

