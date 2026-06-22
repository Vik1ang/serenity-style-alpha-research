# Skill Information Architecture Cleanup Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Reduce runtime context and reference ambiguity without changing structural alpha research gates, buckets, or trading-scenario behavior.

**Architecture:** Keep `skills/structural-alpha-research/` limited to runtime instructions and task-loaded research references. Move benchmark candidates, action planning, and peer-discussion provenance into `docs/decisions/competitive-benchmark-2026-06-08/`. Compress the canonical `SKILL.md` into a routing-first entry while preserving all mandatory gates and synchronize the Codex mirror.

**Tech Stack:** Markdown, Git, Python structural assertions, shell link/hash checks.

---

### Task 1: Lock Existing Runtime Behavior

**Files:**
- Read: `skills/structural-alpha-research/SKILL.md`
- Test: `/tmp/structural alpha-skill-regression.py`

- [ ] Record assertions for frontmatter, Chinese output, demand/bottleneck gates, materiality thresholds, three buckets, watchlist upgrade, red flags, evidence hierarchy, reasoning sequence, trading states, conclusion states, scope, and R9/R10 routing.
- [ ] Run the assertions against the current canonical skill and require PASS before editing.

### Task 2: Separate Runtime References From Decision Provenance

**Files:**
- Move: `skills/structural-alpha-research/references/candidates-*.md`
- Move: `skills/structural-alpha-research/references/competitive-benchmark-action-plan.md`
- Create: `docs/decisions/competitive-benchmark-2026-06-08/README.md`

- [ ] Move all seven benchmark/candidate/debate files into one dated decision directory.
- [ ] Update internal links to remain valid within the new directory.
- [ ] Mark the action plan as canonical backlog and the remaining files as evidence/provenance, not runtime skill inputs.

### Task 3: Slim the Canonical Runtime Entry

**Files:**
- Modify: `skills/structural-alpha-research/SKILL.md`

- [ ] Remove maintenance candidates/action-plan links from the runtime index.
- [ ] Consolidate repeated purpose, workflow, gate, output, and reference text.
- [ ] Preserve all behavior assertions and keep the file near 120–160 lines.

### Task 4: Update Human and Agent Entry Documents

**Files:**
- Modify: `README.md`
- Modify: `AGENTS.md`
- Modify: `CLAUDE.md`
- Modify: `GEMINI.md`
- Modify: `docs/agent-integration.md`
- Modify: `.codex/skills/structural-alpha-research/SKILL.md`

- [ ] Keep top-level indexes runtime-only.
- [ ] Add the decision archive under maintenance documentation, not skill loading instructions.
- [ ] Route A-share tasks to R4/R5/R6 plus conditional R9/R10.
- [ ] Synchronize the Codex mirror from canonical files.

### Task 5: Verify and Commit

**Files:**
- Verify all changed and moved files.

- [ ] Run runtime behavior assertions against canonical and mirror.
- [ ] Verify Markdown paths, headings, frontmatter, and canonical/mirror identity.
- [ ] Confirm no R4/R5/R6/R9/R10 content changed.
- [ ] Run `git diff --check`, inspect the diff, and create one Lore-format commit.
