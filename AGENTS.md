# ISRAA Hub — Agent Guide

SaaS/service platform. Hub provides licensing, subscriptions, installations, releases, updates, catalogs and optional services.

Core and Hub have separate Git repositories, separate databases, are independently versioned, communicate through explicit versioned contracts, and must not directly access each other's databases.

## Agent skills

### Issue tracker

Issues live in GitHub Issues. See `docs/agents/issue-tracker.md`.

### Triage labels

Default canonical labels (`needs-triage`, `needs-info`, `ready-for-agent`, `ready-for-human`, `wontfix`). See `docs/agents/triage-labels.md`.

### Domain docs

Single-context layout (root `GLOSSARY.md` + `docs/adr/`). See `docs/agents/domain.md`.
