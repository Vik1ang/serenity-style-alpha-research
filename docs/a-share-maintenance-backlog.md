# A-share Skill Maintenance Backlog

This document tracks known follow-ups for the A-share extension of
`structural-alpha-research`. These items are not blockers for current manual
research use, but should be addressed before treating the A-share stack as a
production-grade skill workflow.

## Current Status

The A-share spec stack is usable for manual thesis-level research. It includes:

- D4 final index: `references/a-share-skill-spec-FINAL.md`
- D3 draft / R4-R6 index: `references/a-share-skill-spec-draft.md`
- R4 thesis-level bucketing and announcement calibration
- R5 M&A/new-vehicle layering and company-level financial/governance red flags
- R6 market-structure evidence and R2/R3 risk pricing

Pressure-tested cases:

- 春秋电子 — company denial + multi-thesis split
- 鹏鼎控股 — real revenue but low materiality + large-cap crowding
- 黄河旋风 — loss-making small/mid cap + AI cooling narrative + financial red flags

## Backlog

### 1. Create an A-share output template

**Priority:** high  
**Target file:** `references/a-share-output-template.md`

The current A-share stack is methodology-heavy. It still lacks a fixed output
shape for actual research runs. Add a template covering:

- thesis-level table
- policy/cycle stage
- diffusion stage
- re-rating path
- R2/R3 market-structure evidence
- announcement counter-evidence level
- company-level red-flag threshold table
- missing checkpoints
- final bucket and confidence

Do this before wider repeated use, so future runs do not drift in format.

### 2. Build an announcement counter-evidence sample library

**Priority:** high  
**Target file:** `references/a-share-announcement-counterevidence-samples.md`

R4 defines six levels of announcement counter-evidence, but the levels need
sample calibration. Build a 10-20 case library from 巨潮 / 上交所 / 深交所
announcements, with each sample mapped to:

- exact announcement wording
- target thesis
- Level 1-6 classification
- bucket decision
- later verification outcome, if available

This reduces false positives when distinguishing template cooling from real
company denial.

### 3. Rename or redirect the R5 file

**Priority:** medium  
**Current file:** `references/a-share-r5-ma-target-layering-smallcap-redflags.md`

The R5 file name still says `smallcap-redflags`, but the content now covers
company-level financial/governance red flags across all market-cap sizes.

Preferred future name:

`references/a-share-r5-ma-vehicle-layering-company-redflags.md`

If renamed, update every reference in:

- `SKILL.md`
- `README.md`
- `CLAUDE.md`
- `references/a-share-skill-spec-FINAL.md`
- `references/a-share-skill-spec-draft.md`

If compatibility matters, keep the old file as a redirect note instead of
silently deleting it.

### 4. Split the large R1 source file

**Priority:** medium  
**Current file:** `references/a-share-4-pillars-spec.md`

This file is intentionally preserved as provenance, but it mixes session prompt,
raw generated spec, overview, and self-review. For cleaner maintenance, split it
into:

- `references/a-share-4-pillars-spec-clean.md` — clean R1 four-pillar spec only
- `references/a-share-4-pillars-session-log.md` — prompt/session provenance

Then update D4 and README/CLAUDE references. Do not do this unless there is time
to verify links, because the current large file is stable and not a runtime
blocker.

### 5. Decide whether A-share methodology should enter SKILL.md body

**Priority:** medium  
**Current state:** SKILL.md links to A-share references but does not inline the
A-share workflow.

This is intentional for token control. Before changing it, test whether agents
actually load `a-share-skill-spec-FINAL.md` when asked to run A-share names. If
not, add a short A-share trigger paragraph to SKILL.md, but do not inline R4/R5/R6
rules.

### 6. Add production-readiness verification prompts

**Priority:** low  
**Target file:** optional under `docs/` or `references/`

Create 3-5 standard pressure-test prompts for regression checks:

- company denial / multi-thesis split
- real revenue but low materiality
- loss-making small cap + financial red flags
- M&A/new business vehicle optionality
- large-cap crowding vs small-cap relay

Use these to check future edits do not weaken core rules.

## Do Not Do Yet

- Do not add package/build tooling; this is still a Markdown skill package.
- Do not rename R5 without updating every link.
- Do not split `a-share-4-pillars-spec.md` without preserving provenance.
- Do not add new rating buckets beyond Shortlist / Watchlist — Early Optionality / Excluded.
