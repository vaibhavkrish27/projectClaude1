# CLAUDE.md — Rupali Marketing Analysis

## About this project

- Purpose: analyse the details and costing of products currently available across multiple e-commerce platforms.
- Deliverable: a comparative summary of **pricing** and **offers** across those platforms.
- Scope per run: the products, platforms, and time period are defined by the user in `inputs/` — never inferred.

## Project structure

| Folder | What goes here |
| --- | --- |
| `inputs/` | Source data provided by the user — product lists, platform links, raw exports, scraped price sheets. |
| `workflows/` | Repeatable steps and prompt/process definitions for how an analysis is run. |
| `output/` | Generated summaries, comparison tables, and final analysis outputs. |
| `resources/` | Reference material — templates, platform notes, glossaries, past benchmarks. |

- Read inputs from `inputs/`; write every generated artefact to `output/`.
- Do not create new top-level folders without asking first.

## Working rules (must follow)

### Ask, do not assume
- If anything is unclear or ambiguous, **stop and ask the user** before proceeding.
- Never fill a gap with an assumption — missing product names, platforms, dates, currencies, or units are always a question, not a guess.
- If a price, offer, or specification cannot be verified from the inputs, mark it as **"Not available"** rather than estimating.

### Confirm before changing
- Ask for explicit confirmation **before** creating, editing, deleting, or overwriting any file.
- Present the intended change first (what file, what content, why), then wait for approval.
- Confirm again before any step that is hard to reverse.

### Tone and style
- Tone: **formal and warm** — courteous, respectful, and clear.
- Prefer **bullet points over paragraphs**.
- Use tables for any side-by-side price or offer comparison.
- Keep language plain; spell out terms rather than using shorthand.

## Output expectations

- Every comparison should state: product, platform, listed price, discount/offer, effective price, and date checked.
- Always cite the source (platform name and link) for each data point.
- Flag clearly when data across platforms is not directly comparable (different pack size, variant, seller, or region).
