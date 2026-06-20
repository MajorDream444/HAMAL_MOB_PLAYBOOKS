# Interpretable Context Methodology — Playbook Foundation

## Purpose

This file defines how HAMAL builds skills, playbooks, SOPs, and agent context using folders and Markdown.

The goal is not more files for the sake of files.

The goal is to turn useful conversations into reusable operating memory.

## Core Principle

```text
The chat discovers the method.
The folder preserves the method.
The agent executes the method.
The playbook monetizes the method.
```

## Definition of a Skill

A skill is a structured folder of context that teaches an AI agent how to perform a specific task.

It can include Markdown files, templates, scripts, examples, outputs, and validation rules.

A skill should be interpretable by a human and executable by an agent.

## Standard Skill Folder

```text
/skills/[skill_name]/
├── README.md
├── claude.md
├── codex.md
├── voice.md
├── tone.md
├── context.md
├── pillars.md
├── process.md
├── decision_chain.md
├── inputs.md
├── outputs.md
├── examples.md
├── validation.md
├── handoff.md
├── research/
├── templates/
├── outputs/
└── archive/
```

## Minimum Viable Skill

Not every skill needs every file on day one.

Minimum viable skill:

```text
README.md
context.md
process.md
examples.md
validation.md
handoff.md
```

Add voice, tone, scripts, templates, and deeper decision chains as the skill matures.

## Skill Maturity Levels

### Level 0 — Raw Note

A useful idea exists, but it is not yet structured.

### Level 1 — Captured Skill

The idea has a folder and basic Markdown files.

### Level 2 — Usable Skill

The skill has process, examples, validation, and handoff instructions.

### Level 3 — Agent-Ready Skill

The skill includes claude.md / codex.md maps and can be used by agents reliably.

### Level 4 — Playbook-Attached Skill

The skill is mapped into a larger business playbook.

### Level 5 — Automated Skill

The skill is connected to tools, scripts, APIs, MCPs, or workflows.

## Chain of Decisions Extraction

Every strong skill begins with a successful dialogue.

Extract:

```yaml
what_was_the_goal:
what_did_major_want:
what_constraints_mattered:
what_examples_were_used:
what_did_the_ai_get_wrong_first:
what_corrections_fixed_it:
what_decisions_created_the_final_output:
what_style_rules_emerged:
what_process_rules_emerged:
what_assumptions_must_be_preserved:
what_should_never_happen:
what_output_was_accepted:
what_next_step_should_follow:
```

## File Roles

### README.md

What this skill does and when to use it.

### context.md

Background the agent must know.

### process.md

Step-by-step method.

### decision_chain.md

Why the method works and how it was discovered.

### examples.md

Good examples, bad examples, before/after examples.

### validation.md

Checklist for judging output quality.

### handoff.md

Where the output goes next.

### claude.md

How Claude-like agents should use the skill.

### codex.md

How Codex/execution agents should use the skill.

## Scriptwriting Skill Example

```text
/skills/scriptwriting_skill/
├── README.md
├── claude.md
├── codex.md
├── voice.md
├── tone.md
├── pillars.md
├── process.md
├── decision_chain.md
├── research/
│   ├── hooks.md
│   ├── outlines.md
│   └── source_materials.md
├── templates/
│   ├── short_form_video.md
│   ├── podcast_intro.md
│   └── sales_video.md
├── outputs/
│   ├── final_scripts.md
│   └── placeholders/
└── validation.md
```

## HAMAL Folder Strategy

The HAMAL ecosystem should organize knowledge into:

```text
00_stage_a_foundation/
01_doctrine/
02_playbooks/
03_agents/
04_skills/
05_templates/
06_audits/
07_rubrics/
08_outputs/
09_archive/
```

## Playbook Rule

A playbook is a sequence of skills.

Example:

```text
Research Skill
→ Scriptwriting Skill
→ Video Direction Skill
→ Distribution Skill
→ Analytics Skill
```

The playbook defines how the skills combine to create a business outcome.

## Agent Rule

Agents must be given:

```yaml
skill_folder:
playbook_folder:
context_file:
process_file:
validation_file:
output_location:
handoff_target:
```

## No Drift Rule

If a folder has a `claude.md`, `codex.md`, or `README.md`, the agent must read the map before acting.

Do not invent a new process if a process file already exists.

## First Skills To Build This Way

Priority HAMAL skills:

```text
business_pressure_test_skill
client_onboarding_sow_skill
scriptwriting_skill
video_director_skill
model_influencer_audit_skill
west_africa_corridor_pitch_skill
telegram_bot_flow_skill
agent_handoff_skill
graphify_context_skill
```

## Operating Reminder

The folder system is not extra work.

The folder system is how the work stops being repeated.

```text
Do it once.
Capture it.
Structure it.
Reuse it.
Improve it.
```
