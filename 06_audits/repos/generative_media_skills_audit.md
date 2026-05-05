# Generative Media Skills Audit

## Repo

- HAMAL fork: `MajorDream444/Generative-Media-Skills`
- Upstream reference: `SamurAIGPT/Generative-Media-Skills`
- Local audit source: `/Users/majordreamwilliams/LocalProjects/Generative-Media-Skills`
- Source branch: `main`
- Latest local commit from audit: `2c3c018`
- Stage: Stage A — inspect only

## Stage A Boundary

This audit inspected files only.

No scripts, tools, APIs, MCPs, workflows, or automations were executed.

## Summary

`Generative-Media-Skills` is a high-value media skill library for HAMAL.

It contains core generation/edit/platform primitives plus library skills for clipping, cinematic direction, Seedance 2, social media video, YouTube Shorts, logo creation, Nano Banana image prompting, photo pack generation, UI design, and workflow orchestration.

This repo should become the base of the HAMAL Generative Media Department Pack.

Primary MOB owner: Artisans.

Secondary MOB owners: Provocateurs, Vanguards, Strategists, Guardians.

## Repo Tree Summary

```text
Generative-Media-Skills/
├── README.md
├── schema_data.json
├── media_outputs/
├── core/
│   ├── media/
│   ├── edit/
│   └── platform/
└── library/
    ├── edit/ai-clipping/
    ├── motion/cinema-director/
    ├── motion/seedance-2/
    ├── social/social-media-video/
    ├── social/youtube-shorts/
    ├── visual/logo-creator/
    ├── visual/nano-banana/
    ├── visual/photo-pack-generator/
    ├── visual/ui-design/
    └── workflow/
```

## Markdown / Skill Files

```text
README.md
core/edit/SKILL.md
core/media/SKILL.md
core/platform/SKILL.md
library/edit/ai-clipping/SKILL.md
library/motion/cinema-director/SKILL.md
library/motion/seedance-2/SKILL.md
library/social/social-media-video/SKILL.md
library/social/youtube-shorts/SKILL.md
library/visual/logo-creator/SKILL.md
library/visual/nano-banana/SKILL.md
library/visual/photo-pack-generator/SKILL.md
library/visual/ui-design/SKILL.md
library/workflow/SKILL.md
```

## Skill Inventory

| Item | HAMAL Class | What It Does | Risk | Playbook Fit |
|---|---|---|---|---|
| `core/media` | Tool / Integration Skill | Media generation primitives for image, video, audio request outputs | High | Media Asset Generation |
| `core/edit` | Tool / Integration Skill | Edit and enhance media assets | High | Media Enhancement |
| `core/platform` | Tool / Harness | Auth, setup, polling, result utilities | High / Blocked Stage A | Tool Readiness |
| `ai-clipping` | Output / Integration Skill | Turns long video into ranked clips with timestamps and scores | High | Long-Form Repurposing |
| `cinema-director` | Process / Output Skill | Converts creative intent into cinematic director prompts | Medium / High | Cinematic Promo Video |
| `seedance-2` | Process / Integration Skill | Seedance 2 expert wrapper for video generation modes and tiers | High | Director-Level Video Production |
| `social-media-video` | Process / Output Skill | Brand-aware social video pipeline using brand identity, ICP, messaging, storyboard, reference frames, and video generation | High | Social Video Campaign |
| `youtube-shorts` | Output Skill | Platform wrapper for shorts-style clipping | High | Shorts / Reels Repurposing |
| `logo-creator` | Output / Process Skill | Generates logo prompts/assets from brand concepts | Medium / High | Brand Identity Asset Generation |
| `nano-banana` | Process / Output Skill | High-fidelity image prompt/image generation | Medium / High | Image Generation |
| `photo-pack-generator` | Output / Evaluation Skill | Identity-preserving photo pack generation | Critical / Blocked Until Consent Policy | Founder / Personal Brand Media Pack |
| `ui-design` | Output / Template Skill | UI mockup generation from product brief and theme | Medium / High | MVP Visual Concepting |
| `workflow` | Harness / Plugin / Integration Skill | Creates and executes multi-step media workflows | Critical / Blocked Stage A | Multi-Step Media Pipeline |

## Duplicate / Wrapper Notes

- `youtube-shorts` overlaps with `ai-clipping`; treat as a platform preset wrapper.
- `cinema-director` overlaps with `seedance-2`; treat Cinema Director as model-agnostic parent and Seedance 2 as model-specific child.
- `social-media-video` bundles `seedance-2`, `nano-banana`, and `core/media`; split into context, storyboard, reference generation, execution, and review gates.
- `workflow` can execute, rename, delete, and run media workflows; block until Stage B.
- `photo-pack-generator` requires consent, likeness, identity, and prohibited-use policy before any operational use.
- `core/platform` touches credentials and polling; useful later, not Stage A-safe.

## Top 5 Skills To Upgrade First

1. `social-media-video`
   - Best fit for HAMAL campaign playbooks.
   - Needs brand context contracts and review gates.

2. `ai-clipping`
   - Cleanest production-shaped output schema.
   - Needs clip scoring rubric and content-rights context.

3. `seedance-2`
   - Strong technical reference.
   - Needs safe modes and HAMAL presets.

4. `logo-creator`
   - Useful for brand packages.
   - Needs brand brief template, trademark guardrails, and acceptance rubric.

5. `photo-pack-generator`
   - High-value but highest safety risk.
   - Add consent, likeness, identity, and prohibited-use context first.

## Recommended HAMAL Playbooks

- Brand Asset Generation Playbook
- Social Video Campaign Playbook
- Long-Form Content Repurposing Playbook
- Founder / Personal Brand Media Pack Playbook
- Product Showcase Video Playbook
- Cinematic Promo Video Playbook
- UI Mockup / MVP Concept Visual Playbook
- Media Enhancement And Cleanup Playbook
- AI Media Workflow Audit Playbook
- Legacy Vault Media Engine Playbook

## Required Context To Add Before Operational Use

- HAMAL media rights and consent policy
- MuAPI tool/API/MCP risk classification
- Credential policy for `MUAPI_KEY` / `MUAPI_API_KEY`
- Output storage rules for generated media, JSON, request IDs, and clip URLs
- Brand context contract requiring `brand-identity.md`, `ICP.md`, and `messaging.md`
- Platform specs for Shorts, TikTok, Reels, LinkedIn, YouTube, Instagram
- Quality rubrics for clips, logos, UI mockups, cinematic video, social video, and likeness preservation
- Human review gates before publishing, downloading, uploading, face/identity generation, or workflow execution
- Stage B prerequisites for any `muapi workflow`, `muapi mcp serve`, API calls, or script execution
- Duplicate/wrapper policy for skills that merely preset another skill

## HAMAL Status

```yaml
name: Generative-Media-Skills
source_type: GitHub repo
source_repo: https://github.com/MajorDream444/Generative-Media-Skills
original_repo: https://github.com/SamurAIGPT/Generative-Media-Skills
fork_status: fork/reference repo
category:
  - Skill Library
  - Media / Creative
  - Output Skill
  - Process Skill
  - Integration Skill
summary: Generative media skill library for image, video, clipping, social video, visual design, logo, photo pack, Seedance 2, and workflow orchestration.
required_context:
  - brand identity
  - ICP
  - messaging
  - media rights
  - platform spec
  - quality rubric
required_tools:
  - muapi
  - curl
  - jq
  - python3
required_mcps:
  - optional media MCP
  - optional workflow MCP
  - optional GitHub MCP
agent_owner:
  - Director
  - Orator
  - Operator
mob_owner:
  - Artisans
  - Provocateurs
  - Vanguards
playbooks:
  - Social Video Campaign Playbook
  - Visual Intelligence Playbook
  - Legacy Vault Media Engine Playbook
risk_level: High
status: Review Needed / P1
last_reviewed: 2026-05-06
```

## Next Actions

1. Create `06_audits/skills/generative_media_skill_inventory.md`.
2. Create HAMAL media rights and consent policy.
3. Create media output rubrics.
4. Create Brand Context Contract.
5. Create Social Video Campaign Playbook.
6. Create Legacy Vault Media Engine Playbook.
7. Keep upstream `main` clean and build HAMAL adaptations on a branch.
