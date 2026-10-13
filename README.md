# Crypto Research and Controlled Trading Platform

[English](README.md) · [繁體中文](README.zh-TW.md)

A private Python platform for studying crypto-market hypotheses, rejecting unsupported claims, and developing controlled strategy execution. It connects reproducible research to a separately authorized trading system; a research result never grants permission to deploy or place orders.

## What the platform implements

- **Data and evidence:** Binance Spot and USD-M research data, provenance checks, point-in-time views, and outcome-blind readiness checks.
- **Governed research:** staged measurement, frozen criteria and artifacts, explicit scientific decisions, and protected evidence boundaries.
- **Autonomous Development Research:** bounded Stage 1–3 campaigns and Stage4A design preparation, using deterministic validation and a scientific collaboration process. Completed campaign inventories can move through READY publication and GitHub integration.
- **Shared strategy semantics:** a neutral strategy engine used for research projection and trading, with explicit catalog and deployment-manifest bindings.
- **Controlled trading:** replay, Shadow and gated Binance Spot Testnet execution. A multi-deployment host supports global and per-deployment risk limits, atomic reservations, durable state, exchange reconciliation, and recovery.
- **Engineering checks:** type checking, linting, unit tests, integration tests, and offline end-to-end (E2E) tests.

## What is *not* claimed

This is not a live production trading service. There are **no approved production strategies**. The unattended Testnet runtime and multi-deployment functionality are implemented, but B8 online Testnet behavior and GCP unattended certification have not been established by the offline tests. Production order execution, futures execution, and live capital authority are outside the current trading scope.

## Public scope

The source repository is private. These pages explain engineering boundaries and design decisions without publishing strategy hypotheses, exact rules, parameters, measured outcomes, protected holdout evidence, or operational secrets.

- [Architecture](ARCHITECTURE.md)
- [Research method](RESEARCH_METHODOLOGY.md)
- [Engineering quality](ENGINEERING_QUALITY.md)
- [Selected design cases](CASE_STUDIES.md)
- [Disclosure boundary](SECURITY_AND_DISCLOSURE.md)
