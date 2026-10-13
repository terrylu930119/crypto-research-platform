# Selected Design Cases

[English](CASE_STUDIES.md) · [繁體中文](CASE_STUDIES.zh-TW.md)

These examples focus on engineering trade-offs rather than private signals, performance, or strategy outcomes.

## A missing candle is not evidence of a market closure

A data gap can reflect missing collection, exchange downtime, or unresolved provenance. The data plane keeps unknown cases unresolved and prevents an incomplete sequence from being silently accepted as a continuous research window. **Trade-off:** fewer admissible observations in exchange for more defensible evidence.

## An order timeout is not an order rejection

A timed-out request may already have reached the Exchange. The execution layer keeps an explicit `UNKNOWN` outcome and reconciles with Exchange and durable Journal state before any new action. **Trade-off:** pause or constrain execution rather than risk duplicate exposure.

## Shared capital needs one atomic decision

In a multi-deployment host, two strategies can request the same account cash. Global exposure ceilings apply across deployments; optional per-deployment static budgets restrict each strategy further. The Portfolio layer checks and records reservations within a SQLite transaction, and a stable allocation order resolves competing entries. **Trade-off:** deterministic, conservative admission rather than optimistic independent budgets.

## Strategy upgrades cannot abandon old positions

The same logical strategy can have multiple Manifest-derived deployment identities. A previous deployment can stop opening positions while retaining ownership of its exits and recovery obligations. It may be removed from the loaded set only after active state is resolved. Ambiguous legacy checkpoint ownership fails closed. **Trade-off:** more explicit migration steps in exchange for safer restart and version transitions.

## Automation and scientific judgment are different responsibilities

Deterministic validation verifies criteria, identity, admissible inputs, and artifact bindings; it cannot certify causal design or scientific merit. The Research Runbook uses methodology and evidence reviewers for substantive scientific critique, without making their agreement a mechanical workflow gate. Terminal results can be published through READY and integrated into Git history, but do not gain trading or protected-holdout authority. **Trade-off:** preserve useful autonomous throughput without mistaking automation for independent scientific confirmation.
