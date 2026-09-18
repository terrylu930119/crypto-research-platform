# Research Method

[English](RESEARCH_METHODOLOGY.md) · [繁體中文](RESEARCH_METHODOLOGY.zh-TW.md)

The research flow is staged so that one result cannot quietly justify a stronger claim than it measured.

```mermaid
flowchart TD
    A[Market Event Information] --> B[Post-Event Information]
    B --> C[Execution Economics]
    C --> D[Strategy Lifecycle]
    D --> E[Candidate Freeze]
    E --> F[Protected Holdout]
    F --> G[Final Decision]
```

## Rules that matter

**Point-in-time access** — research code only sees information that was available at that decision time.

**Outcome-blind preflight** — feasibility checks are done without reading future outcome values.

**Review before seal** — an Agent-authored scientific config, criterion set, or downstream design is independently reviewed before its first Git seal. Pre-outcome findings may be corrected with the same reviewer while the draft is still unfrozen.

**Separate measurement from judgment** — a completed run does not automatically mean `ADVANCE`.

**Freeze before holdout** — candidate identity and evaluation rules are fixed before protected evidence is used.

**No post-hoc rescue** — a consumed holdout is not a tuning dataset.

**Traceable authority** — configs, run artifacts, and decisions are tied to repository state and validated identities.

The platform also supports bounded agent-operated Development Research. The main Research Agent can move through Stage 1–3 under the campaign control plane, while an independent Reviewer audits scientific drafts before sealing and measured interpretations before progression. Automation still does not gain authority over Protected Holdout or Stage 4 formal measurement.
