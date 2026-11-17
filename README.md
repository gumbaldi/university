# University Template

A private, persistent **multi-learner mission operating system**: AI-assisted learning, investigation, goal achievement, GitHub durable state, source-grounded knowledge, reusable learning material, and scalable scientific/empirical inquiry.

> Humans: start here. AI agents: `ENTRYPOINT.md`. Build another University from one file: `SETUP.md`.

## Core model

A University serves multiple learners without merging their personal state. `UNIVERSITY_PROFILE.md` provides instance configuration and a routing default; each learner owns a separate `learners/<learner-id>/` workspace. Shared material is neutral and learner-independent.

Root `MISSION.md` is a cold University-wide charter. The first learner's first mission belongs to that learner's first topic and never silently narrows the University's global purpose.

## Mission modes

A topic is a persistent mission workspace, not necessarily a course.

| Mode | Primary purpose |
|---|---|
| `learn` | build usable, durable understanding or skill |
| `investigate` | answer a question, analyze evidence/options, reduce uncertainty |
| `achieve` | move a real-world outcome forward through planning/action/adaptation |
| `hybrid` | combine only the mechanisms the mission genuinely needs |

**Mission first, method second.** Competencies/tests are useful for genuine learning, not mandatory for every investigation or real-world goal.

## Scientific / empirical inquiry

Research-like work stays inside `investigate` (or the investigation component of `hybrid`); there is no separate research mission mode.

When work involves original data collection, empirical inference, comparative evaluation or similarly research-like knowledge generation, the engine can activate a scalable scientific-inquiry lens with inferred rigor:

- `lightweight` — ordinary exploratory/low-consequence inquiry,
- `structured` — original data or conclusions that need a traceable method/inference trail,
- `high-rigor` — high consequence, publication/reproducibility need, strong causal claims or substantial independent scrutiny.

The protocol scales across: **Frame → Design → Collect → Analyze → Challenge → Interpret & Validate → Report & Revise**. It includes adversarial evidence, pre-data-plan/amendment integrity, operationalization, data lineage, sampling/stopping, missing-data/data-quality handling, causal/bias discipline, uncertainty/robustness, ethics/privacy, validation/replication and non-selective reporting where relevant.

`RESEARCH.md` is optional and lazy. Ordinary lookup/research does not create it. When method/auditability state matters, `RESEARCH.md` is the topic-local entrypoint and optional actual artifacts may live under `research/` (`data/`, `analysis/`, `code/`) only as needed.

## Runtime economy and durable state

Known-topic work starts with `index.md + PROGRESS.md`, then loads only task-relevant state/models/contracts/sources.

> Use the minimum sufficient context, not the minimum sufficient answer.

`PROGRESS.md` remains a compact current snapshot. On meaningful writes the engine reasons through:

- **KEEP** — needed to resume or make the next decision,
- **MOVE** — durable detail that belongs in a canonical evidence/knowledge/resource/research/sub-mission artifact,
- **DROP** — superseded/intermediate/redundant state recoverable from Git.

No arbitrary age/byte/token split threshold is used. If Progress itself starts consuming a substantial share of normal hot context, compaction review is mandatory.

After decision-relevant durable state changes, the not-yet-written difference is an **unpersisted durable delta**. Before the repository is described as current, used as the resume/handoff point, or a meaningful segment is intentionally paused/ended, that delta must be persisted successfully.

## Framework observations

Framework observations are cold local state under `notes/framework/`, outside the deterministic bootstrap package.

- new observations: `notes/framework/open/NNNN-<slug>.md`, one idea per file,
- resolved observations: `notes/framework/done/NNNN-<slug>.md`, retaining the stable ID and resolution/version metadata,
- explicit framework/version review reads `open/` by default; `done/` is historical context loaded only when needed.

Observations are not tasks, priorities, approvals or framework-unlock state.

## Conversation, language and isolation

Learner-facing chats bind exactly one learner for the conversation. Subject/mission chats bind one stable primary topic once intent is clear. Related same-learner secondary topics may be consulted selectively; unrelated work belongs in another chat.

Generic engine docs/contracts/templates/metadata are English. Learner-facing language follows the active learner/current conversation and actually known learner preferences. University `preferred_knowledge_language`, when set, applies only to neutral shared/maintained knowledge.

Structured internal state does not imply workflow-log conversation. Routine dialogue stays centered on the learner's subject, decision or action.

## Deterministic bootstrap and portability

`SETUP.md` is the standalone portable source package for the generic engine. Its package body contains the exact packaged-static manifest and canonical content of every packaged static file. Local profiles, learners, topics, version history and framework observations are dynamic/local state and are not copied from the source University.

A newly bootstrapped University begins its own local engine/spec line at `1.0.0` while preserving source provenance separately.

The generic engine is Markdown/text-first and must remain interpretable without mandatory Bash/shell scripts, Python scripts, cron jobs, GitHub Actions or daemons. Temporary development tooling may verify a release but is never a runtime/bootstrap dependency.

## Framework lock and safety

The generic core is locked by default. Core implementation requires an explicit scope/reason/affected-area/SemVer summary and a single-use current-conversation authorization. Structural/version changes use branch + PR and create a new local engine version.

Private-core must remain exactly `private`; metadata is freshly checked before every mutation. Public writes require exact approval. Secrets are never stored. High-stakes/current work uses stronger source, uncertainty, ethics and safety handling.

## Key docs

- Runtime/hard rules: `ENTRYPOINT.md`, `AGENTS.md`, `docs/RUNTIME_CONTEXT.md`
- Mission/research routing: `docs/MISSION_MODEL.md`
- Knowledge/evidence/inference: `docs/KNOWLEDGE_MODEL.md`
- Learners/topics: `docs/contracts/learner.md`, `docs/TOPIC_MODEL.md`, `docs/contracts/topic.md`
- Research record/artifacts: `docs/contracts/research.md`, `templates/research.md`
- Learning: `docs/LEARNING_MODEL.md`
- Artifact router: `docs/CONTENT_FORMATS.md`
- Outputs/design/prose: `docs/OUTPUT_FORMATS.md`, `docs/DESIGN_SYSTEM.md`, `docs/PROSE_STYLE.md`
- Publication: `docs/PUBLICATION.md`
- Versioning/bootstrap: `docs/VERSIONING.md`, `SETUP.md`
- Research/attribution: `CREDITS.md`
