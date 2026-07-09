# Awesome AI for Education Editorial Field Guide Design

## Objective

Transform `KaynXu/awesome-ai-education` from a generic bilingual tool directory into a human-curated, evidence-backed field guide for AI that improves educational practice.

The repository should become the clearest GitHub-native reference for educators, curriculum designers, school leaders, learning designers, and education operators who need to understand which AI applications are useful, how they are used, and what public evidence supports them.

The repository is about AI for education. It is not about courses that teach people how to use AI.

## Positioning

Public title:

```text
Awesome AI for Education
```

Public promise:

```text
A human-curated, evidence-backed field guide to AI that improves educational practice.
```

Boundary statement:

```text
AI for education, not education about AI.
```

The repository slug remains `awesome-ai-education` to preserve its existing URL, forks, and search history.

The English README remains the default global entry point. `README.zh-CN.md` mirrors its structure, scope, ordering, and editorial decisions.

## Editorial Principles

1. Human approval is required for every Main List entry. AI may discover candidates, gather sources, and draft text, but it may not approve an entry.
2. The Main List contains only resources with a concrete education workflow, a clear target user, and public evidence that can be inspected.
3. Popularity is not sufficient. A popular general AI product stays out unless its educational workflow is explicit and publicly documented.
4. Open source is an important independent layer, not the boundary of the whole repository.
5. Research papers are not list entries unless they are tied to a practical project, implementation, or product evidence record.
6. Vendor case studies are allowed only when clearly labeled as vendor-reported.
7. Weak, early, or self-reported resources belong in Watchlist until stronger evidence appears.
8. Entry order is editorial, not alphabetical. The most useful and best-supported resources appear first.
9. Contributors may submit in English only. Maintainers are responsible for final bilingual parity so language requirements do not block global participation.
10. The list stays selective. Removing a weak or stale entry is as valuable as adding a new one.

## README Information Architecture

The first screen contains only:

```markdown
# Awesome AI for Education [Awesome badge]

> A human-curated, evidence-backed field guide to AI that improves educational practice.

AI for education, not education about AI.

English | Chinese

Human-reviewed | Evidence-labeled | Bilingual
```

The first H2 section is `Contents` to remain compatible with official Awesome guidance.

The full section order is:

1. Contents
2. Teaching and Lesson Design
3. Assessment and Feedback
4. Tutoring and Learner Support
5. Content and Curriculum
6. School Operations and Governance
7. Teacher Development and Coaching
8. Open Source
9. Field Evidence
10. Watchlist
11. How Curation Works
12. Contributing

The first six content sections are organized by education workflow. `Open Source`, `Field Evidence`, and `Watchlist` are explicit editorial layers with different admission rules.

No project is duplicated across workflow sections. A project is placed where its strongest education workflow appears. Case-study links may mention a listed product again because the linked resource is the implementation evidence, not a duplicate product entry.

## Entry Format

Main List entries use one readable sentence with three fixed facts:

1. The education workflow.
2. The target user.
3. The strongest available evidence type.

English format:

```markdown
- [Project](https://example.com/) - Supports a specific education workflow and explains the practical value. For target users; [evidence label](docs/evidence.md#project-anchor).
```

Chinese format:

```markdown
- [Project](https://example.com/) - 支持明确的教育工作流, 并说明实际价值. 面向目标用户; [证据标签](docs/evidence.md#project-anchor).
```

Entries do not use generic marketing tags. Labels such as `AI`, `Platform`, `Workflow`, or `Engagement` do not help readers make decisions and are removed.

Open-source entries include inspectable repository facts:

```markdown
- [Project](https://github.com/owner/repo) - Supports a specific education workflow. For target users; open source; license; self-hostable when verified; [review record](docs/evidence.md#project-anchor).
```

Dynamic star counts are not embedded in README because they become stale and reward popularity over educational value.

Field Evidence entries name the setting and source type:

```markdown
- [Institution + Product](https://example.com/case-study) - Describes the implementation setting, workflow, and scale. Vendor-reported case study.
```

## Evidence Taxonomy

`docs/evidence.md` is the public evidence ledger and citation surface. Every Main List and Open Source entry has a matching record.

Evidence labels are descriptive, not scores:

- `Independent evaluation`: A non-vendor source reports methods and findings about the product or implementation.
- `Public deployment`: A named school, district, university, or education organization publicly describes real use.
- `Vendor case study`: A named implementation is documented by the vendor. This is useful but not independent.
- `Open source review`: Code, license, setup path, maintenance activity, and education workflow are inspectable.
- `Product documentation`: The workflow is supported only by official product documentation. This alone normally places a resource in Watchlist.

Each evidence record contains:

- Project name and primary URL.
- Current list layer.
- Target users and workflow.
- Strongest evidence label.
- Public source links.
- Editorial note describing what the evidence does and does not establish.
- Last reviewed date in `YYYY-MM-DD` format.

No numeric score is used. Numeric ratings would imply precision that the available evidence cannot support.

## Initial Curation Decisions

The initial rewrite prioritizes quality over expansion. It does not add a large batch of new products.

Main List candidates:

- MagicSchool
- Eduaide
- Curipod
- Teachmate
- SchoolAI
- Brisk Teaching
- Gradescope
- Writable
- Khanmigo
- CENTURY Tech
- Flint
- Diffit
- Merlyn
- Edthena AI Coach

Open Source:

- Shiori remains because the repository, MIT license, setup path, self-hosting option, and education workflow are inspectable.

Watchlist candidates:

- Chalkie
- QuizVerse
- Kira Learning
- Cognii
- Nolej
- Google Learn About
- Mindsmith

Field Evidence candidates:

- Ottawa Catholic School Board + Brisk
- Barbers Hill ISD + Brisk
- Ysleta Middle School + Curipod

Removal candidates:

- Superhighway EdTech Research Agent is removed because it supports market research and procurement intelligence rather than teaching, learning, assessment, curriculum, school operations, or educator development.
- Jessica Bryant + Eduaide is removed because the public source is unavailable and the existing entry does not provide a reviewable implementation record.

All final inclusion decisions are verified again immediately before editing.

## Contribution and Governance Flow

The contribution flow is:

```text
Suggestion -> scope screen -> evidence review -> layer decision -> human approval -> bilingual merge -> periodic review
```

Project suggestions require:

- Project name and primary public URL.
- Target users.
- Concrete education workflow.
- Explanation of how AI is applied.
- Best public evidence source.
- Access or open-source status.
- Submitter affiliation and self-promotion disclosure.

Case-study suggestions require:

- Named education setting.
- Implementation scale and participants.
- Education workflow.
- AI role.
- Observed result or operational change.
- Source owner and disclosure of whether the source is vendor-published.

Pull requests must state the layer requested: Main List, Open Source, Field Evidence, or Watchlist.

Maintainers may move a submission to a different layer, request stronger evidence, or decline it even when the project is functional.

The final merge must preserve English and Chinese README parity. Contributors are not required to translate their own submissions.

## GEO and SEO Strategy

Discoverability is built from useful primary content, not duplicated metadata files.

The strongest discovery assets are:

- A clear repository name, description, and GitHub topics.
- A concise first-screen promise using natural language.
- Workflow-first headings that match practitioner questions.
- Evidence records with original editorial notes and direct sources.
- Public contribution and review history.
- External references from projects, educators, newsletters, and the Awesome ecosystem.

`metadata.json` is removed because it is not a standard GitHub repository discovery surface and duplicates the README.

`llms.txt` is removed for now because the repository is not serving it at a website or sub-site root. A compliant `llms.txt` may return only when a real GitHub Pages or custom-domain site exists.

No website scaffold, GitHub Pages build, or new automation is added in this implementation. That remains a separate future project because the repository rules explicitly require separate authorization for website scaffolding and automation.

## Maintenance and Failure Handling

Entries are reviewed when any of these conditions occur:

- The primary link breaks or redirects to an unrelated product.
- The product is discontinued, acquired, or materially changes scope.
- The education workflow is no longer publicly visible.
- Evidence claims are withdrawn, contradicted, or become unverifiable.
- An open-source repository is archived, loses its license, or no longer has a usable setup path.
- A conflict of interest or undisclosed self-promotion is discovered.

The response is one of:

- Rewrite the entry with corrected claims.
- Move the entry to Watchlist.
- Move the entry from Watchlist to Main List after stronger evidence appears.
- Remove the entry.

Broken or contradictory evidence never remains silently attached to a Main List entry.

## Verification

The implementation must prove:

- `README.md` passes `awesome-lint`.
- English and Chinese README files have the same ordered H2 section structure.
- English and Chinese README files contain the same ordered project names.
- Every Main List and Open Source project has an anchor in `docs/evidence.md`.
- Every evidence record has a `Last reviewed` date.
- No duplicate external project URL appears across workflow sections.
- `metadata.json` and `llms.txt` are removed without leaving references.
- Superhighway EdTech Research Agent is absent from both READMEs.
- All Markdown links use valid syntax.
- `git diff --check` passes.
- The final worktree is clean after commits.

Proof is executed through a temporary verification script and its complete output is retained in the task report.

## Licensing Constraint

The current repository uses MIT and includes contributor-authored entries. Official Awesome guidance prefers CC0 or another Creative Commons license and does not accept a code license for a submitted list.

This implementation does not silently relicense existing contributor content. `LICENSE` remains unchanged. A future owner-led licensing review may migrate the repository to CC0 or CC BY after contributor rights and attribution requirements are resolved.

Official Awesome submission remains a future milestone after the repository has a sustained human-curated history and a compatible license.

## Non-Goals

- Building a website or searchable web application.
- Adding a large number of new projects.
- Automating editorial approval.
- Ranking products with numeric scores.
- Guaranteeing a specific star count or search rank.
- Merging changes directly to `main`.
