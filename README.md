# HSI_Procedure_Toolkit
Generate encounters at the push of a button. Made for the sole purpose of running D&amp;D games using the Hot Springs Island campaign setting and book by Jacob Hurst and Swordfish Bay.

A human-in-the-loop toolkit for generating encounters for **Hot Springs Island (HSI) v2**, with GitHub as the authoritative store and AI used only for reasoning, review, and proposal.

This repository prioritizes **truth, reproducibility, and auditability** over speed or automation.

---

## Core Principles

* **GitHub is the source of truth**

  * Canonical tables, generators, and logic live here.
  * History, diffs, and releases matter.

* **AI does not have authority**

  * Codex / ChatGPT may analyze, draft, and propose.
  * Humans decide what becomes canon.

* **Encounters are epistemic artifacts**

  * Draft ≠ playtest ≠ canon.
  * Each stage has explicit rules and boundaries.

---

## Environments (How to Think About This Repo)

This repo uses **GitHub Environments** to encode *trust and authority*, not deployment.

### `analysis` (default working state)

**Purpose:** Safe reasoning and draft generation.

* Draft encounter outputs
* Experimental table tweaks
* Schema refactors
* “What would this generate?” previews
* Markdown or JSON artifacts meant for inspection

Rules:

* Nothing here is canon.
* No direct commits to protected branches.
* AI assistance is unrestricted but non-authoritative.

Think of this as the **scratchpad and proposal engine**.

---

### `canon` (authoritative)

**Purpose:** Locked, table-ready truth.

* Approved encounter logic
* Locked HSI tables and procedures
* Stable generators
* Tagged releases

Rules:

* All changes arrive via PR.
* Human approval required.
* Every change must justify:

  * *What changed*
  * *Why*
  * *Which table / rule it affects*

If it’s here, it’s real.

---

### `playtest` (optional / future)

**Purpose:** Structured experimentation.

* Variant generators
* Optional or house-rule logic
* Debug-heavy tooling

Rules:

* May drift or break.
* Never implicitly promoted to canon.
* Exists to protect canon from experimentation.

---

## Repository Structure (Conceptual)

```
/src
  /engine        ← encounter generation logic
  /tables        ← HSI tables (authoritative when canonized)
  /validators    ← sanity checks and invariants

/outputs
  /analysis      ← draft encounters, previews
  /playtest      ← experimental runs
  /canon         ← approved generators / exports

/docs
  DESIGN.md
  TABLE_AUTHORITY.md
  VERSIONING.md
```

Folders reinforce intent; environments reinforce authority.

---

## Canonization Workflow (High Level)

1. Work happens in **`analysis`**
2. Outputs are reviewed by a human
3. A PR proposes promotion to **`canon`**
4. Approval merges truth
5. Releases are tagged from canon only

There is no shortcut by design.

---

## Why This Exists

Hot Springs Island is procedural, emergent, and fragile.

This toolkit exists to:

* Preserve the integrity of HSI’s encounter logic
* Make reasoning visible
* Prevent silent drift
* Allow iteration *without* erosion of canon

If you’re tempted to automate authority away, stop and reread this file.

---

## Final Note to Future Me

If you’re confused about whether something is “real”:

* Check the environment.
* Check the branch.
* Check whether a human approved it.

The friction is intentional.

