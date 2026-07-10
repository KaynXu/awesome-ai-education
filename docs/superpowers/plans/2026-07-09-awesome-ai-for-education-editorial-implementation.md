# Awesome AI for Education Editorial Field Guide Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rebuild the repository as a selective, bilingual, evidence-backed field guide for AI applications that improve educational practice.

**Architecture:** The English and Chinese READMEs form the navigation layer, organized by education workflow and editorial status. `docs/evidence.md` is the shared citation ledger, while criteria, contribution guidance, and GitHub forms enforce the same rules for future changes. A temporary Ruby verifier checks structure, bilingual parity, evidence coverage, cleanup, and form syntax without adding permanent automation.

**Tech Stack:** GitHub Flavored Markdown, GitHub issue-form YAML, Ruby 3 standard library, Node.js with `awesome-lint`, Git, GitHub CLI.

## Global Constraints

- Public title: `Awesome AI for Education`.
- Public promise: `A human-curated, evidence-backed field guide to AI that improves educational practice.`
- Boundary statement: `AI for education, not education about AI.`
- Keep `README.md` as the global entry point and mirror its scope, order, and decisions in `README.zh-CN.md`.
- Require human approval for every Main List entry.
- Keep open source as an independent layer, not a universal admission requirement.
- Exclude general AI-literacy courses and paper-only resources without a practical implementation.
- Label vendor-published evidence and place weak or early resources in Watchlist.
- Do not embed dynamic star counts or numeric editorial scores.
- Accept English-only submissions; maintainers own final bilingual parity.
- Keep `LICENSE` unchanged.
- Do not add a website, GitHub Pages scaffold, or new automation.
- Do not merge directly to `main`.
- Use ASCII punctuation in every changed file.

---

## File Map

- `README.md`: Canonical English field guide and project order.
- `README.zh-CN.md`: Chinese mirror with the same sections and resources.
- `docs/evidence.md`: Public evidence ledger.
- `docs/criteria.md`: Admission, movement, and removal policy.
- `docs/initial-curation-checklist.md`: Maintainer review checklist.
- `CONTRIBUTING.md`: Contributor-facing workflow.
- `.github/ISSUE_TEMPLATE/*.yml`: Structured project and case-study suggestions.
- `.github/pull_request_template.md`: Disclosure and review checklist.
- `metadata.json` and `llms.txt`: Remove unsupported discovery artifacts.
- `.verify-awesome-ai-education.rb`: Temporary proof script, deleted before commits finish.
- `handoff.md`: Ignored local project handoff, refreshed after substantive work.

---

### Task 1: Create The Temporary Acceptance Verifier

**Files:**
- Create temporarily: `.verify-awesome-ai-education.rb`

**Interfaces:**
- Consumes: Both READMEs, `docs/evidence.md`, issue-form YAML, and repository files.
- Produces: Exit code `0` only when all invariants pass; one `PASS:` or `FAIL:` line per assertion.

- [ ] **Step 1: Add exact assertions**

Use `apply_patch` to create a Ruby standard-library script with these constants:

```ruby
EXPECTED_H2 = ["Contents", "Teaching and Lesson Design", "Assessment and Feedback", "Tutoring and Learner Support", "Content and Curriculum", "School Operations and Governance", "Teacher Development and Coaching", "Open Source", "Field Evidence", "Watchlist", "How Curation Works", "Contributing"]
EXPECTED_PROJECTS = ["MagicSchool", "Eduaide", "Curipod", "Teachmate", "Brisk Teaching", "Gradescope", "Writable", "Khanmigo", "CENTURY Tech", "Flint", "Diffit", "SchoolAI", "Merlyn", "Edthena AI Coach", "Shiori", "Ottawa Catholic School Board + Brisk", "Barbers Hill ISD + Brisk", "Ysleta Middle School + Curipod", "Chalkie", "QuizVerse", "Kira Learning", "Cognii", "Nolej", "Mindsmith", "Google Learn About"]
EVIDENCE_PROJECTS = EXPECTED_PROJECTS.first(15) + EXPECTED_PROJECTS.last(7)
```

Implement `check(label, condition)`, `headings(markdown)`, and `project_names(markdown)`. Assert the title, promise, boundary, exact English H2 array, Chinese H2 count, exact ordered project parity, absence of `Tags:` and `Superhighway`, one `## Project Name` evidence heading for every evidence project, one `Last reviewed: 2026-07-09` per evidence record, safe YAML parsing for both forms, deletion of `metadata.json` and `llms.txt`, and absence of references to those filenames.

- [ ] **Step 2: Prove the old state fails**

Run `ruby .verify-awesome-ai-education.rb`.

Expected: Exit code `1`, including `FAIL: English title`, `FAIL: Ordered project parity`, and missing evidence-anchor failures.

- [ ] **Step 3: Keep the verifier untracked**

Run `git status --short`.

Expected: Only `?? .verify-awesome-ai-education.rb` appears.

---

### Task 2: Build The Evidence And Policy Layer

**Files:**
- Create: `docs/evidence.md`
- Modify: `docs/criteria.md`
- Modify: `docs/initial-curation-checklist.md`

**Interfaces:**
- Consumes: Evidence taxonomy and initial curation decisions from the design spec.
- Produces: Stable project headings, public sources, limitations, and review dates used by both READMEs.

- [ ] **Step 1: Write the evidence ledger**

Create `docs/evidence.md` with an introduction and one H2 record for each Main List, Open Source, and Watchlist resource. Use this exact record shape:

```markdown
## Project Name

- Primary: [Project Name](primary URL)
- Layer: Main List, Open Source, or Watchlist
- For: Target user and concrete education workflow
- Evidence: Independent evaluation, Public deployment, Vendor case study, Open source review, or Product documentation
- Sources: [Descriptive source name](direct URL)
- Editorial note: What the source establishes and what it does not establish.
- Last reviewed: 2026-07-09
```

Never call vendor-hosted claims independent. For Flint, state that the Learning Standard review does not establish learning impact. For Shiori, record its MIT license, setup, self-hosting path, and repository activity. For Watchlist records, name the missing independent evaluation, named deployment, or inspectable implementation.

- [ ] **Step 2: Rewrite editorial policy**

Replace `docs/criteria.md` with `Scope Boundary`, `Editorial Layers`, `Main List Requirements`, `Open Source Requirements`, `Field Evidence Requirements`, `Watchlist Requirements`, `Evidence Labels`, `Conflicts Of Interest`, `Review, Movement, And Removal`, and `Bilingual Merge Policy`. State human approval, the practical-education boundary, open source as a separate layer, and maintainer-owned translation.

- [ ] **Step 3: Rewrite the maintainer checklist**

Replace `docs/initial-curation-checklist.md` with checkboxes for scope, target user, workflow, AI role, primary URL, evidence ownership, disclosure, layer, duplicate check, link review, wording, English order, Chinese parity, and review date.

- [ ] **Step 4: Run focused proof**

Run `ruby .verify-awesome-ai-education.rb | tee /tmp/awesome-ai-education-evidence-proof.txt`.

Expected: Evidence-anchor and date checks pass. README and cleanup checks still fail.

- [ ] **Step 5: Commit**

Run `git add -f docs/evidence.md docs/criteria.md docs/initial-curation-checklist.md && git commit -m "docs: establish evidence-backed curation"`.

Expected: Commit succeeds; the verifier stays untracked.

---

### Task 3: Rewrite The English Field Guide

**Files:**
- Modify: `README.md`

**Interfaces:**
- Consumes: Evidence headings and labels from `docs/evidence.md`.
- Produces: Canonical section structure and project order for the Chinese mirror.

- [ ] **Step 1: Replace the first screen and contents**

Use the exact title, promise, boundary, language switcher, and trust line from the design spec. Keep the Awesome badge linked to `https://awesome.re`. Add all twelve H2 sections in the design order.

- [ ] **Step 2: Populate workflow sections**

Use this exact placement:

```text
Teaching and Lesson Design: MagicSchool, Eduaide, Curipod, Teachmate
Assessment and Feedback: Brisk Teaching, Gradescope, Writable
Tutoring and Learner Support: Khanmigo, CENTURY Tech, Flint
Content and Curriculum: Diffit
School Operations and Governance: SchoolAI, Merlyn
Teacher Development and Coaching: Edthena AI Coach
```

Write one sentence per entry naming workflow, target user, and strongest evidence type, linked to the evidence heading. Remove generic tags.

- [ ] **Step 3: Populate editorial layers**

Add Shiori under Open Source with MIT, self-hosting, and review facts. Add the three named Field Evidence records and label all three `Vendor-reported case study`. Add seven Watchlist resources with neutral monitoring reasons and evidence links.

- [ ] **Step 4: Explain curation and contribution**

Summarize the human-approval rule, evidence taxonomy, movement between layers, evidence ledger, and scope boundary. Link to contribution guidance, both issue forms, criteria, and evidence. Welcome English-only suggestions.

- [ ] **Step 5: Verify and commit**

Run `npx --yes awesome-lint README.md` and `ruby .verify-awesome-ai-education.rb | tee /tmp/awesome-ai-education-english-proof.txt`.

Expected: Awesome lint exits `0`; English, evidence, and removal checks pass; Chinese parity and artifact cleanup still fail.

Run `git add README.md && git commit -m "docs: rebuild English field guide"`.

---

### Task 4: Build The Chinese Mirror

**Files:**
- Modify: `README.zh-CN.md`

**Interfaces:**
- Consumes: Exact project order and section count from `README.md`.
- Produces: Chinese copy with identical scope and editorial decisions.

- [ ] **Step 1: Mirror structure and entries**

Use Chinese headings and descriptions but preserve the number and order of H2 sections, all 25 project names, public URLs, evidence links, and layer decisions. Use ASCII punctuation.

- [ ] **Step 2: Verify parity**

Run `ruby .verify-awesome-ai-education.rb | tee /tmp/awesome-ai-education-bilingual-proof.txt`.

Expected: `PASS: Chinese H2 count` and `PASS: Ordered project parity`; only cleanup checks may fail.

- [ ] **Step 3: Commit**

Run `git add README.zh-CN.md && git commit -m "docs: align Chinese editorial field guide"`.

---

### Task 5: Rebuild The Contribution Surface

**Files:**
- Modify: `CONTRIBUTING.md`
- Modify: `.github/ISSUE_TEMPLATE/suggest-project.yml`
- Modify: `.github/ISSUE_TEMPLATE/suggest-case-study.yml`
- Modify: `.github/pull_request_template.md`

**Interfaces:**
- Consumes: Layer names, evidence labels, human approval, disclosure, and bilingual policy.
- Produces: Complete submission data for human editorial decisions.

- [ ] **Step 1: Rewrite contributor guidance**

Explain the four layers, scope boundary, required evidence and disclosure, English-only acceptance, maintainer translation, entry style, and exact flow: `Suggestion -> scope screen -> evidence review -> layer decision -> human approval -> bilingual merge -> periodic review`.

- [ ] **Step 2: Rewrite both issue forms**

The project form requires name, primary URL, requested layer, target users, education workflow, AI role, evidence URL, access or open-source status, affiliation, and disclosure. The case form requires named setting, source URL, scale, participants, workflow, AI role, observed result, source owner, vendor-published status, affiliation, and disclosure. Use labels `submission:project` and `submission:case-study` respectively.

- [ ] **Step 3: Rewrite the pull request template**

Require layer, workflow, target users, evidence link and ownership, affiliation, changed files, link and scope checks, and acknowledgement that maintainers ensure bilingual parity.

- [ ] **Step 4: Parse, verify, and commit**

Run:

```bash
ruby -e 'require "yaml"; Dir[".github/ISSUE_TEMPLATE/*.yml"].sort.each { |f| YAML.safe_load_file(f, permitted_classes: [], aliases: false); puts "PASS: #{f}" }'
```

Expected: One `PASS:` line for each form.

Commit with `git add CONTRIBUTING.md .github/ISSUE_TEMPLATE .github/pull_request_template.md && git commit -m "docs: strengthen community contribution flow"`.

---

### Task 6: Remove Discovery Theater And Refresh Handoff

**Files:**
- Delete: `metadata.json`
- Delete: `llms.txt`
- Modify locally if present: `AGENTS.md`
- Modify locally if present: `handoff.md`

**Interfaces:**
- Consumes: Final repository structure.
- Produces: No misleading discovery artifacts and an accurate local handoff.

- [ ] **Step 1: Delete artifacts and stale references**

Delete both files with `apply_patch`. Search tracked text and remove claims that these files improve discovery.

- [ ] **Step 2: Refresh ignored local guidance**

If present, update `AGENTS.md` only for the new editorial direction. Rewrite `handoff.md` to current status, completed work, remaining publication step, risks, and workspace state.

- [ ] **Step 3: Run complete proof**

Run:

```bash
ruby .verify-awesome-ai-education.rb | tee /tmp/awesome-ai-education-final-proof.txt
npx --yes awesome-lint README.md
git diff --check
```

Expected: Every verifier line starts with `PASS:`; the other commands exit `0` without output.

- [ ] **Step 4: Remove verifier and commit cleanup**

Delete `.verify-awesome-ai-education.rb` with `apply_patch`. Run `test ! -e .verify-awesome-ai-education.rb && echo "PASS: temporary verifier removed"`.

Expected: `PASS: temporary verifier removed`.

Commit with `git add -u metadata.json llms.txt && git commit -m "chore: remove unsupported discovery artifacts"`.

---

### Task 7: Verify, Integrate, And Publish

**Files:**
- No additional tracked content files.

**Interfaces:**
- Consumes: Clean feature and `develop` branches.
- Produces: Remote `develop`, GitHub metadata and labels, and an unmerged pull request to `main`.

- [ ] **Step 1: Run clean-worktree proof**

Restore the verifier with `apply_patch`, run it and capture complete output, then delete it with `apply_patch`. Run `npx --yes awesome-lint README.md`, `git diff --check`, and `git status --short --branch`.

Expected: All checks pass and status shows only `## codex/editorial-field-guide`.

- [ ] **Step 2: Merge into develop and reverify**

From the primary worktree run `git switch develop` and `git merge --no-ff codex/editorial-field-guide -m "merge: evidence-backed editorial field guide"`. Repeat the temporary-script proof on `develop`.

Expected: Merge succeeds, proof passes, and `develop` is clean.

- [ ] **Step 3: Update the exact GitHub target**

Restate target `KaynXu/awesome-ai-education`. Update its description to the public promise and topics to `awesome-list`, `ai-in-education`, `education`, `edtech`, `educators`, `learning-design`, `assessment`, and `open-source`. Create or update labels `submission:project`, `submission:case-study`, `evidence-review`, and `watchlist`.

- [ ] **Step 4: Push and open the review boundary**

Push `develop` to origin. Open a pull request from `develop` to `main` summarizing positioning, curation, evidence ledger, bilingual parity, governance, cleanup, proof, and the unchanged MIT license. Do not merge it.

- [ ] **Step 5: Remove the completed worktree**

Run `git worktree remove .worktrees/editorial-field-guide`, `git branch -d codex/editorial-field-guide`, and `git worktree list`.

Expected: The feature worktree and local feature branch are gone; `develop` remains clean and active.
