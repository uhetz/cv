# CV Repository Agent Guidelines (`uhetz/cv`)

This repository hosts the static English and German CV/Lebenslauf for **Hermann Hetzel** on GitHub Pages (`https://uhetz.github.io/cv/`).

## Files & Synchronization
- `index.html`: English version (`lang="en"`), hosted at `/cv/`.
- `de.html`: German version (`lang="de"`), hosted at `/cv/de.html`.
- `style.css`: Shared stylesheet for web (Light/Dark theme) and PDF/Print output (`@media print`).
- **Rule**: Whenever content, structure, or styling changes in one language file (`index.html` or `de.html`), keep the other language file synchronized unless instructed otherwise.

## 3-Page Print / PDF Layout (`@media print`)
The CV is strictly structured to print cleanly onto **3 pages** (A4 / Letter) when using **Save PDF** (`window.print()`):

1. **Page 1 — Overview**:
   - Header & Contact links (`#cv-header`)
   - Summary / Profil (`#summary`)
   - Technical Skills / Technische Kenntnisse (`#skills`)
   - Languages / Sprachen (`#languages`)
2. **Page 2 — Professional Experience**:
   - Starts with `.print-page-break` (`break-before: page`) on `#experience`.
   - Lists roles in reverse-chronological order (BSH Home Appliances Group, e:fs TechHub GmbH, Klinikum rechts der Isar).
   - Within BSH, domain sub-bullets stay strictly chronological (Ovens Domain, then Fully Automatic Coffee Machines).
   - Older/role-specific technologies (Java, Spring Boot, OpenSearch, Kubernetes, TS/JS, Pandas, VBA, D3.js) stay in the `Tech:` line of each role rather than in the main Technical Skills section.
3. **Page 3 — Hackathons, Projects & Education**:
   - Starts with `.print-page-break` (`break-before: page`) on `#hackathons`.
   - Includes:
     - **Hackathons & Competitions** (`#hackathons`): Concise 1-line descriptions, official/news recap links on event titles, and award badges (`1st Place`, `Rocket Science Category Winner`) placed to the **right** of `.organization`.
     - **Selected Projects** (`#projects`): 2-column grid in print (`.projects-grid { grid-template-columns: 1fr 1fr }`) featuring `Target Hardware Test Automation & Claude Skill` and `dotfiles`.
     - **Education** (`#education`): IU Internationale Hochschule (B.Sc. Business Informatics) and Tyumen State University.
   - **Rule**: Keep descriptions on Page 3 concise (1 line per item) and `.role { display: inline; }` so all three sections fit on Page 3 without spilling onto a 4th page.

## Content & Tone Guidelines
- **Direct, technical, non-buzzy**: Avoid corporate buzzwords or inflated claims (e.g., use `"bugs"` instead of `"defects"`; do not claim OS/platform/container architecture ownership when tools like Docker or TinyOS are simply used for development).
- **Core focus**: Highlight delivering reliable embedded C++ software fast on Linux and leveraging AI-assisted workflows (such as Claude skills) to shorten time-to-market (TTM) for software components.
- **Active skills only**: Keep the main `#skills` section focused on active core tools (`C++`, `Python`, `Bash`, `C`, `Linux`, `POSIX`, `Docker`, `TinyOS`, `CMake`, `Neovim`, `Git`, `CI/CD`, `GDB`).

## Workflow Rules
- **Do not push automatically**: Always apply and review edits locally first. Only commit and `git push` when the user explicitly confirms to publish.
- **Step-by-step confirmation**: When making multi-step updates, confirm each step with the user before moving to the next.
