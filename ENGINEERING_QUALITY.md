# Engineering Quality

[English](ENGINEERING_QUALITY.md) · [繁體中文](ENGINEERING_QUALITY.zh-TW.md)

Research and trading boundaries are meaningful only when the implementation and tests enforce them.

## Development verification

- Python 3.12, `mypy` type checking, `Ruff` linting, and `pytest`.
- Unit and integration tests for data, research contracts, Exchange adapters, and typed risk/execution boundaries.
- Offline end-to-end (E2E) tests exercise strategy projection, TradingHost behavior, recovery paths, and multi-deployment state isolation.
- Explicit opt-in for online Testnet checks. Offline E2E success is **not** an online, GCP, unattended, or production certification.

## Defensive invariants

**Fail closed.** Missing provenance, invalid artifact identity, incompatible deployment contracts, stale risk inputs, or uncertain ownership block the affected operation instead of relaxing a rule.

**Point-in-time research.** Development measurement cannot silently access data outside its approved time or evidence scope; protected evidence is a separate authority.

**Exact financial state.** Price, quantity, balance, and risk computations use `Decimal`-based representations. Global and deployment-level exposure checks precede order submission.

**Atomic allocation.** A shared Portfolio and SQLite Journal coordinate reservations across multiple deployments. Deterministic admission order prevents market-update arrival order from redefining capital allocation.

**Recoverable uncertainty.** Timeouts and ambiguous orders remain `UNKNOWN` pending reconciliation. Durable checkpoints, order identities, reservations, and positions survive process restarts; unproven deployment ownership is not guessed.

## Traceability

Formal research binds Git-tracked configs, frozen evidence, and exact run identities. Trading deployments require pinned strategy/catalog semantics and explicit manifests; research outcomes alone never grant execution rights.

These tests demonstrate engineered boundaries, **not** profitable strategy performance or authorization to place real-money orders.
