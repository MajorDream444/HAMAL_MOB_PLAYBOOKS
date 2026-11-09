# Six-document build handoff

**Status:** Proposal for human review. This is a MobStack workflow playbook. [HAMAL MOB PLAYBOOKS](https://github.com/MajorDream444/HAMAL_MOB_PLAYBOOKS) owns reusable doctrine. The workload repository owns the actual packet, decisions, and implementation.

Use this workflow for new apps, sites, automations, and material changes. Before external release, check the current packet and run the applicable release checks. For an existing project, record the current baseline and assess the proposed change. A static site can use a reviewed inapplicability rationale for a data requirement it genuinely lacks.

## 1. Ground the request

YAWDIE identifies the workload, product owner, decision maker, source, and release scope. Record original wording, date, source, and an agreed interpretation in the workload's approved workspace.

- **Founder-led:** Major owns product intent. Preserve his wording and reflect back the intended outcome, scope, and acceptance criteria.
- **Client-led:** Capture the client's words, ask for an example of the desired outcome, and have the authorized client owner confirm the interpretation. Track conflicting requests and who can resolve them.
- **Team and agents:** Clarify ambiguity and propose improvements with rationale and impact. Keep proposals separate from approved requirements. Engineering owns routine implementation choices within approved boundaries. Changes to the experience, scope, pricing, permissions, data use, or release boundaries go back to the relevant owner.

Optional discovery can compare competing products, substitutes, and underserved users. Label findings with sources and date, separate them from hypotheses, and return positioning proposals to the owner. Discovery may inform scope after a recorded decision.

## 2. Assemble and review the packet

Put an index such as `docs/BUILD-PACKET.md` in the owning repository. For each row record the exact source/version, owner, status, and approval evidence or blocker. Reuse current approved equivalents.

| Document | Required coverage |
| --- | --- |
| PRD | User, problem, intended outcome, scope, exclusions, metrics, and testable requirements |
| App flow | User and operator journeys, failure paths, and recovery |
| UI/UX design brief | Approved references, responsive screens, and loading, empty, and error states |
| Technical requirements | Architecture, integrations, boundaries, dependencies, and operational failure handling |
| Backend schema | Data ownership, constraints, access, lifecycle, and state transitions |
| Implementation plan | Work order, owners, acceptance tests, staging evidence, deployment, and rollback |

Give each requirement an ID and carry it through the relevant flow, design, technical or data decision, implementation ticket, and acceptance evidence.

## 3. Decide readiness and record a receipt

- **Build review:** YAWDIE checks all six slots, links current evidence, and flags gaps. The product owner approves scope and experience, engineering confirms feasibility, and blocking decisions must be closed. A named human records the gate decision against the exact version.
- **Release review:** Recheck the approved scope against the candidate version. Record staging results, known exceptions, rollback or recovery steps, and the release owner's decision. For payments, limited inventory, licenses, or other exclusive allocations, apply the [commerce release checks](commerce-release.md) and the existing [foundation gates](https://github.com/MajorDream444/Mobstack/blob/74f2e6d38f2592a74b16b5e794314525b7df9eb9/gates/README.md).
- **Receipt:** Record workload and commit/version, source and packet links, six document statuses, decision maker and outcome, test evidence, blockers, and next owner/action. Use PASS, HOLD, REDIRECT, or STOP. A material change reopens the affected approval. Keep private source material and receipts in the authorized workspace.
