# Selected Design Cases

[English](CASE_STUDIES.md) · [繁體中文](CASE_STUDIES.zh-TW.md)

## Data gaps are not guessed away

A missing candle does not automatically mean corruption or exchange downtime. The data layer keeps unresolved gaps unresolved unless there is enough provenance to classify them.

The important part is that research rules do not become looser just because the data is inconvenient.

## An order timeout is not a failed order

If an order request times out, the exchange may still have received it. Retrying immediately can create a duplicate position.

The execution model therefore has an explicit `UNKNOWN` state and requires reconciliation before retrying.

## Independent review happens before research is sealed

The main Research Agent can draft a hypothesis, control design, criteria, or downstream research contract, but Agent-authored scientific artifacts are reviewed before their first Git seal.

This matters because schema validation cannot detect every research-design mistake. An independent Reviewer can catch mismatches between the written claim and the actual config, confounded controls, or unsupported assumptions while the draft is still outcome-blind and editable.

After formal outcomes exist, the rule changes: review can block progression, but it cannot become a loop for rewriting the interpretation until it passes.

## Automation stays inside research boundaries

The autonomous campaign can coordinate Stage 1–3 Development Research and bounded Stage4A preparation, but it is not a shortcut around formal authority, Stage 4 formal authorization, or Protected Holdout controls.
