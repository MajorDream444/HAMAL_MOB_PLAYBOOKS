---
name: maim-creative-workflow-orchestrator
description: "Coordinate MAIM creative production and maintain a versioned skill registry. Use for creative briefs, agent handoffs, skill evaluation, provider routing and sovereignty planning."
---

# Creative Workflow Orchestrator

Read [production-contract.md](references/production-contract.md) before production.

Version: 0.1.0

## Workflow

1. Classify request as preservation, cover/layout, film, motion or marketing. Load the matching companion skill and the shared contract in references/production-contract.md. Reuse approved assets before commissioning new ones.

2. Create a job with brief, references, workflow, assigned role, dependencies, estimated cost, budget ceiling and acceptance checks. Separate planned, running, blocked, review and completed states.

3. Route Brand Steward -> specialist -> production review -> marketing handoff. An instruction skill is not an autonomous deployed agent. A browser-local registry is not a shared backend. Report actual execution boundaries.

4. Keep tool adapters replaceable: schema, authentication location, availability check, model/version, price basis, timeout, retry/idempotency, result storage and fallback. MCP/API wrappers alone do not supply model weights or compute.

5. Check licenses before importing external skills or assets. Keep restricted downloads external and linked; never rebrand edited third-party instructions as original MAIM work. Write MAIM-specific skills from independent requirements.

6. Evaluate with realistic briefs: exact-logo thumbnail, cover reconstruction, campus continuity and missing-reference job. Record evidence and failures; use untested or structurally_validated labels rather than invented scores.

7. Output a reviewable brief, job manifest, selected skill versions, source evidence, completion limits and a copy-and-paste engineering handoff for any unfinished integration.
