# Generative Media Skill Inventory

## Source

- HAMAL fork: `MajorDream444/Generative-Media-Skills`
- Upstream reference: `SamurAIGPT/Generative-Media-Skills`
- Audit basis: Stage A local file inspection from Codex
- Status: P1 Review Needed

This inventory turns the repo audit into reusable HAMAL skill records.

## Inventory Rules

- Do not run scripts, APIs, MCP servers, or workflow execution from this inventory.
- Treat executable primitives as blocked until Stage B.
- Every skill must attach to a playbook before operational use.
- Every media-generation skill requires rights, consent, platform, and storage context.
- Face/likeness generation remains blocked until explicit consent and likeness policy exists.

---

## 1. `core/media`

```yaml
name: core_media
source_path: core/media/SKILL.md
hamal_class:
  - Tool
  - Integration Skill
category: Media Generation Primitive
purpose: Submit media generation requests and return image, video, or audio outputs, request IDs, and URLs.
inputs:
  - prompt
  - image URL or file
  - model
  - duration
  - style
  - aspect ratio
outputs:
  - generated media URL
  - request ID
  - JSON response
required_context:
  - model policy
  - rights and consent
  - output storage rules
  - naming convention
required_tools:
  - muapi
  - curl
  - jq
  - python3
required_credentials:
  - MUAPI_KEY or MUAPI_API_KEY
risk_level: High
stage_status: Blocked until Stage B
mob_owner:
  - Artisans
  - Vanguards
agent_owner:
  - Operator
  - Director
playbook_fit:
  - Media Asset Generation Playbook
  - Product Showcase Video Playbook
  - Social Video Campaign Playbook
upgrade_needed:
  - add safe execution wrapper
  - add output storage contract
  - add cost/token/run logging
  - add human approval gate
status: Review Needed
```

## 2. `core/edit`

```yaml
name: core_edit
source_path: core/edit/SKILL.md
hamal_class:
  - Tool
  - Integration Skill
category: Media Editing Primitive
purpose: Edit, enhance, transform, or clean media assets using API-backed edit operations.
inputs:
  - media URL or file
  - edit prompt
  - operation type
  - model
outputs:
  - edited media URL
  - request ID
  - JSON response
required_context:
  - media rights
  - allowed edits
  - source ownership
  - storage policy
required_tools:
  - muapi
  - curl
  - jq
  - python3
risk_level: High
stage_status: Blocked until Stage B
mob_owner:
  - Artisans
  - Guardians
agent_owner:
  - Editor
  - Guardian
playbook_fit:
  - Media Enhancement And Cleanup Playbook
  - Legacy Vault Media Engine Playbook
upgrade_needed:
  - define allowed edit policy
  - add before/after review gate
  - add source asset preservation rule
status: Review Needed
```

## 3. `core/platform`

```yaml
name: core_platform
source_path: core/platform/SKILL.md
hamal_class:
  - Tool
  - Harness
category: Platform Utility
purpose: Handle platform setup, authentication, result polling, and request status utilities.
inputs:
  - API key
  - request ID
  - endpoint configuration
outputs:
  - auth status
  - request status
  - result payload
required_context:
  - credential policy
  - environment file policy
  - logging policy
  - secret handling rules
required_tools:
  - shell
  - muapi
risk_level: High
stage_status: Blocked until Stage B
mob_owner:
  - Vanguards
  - Guardians
agent_owner:
  - Operator
  - Guardian
playbook_fit:
  - Tool Readiness Playbook
  - AI Media Workflow Audit Playbook
upgrade_needed:
  - remove any unsafe credential behavior
  - enforce .env-only secrets
  - add safe polling wrapper
status: Blocked
```

## 4. `ai-clipping`

```yaml
name: ai_clipping
source_path: library/edit/ai-clipping/SKILL.md
hamal_class:
  - Output Skill
  - Integration Skill
category: Long-Form Repurposing
purpose: Convert long videos into ranked short clips with timestamps, scores, and clip outputs.
inputs:
  - long video URL or file
  - clip count
  - target aspect ratio
  - platform
  - scoring preference
outputs:
  - clip list
  - timestamps
  - clip scores
  - clip URLs or export references
required_context:
  - content rights
  - platform specs
  - clip scoring rubric
  - brand voice
required_tools:
  - muapi clipping endpoint
risk_level: High
stage_status: Needs context before Stage B
mob_owner:
  - Artisans
  - Provocateurs
agent_owner:
  - Editor
  - Distributor
playbook_fit:
  - Long-Form Content Repurposing Playbook
  - YouTube To Shorts Playbook
  - Creator Content System Playbook
upgrade_needed:
  - HAMAL clip score rubric
  - rights check before processing
  - platform-specific output schema
status: Upgrade First
```

## 5. `cinema-director`

```yaml
name: cinema_director
source_path: library/motion/cinema-director/SKILL.md
hamal_class:
  - Process Skill
  - Output Skill
category: Cinematic Direction
purpose: Translate creative intent into director-level cinematic prompts and shot instructions.
inputs:
  - subject
  - intent
  - mood
  - brand/story goal
  - platform
outputs:
  - director brief
  - shot language
  - camera movement
  - lighting and pacing direction
required_context:
  - creative brief
  - brand identity
  - target emotion
  - platform format
required_tools:
  - optional video generation tool
risk_level: Medium
stage_status: Stage A usable as planning-only skill
mob_owner:
  - Artisans
  - Provocateurs
agent_owner:
  - Director
  - Orator
playbook_fit:
  - Cinematic Promo Video Playbook
  - Product Showcase Video Playbook
  - Visual Intelligence Playbook
upgrade_needed:
  - separate planning-only mode from execution mode
  - add output schema
  - add examples by use case
status: Active After Adaptation
```

## 6. `seedance-2`

```yaml
name: seedance_2
source_path: library/motion/seedance-2/SKILL.md
hamal_class:
  - Process Skill
  - Integration Skill
category: Video Generation Engine Wrapper
purpose: Provide expert Seedance 2 prompting, mode selection, tier rules, camera grammar, audio direction, and generation syntax.
inputs:
  - director brief
  - tier
  - mode
  - reference images
  - reference audio
  - reference video where supported
  - duration
  - aspect ratio
outputs:
  - Seedance video request
  - request ID
  - generated video
  - execution syntax
required_context:
  - mode rules
  - media rights
  - face/identity restrictions
  - audio direction
  - output storage
required_tools:
  - muapi
  - bash scripts
  - curl
  - jq
risk_level: High
stage_status: Needs safe mode presets before Stage B
mob_owner:
  - Artisans
  - Vanguards
  - Guardians
agent_owner:
  - Director
  - Operator
playbook_fit:
  - Director-Level Video Production Playbook
  - Cinematic Promo Video Playbook
  - Product Showcase Video Playbook
upgrade_needed:
  - define HAMAL safe presets
  - block watermark removal until policy exists
  - require audio directive
  - require rights review
status: Upgrade First
```

## 7. `social-media-video`

```yaml
name: social_media_video
source_path: library/social/social-media-video/SKILL.md
hamal_class:
  - Process Skill
  - Output Skill
category: Brand-Aware Social Video Pipeline
purpose: Create platform-ready social videos from brand identity, ICP, messaging, storyboard, reference frames, and generation tools.
inputs:
  - brand-identity.md
  - ICP.md
  - messaging.md
  - campaign goal
  - platform
  - storyboard or prompt
  - references
outputs:
  - post copy
  - storyboard
  - reference frame prompts
  - director brief
  - video generation plan
  - platform-ready asset plan
required_context:
  - brand context contract
  - audience
  - offer
  - CTA
  - platform spec
  - rights policy
required_tools:
  - image generation
  - Seedance 2 or video generation
  - optional scheduler later
risk_level: High
stage_status: P1 upgrade target
mob_owner:
  - Artisans
  - Provocateurs
  - Strategists
agent_owner:
  - Director
  - Orator
  - Distributor
playbook_fit:
  - Social Video Campaign Playbook
  - Creator Content System Playbook
  - Business Pressure Test Campaign Playbook
  - Spark Lab Campaign Playbook
upgrade_needed:
  - split into planning, generation, review, distribution stages
  - add brand context contract
  - add human review gate
status: Upgrade First
```

## 8. `youtube-shorts`

```yaml
name: youtube_shorts
source_path: library/social/youtube-shorts/SKILL.md
hamal_class:
  - Output Skill
  - Wrapper Skill
category: Platform Preset
purpose: Create Shorts/TikTok/Reels-style clips by wrapping AI clipping with platform-specific defaults.
inputs:
  - source video
  - platform
  - clip count
  - aspect ratio
outputs:
  - short-form clips
  - timestamps
  - captions or title ideas
required_context:
  - platform specs
  - content rights
  - clip scoring rubric
required_tools:
  - ai-clipping
risk_level: High
stage_status: Merge or wrapper
mob_owner:
  - Artisans
  - Provocateurs
agent_owner:
  - Editor
  - Distributor
playbook_fit:
  - Long-Form Content Repurposing Playbook
  - Creator Content System Playbook
upgrade_needed:
  - mark as wrapper, not separate core skill
  - merge scoring logic with ai-clipping
status: Merge Candidate
```

## 9. `logo-creator`

```yaml
name: logo_creator
source_path: library/visual/logo-creator/SKILL.md
hamal_class:
  - Output Skill
  - Process Skill
category: Brand Identity Asset Generation
purpose: Generate logo concepts and image prompts from brand direction, style, color, and concept.
inputs:
  - brand name
  - brand concept
  - audience
  - style
  - color palette
  - usage context
outputs:
  - logo prompt
  - logo concept
  - image generation plan
required_context:
  - brand brief
  - trademark caution
  - design acceptance rubric
required_tools:
  - image generation
risk_level: Medium
stage_status: Usable after brand/rubric context
mob_owner:
  - Artisans
agent_owner:
  - Designer
playbook_fit:
  - Brand Asset Generation Playbook
  - MVP Visual Concepting Playbook
upgrade_needed:
  - add trademark guardrails
  - add logo acceptance rubric
  - add revision workflow
status: Upgrade First
```

## 10. `nano-banana`

```yaml
name: nano_banana
source_path: library/visual/nano-banana/SKILL.md
hamal_class:
  - Process Skill
  - Output Skill
category: High-Fidelity Image Prompting
purpose: Generate structured image prompts and/or images with subject, action, context, style, and text control.
inputs:
  - subject
  - action
  - context
  - style
  - text requirements
  - platform
outputs:
  - reasoning image prompt
  - generated image plan
  - image output reference
required_context:
  - creative brief
  - brand style
  - factual grounding
  - platform image rules
required_tools:
  - image generation model
risk_level: Medium / High
stage_status: Planning usable; execution later
mob_owner:
  - Artisans
  - Provocateurs
agent_owner:
  - Visual Designer
  - Director
playbook_fit:
  - Social Video Campaign Playbook
  - Brand Asset Generation Playbook
  - IG Grid Playbook
upgrade_needed:
  - add platform presets
  - add brand safety rules
  - add reference image handling policy
status: Active After Adaptation
```

## 11. `photo-pack-generator`

```yaml
name: photo_pack_generator
source_path: library/visual/photo-pack-generator/SKILL.md
hamal_class:
  - Output Skill
  - Evaluation Skill
category: Identity-Preserving Photo Pack
purpose: Generate personal brand photo packs while preserving likeness or identity from a reference face image.
inputs:
  - reference face image
  - category
  - count
  - style
  - usage context
outputs:
  - identity-preserving image prompts
  - photo pack plan
  - generated image set
required_context:
  - explicit consent
  - likeness policy
  - identity preservation rubric
  - prohibited-use policy
required_tools:
  - image generation model
risk_level: Critical
stage_status: Blocked until consent policy exists
mob_owner:
  - Artisans
  - Guardians
agent_owner:
  - Designer
  - Guardian
playbook_fit:
  - Founder / Personal Brand Media Pack Playbook
  - Legacy Vault Media Engine Playbook
upgrade_needed:
  - create consent checklist
  - create identity/likeness rubric
  - block public person impersonation
  - require human approval
status: Blocked
```

## 12. `ui-design`

```yaml
name: ui_design
source_path: library/visual/ui-design/SKILL.md
hamal_class:
  - Output Skill
  - Template Skill
category: UI Mockup / MVP Visual Concepting
purpose: Generate UI mockup prompts or visual concepts from a product brief, platform, theme, and style.
inputs:
  - product brief
  - platform
  - target user
  - theme
  - design style
outputs:
  - UI mockup prompt
  - screen concept
  - layout direction
required_context:
  - UX requirements
  - design system
  - user journey
  - brand style
required_tools:
  - image generation
  - optional design extraction tool later
risk_level: Medium
stage_status: Stage A usable for planning
mob_owner:
  - Artisans
  - Vanguards
agent_owner:
  - Designer
  - Architect
playbook_fit:
  - MVP Visual Concepting Playbook
  - App Architecture Playbook
  - Client System Blueprint Playbook
upgrade_needed:
  - add UX acceptance rubric
  - add handoff format for developers
  - add responsive/platform presets
status: Active After Adaptation
```

## 13. `workflow`

```yaml
name: workflow
source_path: library/workflow/SKILL.md
hamal_class:
  - Harness
  - Plugin
  - Integration Skill
category: Multi-Step Media Pipeline Harness
purpose: Create, run, edit, rename, delete, or execute media workflows.
inputs:
  - workflow prompt
  - workflow ID
  - inputs
  - execution approval
outputs:
  - node graph
  - workflow run
  - media outputs
  - logs
required_context:
  - execution approval
  - rollback policy
  - storage policy
  - human review gates
required_tools:
  - muapi workflow
  - possible MCP server
risk_level: Critical
stage_status: Blocked until Stage B
mob_owner:
  - Vanguards
  - Guardians
  - Artisans
agent_owner:
  - Operator
  - Guardian
playbook_fit:
  - AI Media Workflow Audit Playbook
  - Multi-Step Media Pipeline Playbook
upgrade_needed:
  - read-only inspection mode
  - workflow sandbox policy
  - approval gate before create/edit/delete/run
  - logging and rollback
status: Blocked
```

---

## Priority Map

### P1 — Upgrade First

- `social-media-video`
- `ai-clipping`
- `seedance-2`
- `logo-creator`
- `photo-pack-generator` policy wrapper

### P2 — Adapt Next

- `cinema-director`
- `nano-banana`
- `ui-design`
- `youtube-shorts` wrapper cleanup

### P3 — Stage B Only

- `core/media`
- `core/edit`
- `core/platform`
- `workflow`

## Skill Packaging Recommendation

Do not use this repo as one giant skill.

Package it into HAMAL skill packs:

```text
Generative Media Pack
├── Planning Skills
│   ├── cinema_director
│   ├── nano_banana
│   └── ui_design
├── Production Skills
│   ├── seedance_2
│   ├── core_media
│   └── core_edit
├── Repurposing Skills
│   ├── ai_clipping
│   └── youtube_shorts_wrapper
├── Brand Skills
│   ├── logo_creator
│   └── photo_pack_generator_guarded
└── Harnesses
    └── workflow_blocked_until_stage_b
```

## Next Context Files Required

1. `00_stage_a_foundation/media_rights_and_consent_policy.md`
2. `05_templates/brand_context_contract_template.md`
3. `07_rubrics/media_outputs/clip_quality_rubric.md`
4. `07_rubrics/media_outputs/social_video_quality_rubric.md`
5. `07_rubrics/media_outputs/logo_quality_rubric.md`
6. `07_rubrics/media_outputs/likeness_preservation_rubric.md`
7. `02_playbooks/content/social_video_campaign_playbook.md`
8. `02_playbooks/content/long_form_repurposing_playbook.md`
9. `02_playbooks/content/legacy_vault_media_engine_playbook.md`
