# {PREFIX}-{project-slug}

**Company/Domain:** {PREFIX} — {Company Name}
**myPKA stub:** `PKM/My-Life/Projects/{slug}.md`
**Goal:** {goal name}
**Status:** planning | active | paused | done

## What this is

{One paragraph: what this project produces and why it exists.}

---

## Folder activation guide

This repo ships with a universal base (always used) plus optional layers. **At project kickoff, delete the optional folders that don't apply — or leave them with `.gitkeep` if you expect to need them later.**

### Universal — keep for every project

| Folder | What goes here |
|---|---|
| `docs/` | Specs, requirements, decisions (ADRs), meeting notes, methodology |
| `inputs/` | Raw source material — **immutable once added** (client docs, source data, briefs) |
| `working/` | In-progress drafts, scratch work, intermediate files |
| `deliverables/` | Final outputs only — what leaves this project (reports, builds, exports) |
| `references/` | External material consulted but not produced here (research, competitor analysis, standards) |
| `scripts/` | Automation: build, deploy, data sync, export, migration — code that *runs* the project |

### Optional — activate by project type

| Folder | Activate when… | Delete when… |
|---|---|---|
| `00-admin/` | Project has contracts, SoW, invoices, NDAs | Personal/internal project with no engagement documents |
| `src/` | Project produces executable code (app, model, library) | Pure document project (tax planning, brand guide) |
| `assets/` | Project uses binary static files: logos, fonts, images | Code-only or document-only project |
| `config/` | Project needs environment config, Docker, Terraform, CI/CD | No deployment or environment config needed |
| `tests/` | Project has automated tests | No tests (document or analysis projects) |
| `data/` | Project processes structured data files (CSV, JSON, DB dumps) | No structured data inputs |
| `notebooks/` | Project uses Jupyter or exploratory notebooks | No notebook-based analysis |
| `models/` | Project trains or versions ML/statistical models | No machine-learning or trained models |

### Domain activation matrix

| Folder | Website | Full-stack app | Scripts / automation | Investment analysis | Tax planning | Brand work |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| `docs/` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `inputs/` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `working/` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `deliverables/` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `references/` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `scripts/` | ✓ | ✓ | ✓ | ✓ | — | — |
| `00-admin/` | — | — | — | maybe | ✓ | maybe |
| `src/` | ✓ | ✓ | ✓ | maybe | — | maybe |
| `assets/` | ✓ | ✓ | — | — | — | ✓ |
| `config/` | ✓ | ✓ | maybe | — | — | — |
| `tests/` | ✓ | ✓ | maybe | — | — | — |
| `data/` | — | maybe | maybe | ✓ | maybe | — |
| `notebooks/` | — | — | maybe | ✓ | — | — |
| `models/` | — | — | — | maybe | — | — |

---

## Naming conventions

- **Folders:** lowercase kebab-case. Exception: Python packages inside `src/` use underscores (import system requirement).
- **Deliverables / dated documents:** `YYYY-MM-DD-description.ext` — date prefix, no version suffix (git is the version history).
- **Binary deliverables** (PDFs, Word docs, design exports): single canonical filename + an entry in `CHANGELOG.md` for each revision. Never `report-v2-FINAL-FINAL.pdf`.
- **Ordered sub-folders** (when sequence matters): numeric prefix — `01-discovery/`, `02-strategy/`, `03-execution/`.
- **Archived material:** `_archive/` with leading underscore — sorts to bottom, signals "do not edit."

---

## Getting started

```bash
# Clone and remove optional folders that don't apply
git clone <repo-url>
cd <repo>
# Delete folders not relevant to this project type — see activation matrix above
rm -rf models notebooks   # example: for a brand project
```

---

## Related

- myPKA project stub: `PKM/My-Life/Projects/{slug}.md`
- myPKA task queue: `Team-Knowledge/tasks/INDEX.md` → By project → `{slug}`
- BKM company knowledge: `_JCDB/BKM/{company-folder}/`
