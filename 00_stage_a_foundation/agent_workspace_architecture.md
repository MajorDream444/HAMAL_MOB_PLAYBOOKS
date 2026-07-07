# Agent Workspace Architecture

Status: Stage A foundation
Owner: HAMAL / AMA

This document defines how HAMAL agents think, remember, receive work, produce outputs, and hand off without scanning the entire repository.

## Purpose

The workspace is where agents live.

It is not production.

It is the operating layer for current work, memory, context, scratchpads, token efficiency, and handoffs.

## Proposed Workspace

```txt
workspace/
  000_SHARED_CONTEXT/
  001_COMMAND_CENTER/
  010_LANDING_AGENT/
  011_REGISTRATION_AGENT/
  012_CONTENT_AGENT/
  ...
  144_AGENT/
```

## Shared Context

Every agent may read:

```txt
workspace/000_SHARED_CONTEXT/
  MAIM_CONTEXT.md
  DESIGN_SYSTEM.md
  BRAND.md
  ABC.md
  ROADMAP.md
  CURRENT_SPRINT.md
  ACTIVE_DECISIONS.md
  GLOSSARY.md
```

Shared context must stay small.

It should summarize canonical files instead of copying the entire repo.

## Command Center

Every agent reads this before active work:

```txt
workspace/001_COMMAND_CENTER/
  sprint.md
  priorities.md
  backlog.md
  releases.md
  blockers.md
```

The Command Center tells agents what matters now.

## Universal Agent Room

Every agent has the same home:

```txt
README.md
context/
inbox/
working/
output/
logs/
archive/
memory.md
```

## Folder Purposes

### `README.md`

Orientation for the agent.

### `context/`

Agent-specific context packets.

### `inbox/`

Incoming briefs, handoffs, contracts, and unresolved questions.

### `working/`

Temporary scratch area.

Empty this at the end of a task or sprint.

### `output/`

Approved or handoff-ready artifacts only.

### `logs/`

Short dated summaries, not full conversations.

### `archive/`

Completed, stale, or superseded workspace material.

### `memory.md`

The agent's durable local memory.

It answers:

```txt
Who am I?
What do I own?
What do I never touch?
What did I learn?
What are my current assumptions?
What known issues should I remember?
```

## Layered Context Model

```txt
Shared Context
-> Agent Memory
-> Working Folder
-> Task
```

Agents should not scan the whole repository by default.

They should consume the smallest context packet that can safely complete the task.

## Agent Communication Rule

Agents communicate through contracts and files, not hidden chat history.

Example:

```txt
Registration Agent produces:
  output/registration.json

Content Agent consumes:
  inbox/registration.json
```

## Contract Fields

Every inter-agent contract should define:

- producer
- consumer
- file name
- version
- required fields
- optional fields
- validation rule
- owner
- next action

## Stage A Safety

This is architecture only.

Do not create autonomous execution.

Do not make live tool calls.

Do not store secrets.

Do not wire production integrations.
