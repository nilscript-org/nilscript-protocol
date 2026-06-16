---
title: NILScript Protocol
description: The neutral standard for letting agents act in real systems — safely, with confirmation, and without bespoke glue per backend.
---

**NILScript Protocol** is the constitution: the **Network Intent Layer (NIL)** wire contract, the
**nilscript DSL** grammar, and the **SEQRD-PC** model. It is documentation — the reading and
authority layer. The runnable engine is the kernel, [`nilscript`](https://github.com/nilscript-org/nilscript)
(`pip install nilscript`).

## The two halves

| | What | Where |
| --- | --- | --- |
| **Protocol** (here) | The spec — NIL, the DSL guides, SEQRD-PC, governance. | docs only |
| **Kernel** | The installable headless engine + SDK + CLI + canonical JSON schemas. | `pip install nilscript` |

> The machine-readable **JSON schemas + conformance vectors** live in the kernel (read offline via
> `importlib.resources`) — the *enforced contract = code*. This site renders/links them; it never forks them.

## Start here

- **NIL** — the wire contract: [v0.2 spec](nil/0.2.0).
- **nilscript DSL** — the orchestration language: [overview](dsl/01-LANGUAGE-OVERVIEW), [how the runtime works](dsl/11-RUNTIME-EXPLAINED).
- **Run it:** `nilscript run plan.nil.json --adapter-url <shim>` (the kernel).
- **Build an adapter:** [nil-adapter-template](https://github.com/nilscript-org/nil-adapter-template).

## Three pillars

1. **Neutral by design** — no backend specifics in the standard (like OpenAPI for APIs).
2. **Safe by contract** — no commit without confirmation; `PROPOSE` has no side effects; `ROLLBACK` previews, never silently writes.
3. **De-frictioned by tooling** — `scan` once, generate an adapter, share the manifest.
