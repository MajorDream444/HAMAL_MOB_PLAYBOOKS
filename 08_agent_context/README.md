# Agent Context

Status: Stage A foundation

This folder stores context rules for agents.

Use it for:

- memory rules
- context packet standards
- pinned / available / discoverable context
- agent workspace rules
- handoff contracts
- token discipline
- escalation rules

## Core Rule

Agents should not scan everything.

Agents should receive layered context:

```txt
Shared Context
-> Agent Memory
-> Working Folder
-> Task
```
