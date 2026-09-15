# Engineering Quality

[English](ENGINEERING_QUALITY.md) · [繁體中文](ENGINEERING_QUALITY.zh-TW.md)

The research rules are only useful if the code enforces them.

## Development checks

- Python 3.12
- strict `mypy` type checking
- `Ruff` linting
- `pytest`, including async and HTTP-boundary tests

## Defensive design

**Explicit failure states** — uncertain exchange responses are not treated as success or failure by guesswork.

**Fail closed** — invalid identities, missing authority, malformed data, or unexpected drift stop the path instead of silently relaxing rules.

**Point-in-time boundaries** — research code cannot freely reach beyond the information available at a decision time.

**Exact monetary types** — price, quantity, and balance calculations use `Decimal` rather than binary floating point.

## Reproducibility

Formal research is tied to tracked configs, repository state, validated artifacts, and explicit identities. A result should be explainable from the inputs and authority that produced it.

Tests focus heavily on boundary failures: data gaps, future-data access, artifact drift, uncertain order state, and invalid research transitions.
