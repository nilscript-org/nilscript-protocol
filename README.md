<div align="center">

# NILScript

The governed action layer for AI agents. An agent proposes intent; a deterministic kernel is the only
thing that commits; an action a backend never declared is unexpressible, not filtered. Composes with
MCP. `pip install nilscript`.

---

# NILScript Protocol

**The constitution of NILScript — the Network Intent Layer (NIL) wire contract, the nilscript DSL grammar, and the SEQRD-PC model.**

*The standard. The runnable kernel lives at [nilscript-org/nilscript](https://github.com/nilscript-org/nilscript).*

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20774491.svg)](https://doi.org/10.5281/zenodo.20774491)

</div>

---

This repository is **documentation only** — the specification text, the constitution, the reading
layer. It is **not** an installable package. Like the OpenAPI, JSON Schema, and MCP specifications,
the standard has its own home, separate from the implementations that run it.

> **Where the machine-readable contract lives:** the canonical **JSON schemas**, the **DSL schema**,
> and the **conformance vectors** ship inside the kernel package (`nilscript`), where they are read
> offline via `importlib.resources` — they are the *enforced contract = code*, not prose. This repo
> renders and references them; it never forks them. See the
> [extraction plan §7.1](https://github.com/nilscript-org/nilscript/blob/main/docs/nilscript-kernel-extraction-plan.md).

## The two halves

| | What | Where |
| --- | --- | --- |
| **NILScript Protocol** (this repo) | The constitution — NIL narratives, the DSL grammar guides, SEQRD-PC, governance. | `nilscript-protocol` (docs) |
| **NILScript** (the kernel) | The installable, headless execution engine + SDK + CLI + canonical JSON schemas. | [`nilscript`](https://github.com/nilscript-org/nilscript) (`pip install nilscript`) |

## Map

### NIL — the Network Intent Layer (`nil/`)
The wire contract: how an agent proposes an action, how a backend answers, the envelope, grants,
refusals, rollback, and per-domain profiles. Seven performatives (**SEQRD-PC**: STATUS · EVENT ·
QUERY · ROLLBACK · DECIDE · PROPOSE · COMMIT).

- [`nil/0.2.0.md`](nil/0.2.0.md) — the current spec (v0.2)
- [`nil/0.1.0.md`](nil/0.1.0.md) — the foundation
- [`nil/0.1.0-hosted-profile.md`](nil/0.1.0-hosted-profile.md) · [`nil/0.1.0-conformance-checklist.md`](nil/0.1.0-conformance-checklist.md) · [`nil/0.2.0-calibration-appendix.md`](nil/0.2.0-calibration-appendix.md)

### nilscript DSL — the orchestration language (`dsl/`)
A declarative, JSON-based, LLM-native language one layer above NIL: an agent writes a program, a
static validator admits it, a runtime executes it. Start at [`dsl/00-INDEX.md`](dsl/00-INDEX.md).
Key chapters: [grammar](dsl/02-GRAMMAR-AND-PRIMITIVES.md), [validation & types](dsl/03-VALIDATION-AND-TYPES.md),
[execution model](dsl/04-EXECUTION-MODEL.md), [the runtime explained](dsl/11-RUNTIME-EXPLAINED.md).

### Profile registry (`registry/`)
The verb catalogs per domain: [commerce-v1](registry/commerce-v1.md) · [services-v1](registry/services-v1.md).

### Governance (`governance/`)
[GOVERNANCE.md](governance/GOVERNANCE.md) (the Steward / Reference-Implementation rule) ·
[VERSIONING.md](governance/VERSIONING.md) · [CODE_OF_CONDUCT.md](governance/CODE_OF_CONDUCT.md).

## Using the standard

- **Run it:** `pip install nilscript` → `nilscript run plan.nil.json --adapter-url <shim>` (the kernel).
- **Build an adapter:** start from [nil-adapter-template](https://github.com/nilscript-org/nil-adapter-template).
- **Implement an SDK in another language:** read the JSON schemas in the
  [kernel's `nil/` and `dsl/`](https://github.com/nilscript-org/nilscript/tree/main/src/nilscript) — no per-language package is reserved.

## License

Specification text: **CC BY 4.0**. Schemas / vectors / code (in the kernel): **Apache 2.0**.

## Citation

This repository is the specification of the **NIL (Network Intent Layer)** framework, described in a
published paper archived on Zenodo with a permanent DOI:
**[10.5281/zenodo.20774491](https://doi.org/10.5281/zenodo.20774491)**.

```bibtex
@misc{elkhider2026nil,
  title  = {Unexpressible, Not Filtered: A Structural Framework for Governing AI-Agent Actions --- the Network Intent Layer},
  author = {Elkhider, ElBasheir A. M.},
  year   = {2026},
  doi    = {10.5281/zenodo.20774491},
  url    = {https://doi.org/10.5281/zenodo.20774491}
}
```
