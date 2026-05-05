# CODEX HANDOFF — STAGE A

## Current Mission

We are in Stage A only: context, playbooks, SOPs, rubrics, and audit structure.

Do not move into Stage B automation yet.

## Repo Purpose

This repo is the doctrine and operating library for HAMAL MOB Playbooks.

It should teach Codex and future agents how to:

- understand context
- create playbooks
- create SOPs
- classify skills, tools, MCPs, APIs, plugins, and harnesses
- audit repos
- map industries to MOB playbooks
- prepare for later execution safely

## Core Rule

No execution without context.

Before building or changing anything, ask:

- What system is this part of?
- What context does it need?
- What playbook does it serve?
- What agent or MOB owns it?
- What tool or MCP does it require?
- Where does output live?
- How is quality judged?

## Immediate Codex Tasks

1. Inspect this repo structure.
2. Read `README.md`, `SYSTEM.md`, and all files in `05_templates/`.
3. Create the missing Stage A foundation files, staying consistent with the existing doctrine.
4. Do not wire live automations yet.
5. Do not create autonomous agent workflows yet.

## First Files to Build Next

- `CONTEXT.md`
- `GLOSSARY.md`
- `00_stage_a_foundation/stage_a_manifest.md`
- `00_stage_a_foundation/context_architecture.md`
- `00_stage_a_foundation/repo_audit_method.md`
- `00_stage_a_foundation/skill_taxonomy.md`
- `00_stage_a_foundation/tool_mcp_taxonomy.md`
- `01_sops/sop_make_context.md`
- `01_sops/sop_make_playbook.md`
- `01_sops/sop_make_skill.md`
- `01_sops/sop_make_rubric.md`
- `01_sops/sop_audit_repo.md`
- `08_agent_context/memory_vs_skill.md`
- `08_agent_context/pinned_available_discoverable.md`
- `08_agent_context/agent_context_rules.md`

## Operating Definitions

- Context: the truth layer.
- Playbook: reusable operating recipe.
- SOP: step-by-step procedure for consistent execution.
- Skill: documented method for solving a specific task.
- Tool: executable capability.
- API: connection to an external system.
- MCP: standard interface for AI tools.
- Plugin: bundled skills + tools + configuration.
- Harness: runtime where agents execute.
- Rubric: quality standard for judging outputs.

## Notion Audit Database

The Notion audit database is named:

`GitHub Repos - Majordream444`

It tracks repo status, theme, action, priority, visibility, duplicates, canonical repo status, and notes.

## Repo Rule

This repository should remain clean, modular, and readable.

Every new file must fit one of these buckets:

- context
- SOP
- playbook
- template
- rubric
- audit
- agent context
- MOB operating model
- industry operating model
- source notes
