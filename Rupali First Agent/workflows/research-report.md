# Workflow: Research Report

**Purpose:** Take any topic the user gives, research it thoroughly, organise the findings, and produce a clean, structured Markdown report saved to `output/`.

**How to trigger:** The user says something like *"research \<topic\>"* or *"run the research-report workflow on \<topic\>"* — or just gives a topic.

---

## Default settings
- **Output format:** Markdown (`.md`)
- **Depth:** Standard — about 5–10 credible sources, key claims verified, a 1–2 page report.
- **Structure:** Standard template (see `resources/report-template.md`).

> The user can override depth by saying **"quick brief"** (3–5 sources, short) or **"deep dive"** (15+ sources, thorough). For a deep dive, use the built-in `deep-research` skill instead of the manual steps below.

---

## Steps

### Step 0 — Clarify (do this first)
Before researching, ask **up to 5 clarifying questions** to sharpen the topic. Good things to check:
- **Scope / angle** — how broad or narrow? Any specific sub-topic?
- **Audience / purpose** — who's it for, and what will it be used for? (decision, learning, a post, etc.)
- **Timeframe / region** — latest developments only? A specific country or market?

Skip this step only if the topic is already crystal clear and specific.

### Step 1 — Show the plan
Briefly list the sub-questions you'll answer and the angles you'll cover. Get a quick nod (or let the user tweak) before researching. *(Per the CLAUDE.md rule: show your plan before executing.)*

### Step 2 — Research
- Web-search for **5–10 credible, recent sources**. Prefer primary and authoritative ones (official sites, reputable publications, original research) over blogs or aggregators.
- For **every key fact**, note the source URL and its date.
- **Cross-check** any surprising, disputed, or high-stakes claim against a second independent source before trusting it.

### Step 3 — Organise
- Group findings into **themes**.
- Separate **facts** from **opinion / speculation / forecasts**.
- **Flag** anything uncertain, outdated, or where sources disagree.

### Step 4 — Write the report
- Fill in `resources/report-template.md`.
- **Bullets over paragraphs.** Clear, jargon-free, human, and detailed.
- Use inline citations `[1]`, `[2]`, … that map to the numbered **Sources** list at the bottom.

### Step 5 — Save & confirm
- Save to `output/` with the filename: **`YYYY-MM-DD-<topic-slug>.md`** (today's date + a short kebab-case topic name).
- Tell the user the exact saved file path and give a 2–3 line summary of what's inside.

---

## Quality checklist (before saving)
- [ ] Every key claim has a citation.
- [ ] Sources are credible and dated.
- [ ] Disagreements / uncertainties are flagged, not hidden.
- [ ] Report follows the template and is easy to skim.
- [ ] Language is plain and jargon-free.
