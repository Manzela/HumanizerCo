# Contributing to HumanizerCo

Thank you for your interest in contributing to HumanizerCo! We welcome contributions from developers of all skill levels. This document outlines the process and standards for submitting changes to this repository.

---

## Technical Architecture

HumanizerCo is implemented as a standalone zero-dependency web application contained within `index.html`. All core modules—including engine transformation pipelines, lexical substitution maps, statistical scoring heuristics, and WCAG accessibility features—reside within this file.

Key design constraints:
* **Zero External Dependencies**: Production builds must run entirely within standard browser APIs without external NPM packages or remote CDN assets.
* **Client-Side Execution**: No user text data may be transmitted to external servers.
* **Browser Compatibility**: Code must run consistently across all modern evergreen browsers (Chrome, Safari, Firefox, Edge).

---

## Development Workflow

### 1. Setting Up Your Environment

Fork the repository on GitHub and clone your fork locally:

```bash
git clone https://github.com/<your-username>/HumanizerCo.git
cd HumanizerCo
```

### 2. Running Locally

Because HumanizerCo is a single-page client-side application, you can serve it locally using any standard static HTTP server:

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000` in your web browser to test your changes.

### 3. Making Changes

* Create a topic branch from `main`: `git checkout -b feature/my-new-feature`
* Ensure code modifications strictly maintain accessibility standards (WCAG 2.2 AA) and dynamic ARIA attributes.
* Verify that lexical substitutions maintain high grammatical accuracy and phonetic alignment.

### 4. Submitting Pull Requests

1. Commit your changes with clear, descriptive commit messages following the [Conventional Commits](https://www.conventionalcommits.org/) specification:
   * `feat: add new lexical variation rules`
   * `fix: correct mobile layout overflow`
   * `docs: update deployment instructions`
2. Push your topic branch to your fork on GitHub.
3. Submit a Pull Request targeting the `main` branch of `Manzela/HumanizerCo`.
4. Provide a clear summary of your changes and test verification in the PR description.

---

## Code Style & Standards

* Use standard 2-space indentation for HTML, CSS, and JavaScript.
* Maintain clean semantic HTML structures with appropriate landmarks (`header`, `main`, `footer`, `dialog`).
* Write clear, technical inline comments explaining complex algorithm choices or performance optimization rationale.
