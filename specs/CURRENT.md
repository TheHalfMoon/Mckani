# Mckani Current Frontier

**Program:** Founding plan -> implementation foundation  
**Repository:** TheHalfMoon/Mckani  
**Planning branch:** codex/founding-plan  
**State:** PLAN READY FOR REVIEW; PRODUCT IMPLEMENTATION NOT YET AUTHORIZED

## Live starting truth

The repository was initialized from an empty Git repository on 2026-09-23.

The seed main commit exists only to create the branchable baseline.

The founding plan lives on `codex/founding-plan` and must be reviewed/merged before product implementation uses it as canonical authority.

## SpecGrain state

Root:

- SG-000001 — Deliver Mckani Spatial Operating System (DRAFT program)

P00:

- SG-000002 — Governance and engineering foundation (DRAFT)

First bounded-candidate draft:

- SG-000019 — MCK-P00-S01-T01 — Establish the implementation workspace and verification baseline (DRAFT)

No `GRAIN`, `READY`, `VERIFIED`, or product-complete state is claimed by this planning branch. The pinned SpecGrain CLI has not promoted an implementation leaf in this repository.

## Next canonical action after plan merge

Reverify `main`, then shape SG-000019 using the pinned SpecGrain source.

The first leaf should include only:

- minimal Rust workspace/shared-core skeleton;
- real formatting/static-analysis/test commands;
- repository tool-version declarations;
- baseline CI;
- no external map/model/provider dependency;
- exact rollback by reverting the bounded foundation change.

After `SHAPED -> REFINING`, run `specgrain check` and promote to `GRAIN` only if current readiness succeeds.

Activate Diffcipline in a separate bounded Grain using the real workspace commands.

## Founder gate before code import

Project-license planning recommendation is Apache-2.0, but it is not yet founder-ratified.

No license-dependent donor source copy/adaptation should occur until that decision is explicit.

## Prohibited shortcuts

- Do not begin with a map UI branch.
- Do not import OpenFreeMap/God's Eye View/MapLibre source before source/dependency qualification.
- Do not add an LLM as a product prerequisite.
- Do not create `.diffcipline.toml` with fictional commands before the workspace exists.
- Do not mark a macro phase complete because planning prose exists.
