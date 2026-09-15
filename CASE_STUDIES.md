# Selected Design Cases

[English](CASE_STUDIES.md) · [繁體中文](CASE_STUDIES.zh-TW.md)

## Data gaps are not guessed away

A missing candle does not automatically mean corruption or exchange downtime. The data layer keeps unresolved gaps unresolved unless there is enough provenance to classify them.

The important part is that research rules do not become looser just because the data is inconvenient.

## An order timeout is not a failed order

If an order request times out, the exchange may still have received it. Retrying immediately can create a duplicate position.

The execution model therefore has an explicit `UNKNOWN` state and requires reconciliation before retrying.

## Automation stays inside research boundaries

The current automation work focuses on bounded research context, review preparation, lifecycle state, and deterministic facts.

It is intentionally not a shortcut around preregistration, human-gated transitions, or Protected Holdout controls.
