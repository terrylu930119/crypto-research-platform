# Crypto Research Platform

[English](README.md) · [繁體中文](README.zh-TW.md)

A private Python project for researching crypto trading ideas with an emphasis on reproducibility, data correctness, and controlled validation.

The goal is not to collect backtests. The system is built to make it easier to reject weak ideas without contaminating later evidence.

## What is in the platform

- Binance Spot and USD-M market data pipelines
- point-in-time research views
- staged research from market-event evidence to execution economics and strategy lifecycle
- Git-bound configs, artifacts, and research decisions
- Testnet execution with explicit handling for uncertain order state
- strict typing, linting, and automated tests

Review tooling and controlled agent-operated development research are still being extended. Protected Holdout and sensitive research decisions remain separately governed.

## Public scope

The production repository is private. This public-facing material describes the architecture and research method, but intentionally excludes strategy hypotheses, parameters, research outcomes, and protected evidence.

- [Architecture](ARCHITECTURE.md)
- [Research method](RESEARCH_METHODOLOGY.md)
- [Engineering quality](ENGINEERING_QUALITY.md)
- [Selected design cases](CASE_STUDIES.md)
- [Disclosure boundary](SECURITY_AND_DISCLOSURE.md)
