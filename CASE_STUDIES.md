# Selected Design Cases

[English](CASE_STUDIES.md) · [繁體中文](CASE_STUDIES.zh-TW.md)

## Data gaps are not guessed away

A missing candle does not automatically mean corruption or exchange downtime. The data layer keeps unresolved gaps unresolved unless there is enough provenance to classify them.

The important part is that research rules do not become looser just because the data is inconvenient.

## An order timeout is not a failed order

If an order request times out, the exchange may still have received it. Retrying immediately can create a duplicate position.

The execution model therefore has an explicit `UNKNOWN` state and requires reconciliation before retrying.

## Deterministic checks do not certify scientific judgment

The campaign validates artifact identity, config and criteria contracts, data readiness, formal provenance, and decision bindings. Those checks cannot establish that a hypothesis is scientifically useful, that its controls avoid confounding, or that its interpretation is persuasive. Independent agent review is optional advice and does not gate the workflow; Human judgment remains necessary for scientific decisions and reserved authority boundaries.

## Automation stays inside research boundaries

The autonomous campaign can coordinate Stage 1–3 Development Research and bounded Stage4A preparation, but it is not a shortcut around formal authority, Stage 4 formal authorization, or Protected Holdout controls.
