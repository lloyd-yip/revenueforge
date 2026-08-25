---
tags: [architecture, planning, conventions]
last_updated: 2026-08-24
---
# Architecture — Core Facts

## Stack
None. RevenueForge is planning-stage — no application code, no database, no hosting.

## Repo layout
This repo is **documents only**. Deployed artifacts live in their own repos (see README).
Do not add application code here; a build gets its own repo per born-standalone.

## Conventions
- `docs/planning/DECISIONS.md` holds *reasoning*; the interactive model holds *conclusions*.
  When they disagree, the model is current and the decision log explains why the parameter exists.
- Documents copied out of the dissolving monorepo are canonical here. Originals are superseded.
