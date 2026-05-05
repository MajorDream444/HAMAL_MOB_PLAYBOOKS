# Skill Audit System

## Purpose

The Skill Audit System exists to turn scattered skills, markdown files, repos, prompts, scripts, and tool instructions into a living operating library.

HAMAL does not collect skills for decoration.

HAMAL audits, tests, upgrades, combines, compresses, and attaches skills to real playbooks.

## Core Doctrine

A skill is not automatically useful because it exists.

A skill becomes useful when it has:

- clear purpose
- defined inputs
- defined outputs
- required context
- tool/MCP dependencies
- quality rubric
- owner agent or MOB
- playbook attachment
- feedback loop
- lifecycle status

## What Counts As A Skill

A skill may appear as:

- `SKILL.md`
- markdown instruction file
- prompt pack
- repo folder
- framework template
- Claude/Codex/OpenClaw skill
- MCP usage guide
- workflow recipe
- SOP that can be executed by an agent
- design or development pattern
- reusable business method

Do not rely only on filenames.

Some of the best skills will not call themselves skills.

## Skill Categories

### 1. Context Skill
Teaches an agent what it must know.

Examples:
- Hanzo company context
- Lux tokenization context
- Major voice and offer context
- client industry context

### 2. Process Skill
Teaches an agent how to do repeatable work.

Examples:
- audit a business
- write a proposal
- score a lead
- build a landing page

### 3. Integration Skill
Teaches an agent how to use a tool, API, MCP, plugin, or runtime.

Examples:
- Airtable writeback
- Notion dossier creation
- Firecrawl scraping
- Remotion rendering

### 4. Output Skill
Teaches an agent how to produce a specific artifact.

Examples:
- one-page SOW
- client blueprint PDF
- investor briefing
- social content pack

### 5. Evaluation Skill
Teaches an agent how to judge quality.

Examples:
- proposal quality rubric
- lead score rubric
- video script rubric

## Audit Workflow

### Step 1 — Locate
Find the candidate skill.

Sources:
- GitHub repo
- forked repo
- local folder
- uploaded markdown
- prior chat output
- Notion note
- Obsidian note
- transcript

### Step 2 — Identify
Determine what it actually is.

Classify as:
- Skill
- Tool
- MCP
- API
- Plugin
- Harness
- Playbook
- SOP
- Rubric
- Context File
- Reference Only

### Step 3 — Extract
Pull out:
- purpose
- inputs
- outputs
- assumptions
- required tools
- required context
- execution steps
- risks
- examples

### Step 4 — Test
Run a small usage simulation.

Ask:
- Does it produce useful output?
- Does it require missing context?
- Does it call tools safely?
- Is it too vague?
- Is it redundant with another skill?

### Step 5 — Score
Use the Skill Quality Rubric.

Score areas:
- clarity
- usefulness
- repeatability
- context dependency
- tool dependency
- output quality
- risk level
- token efficiency
- playbook fit

### Step 6 — Decide
Assign status:
- Active
- Needs Upgrade
- Merge Candidate
- Reference Only
- Deprecated
- Dangerous / Do Not Use

### Step 7 — Attach
Every useful skill must attach to at least one playbook.

If no playbook exists, create a candidate playbook idea.

### Step 8 — Improve
Upgrade the skill into HAMAL format.

### Step 9 — Version
Track changes.

Every improvement should answer:
- what changed?
- why did it change?
- what evidence supports the change?

## HAMAL Skill Record Schema

Use this for every audited skill.

```yaml
name:
source_type:
source_repo:
original_repo:
fork_status:
category:
summary:
inputs:
outputs:
required_context:
required_tools:
required_mcps:
agent_owner:
mob_owner:
playbooks:
risk_level:
token_cost_profile:
local_model_compatible:
quality_score:
status:
upgrade_notes:
last_reviewed:
```

## Skill Lifecycle

```text
Imported
→ Classified
→ Tested
→ Scored
→ Attached to Playbook
→ Upgraded
→ Used in Real Work
→ Reviewed
→ Compressed / Merged / Archived
```

## What Makes A Skill Strong

A strong skill:

- has a clear trigger
- knows when not to run
- uses specific inputs
- produces a predictable artifact
- fits a playbook
- has examples
- has anti-patterns
- can be tested
- can improve over time

## What Makes A Skill Weak

A weak skill:

- sounds smart but gives no process
- lacks inputs and outputs
- assumes context it does not define
- creates generic output
- cannot be evaluated
- does not connect to tools or playbooks
- duplicates better skills
- burns tokens without producing value

## HAMAL Rule

Do not ask “how many skills do we have?”

Ask:

- Which outcomes can these skills produce?
- Which skills belong together?
- Which skills are redundant?
- Which skills should become playbooks?
- Which skills should be retired?
- Which skills can create revenue?

## North Star

The goal is not a bigger skill folder.

The goal is a smarter operating system.
