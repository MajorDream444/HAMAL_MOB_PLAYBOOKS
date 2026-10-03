# Substack OS — 90-Day Implementation Plan
Owner: Major Dream Williams. Created October 3, 2026. Pilot: October 3, 2026–January 1, 2027. Timezone: Asia/Makassar (Bali).

## Mission
Grow a relevant audience, deepen reader relationships and validate monetization. Use Substack as the primary publication/community front door to MAIM and AMA. Preserve Mission Control authority. This is a playbook and skill release, not live publishing integration.

## Trigger and inputs
Run Tuesday and Friday at 10:00 Bali time. Input current drafts, raw source, published URLs, analytics exports, reader evidence and previous experiment log. If metrics are missing, explicitly record missing rather than zero. Recurring ChatGPT review is scheduled separately; it does not run repository agents or install skills automatically.

## Owners and output
Major: editorial judgment, reader conversations, offer commitments and final approval. Editor: positioning/voice/articles. Growth Scout: reader listening/Notes. Analyst: experiments. Handoff operator: reviewed artifacts. These are roles, not provisioned autonomous agents.
Store reusable skills in HAMAL_MOB_PLAYBOOKS/02_playbooks/substack-os/skills. Engine artifacts belong in SUBSTACK-AUTOMATION-ENGINE under its current contract. Global decisions belong in Mission Control. Keep private reader data and raw personal sources out of public GitHub.

## Initial cadence hypothesis
Start with one substantial free article weekly, four original Notes spread across the week and one genuine community question. Tuesday chooses the experiment; Friday reviews. Major approves publication and replies. Add a second article or live session only when workload and reader evidence support it. Do not optimize for volume alone.

## First eight skills
Publication Positioning; Major Voice & Doctrine; Reader Listening; Substack Article Editor; Notes Growth Studio; Subscriber Conversion; Growth Experiment Analyst; Mission Control Handoff.
Each folder includes SKILL.md, agents/openai.yaml, operating context and evaluation prompts. ChatGPT skills are installed separately. For another agent runtime, copy the selected complete folder into its documented skills location. Do not assume registering files creates execution adapters.

## Week-by-week rollout
| Week | Dates | Focus | Completion evidence |
|---|---|---|---|
| 1 | Oct 3–9 | First eight; positioning; baseline; welcome draft | Skills validated; baseline export or missing-data list; one approved packet |
| 2 | Oct 10–16 | Raw Thought Intake; Evidence & Claims Review; Editorial Series Planner; Reaction Doctrine Analyst | Raw archive preserved; claim ledger; two-week editorial plan |
| 3 | Oct 17–23 | Headline & Opening Lab; Publication Navigation; Distribution Adapter | Tested opening variants; start-here draft; one article adaptation |
| 4 | Oct 24–30 | Recommendations & Collaboration Scout; Reader Referral Designer | Relevant shortlist and draft; referral fulfillment costs and proposal |
| 5 | Oct 31–Nov 6 | Community Conversation Host; Live Session Producer | Community needs summary; first live agenda; day-30 review |
| 6 | Nov 7–13 | Podcast & Audio Editor; Paid Membership Architect | Audio pilot; explicit member promise, owner and workload |
| 7 | Nov 14–20 | Paid Resource Builder; AMA Opportunity Router | Useful resource tested with readers; qualification rubric |
| 8 | Nov 21–27 | Member Retention Analyst; Audience Portability | Reader feedback; export/recovery checklist; limited offer test if ready |
| 9 | Nov 28–Dec 4 | Sponsorship & Partner Fit; day-60 review | Evidence-backed media-kit draft; revenue/workload review |
| 10 | Dec 5–11 | Archive Productizer | A thematic collection with rights/source review and demand evidence |
| 11 | Dec 12–18 | Localization Editor | One localized pilot reviewed by a fluent reader |
| 12 | Dec 19–25 | Harden strongest workflows | Regression evaluation and documented revisions |
| 13 | Dec 26–Jan 1 | Day-90 assessment and next-quarter plan | Keep/change/stop decisions; retention/revenue evidence and uncertainties |

Build all 28 audited skills over the pilot; activate new workflows according to evidence and capacity. Creative series are experiments, not simultaneous launch commitments: MAIM Mornings, The System Underneath, From Worker to Ownership, Build With Major, Vibes to Systems, The Diaspora Desk, One Problem One Mob, The Living Book, The Reader’s Boardroom and The 144 Dispatch. Choose one flagship and one supporting series initially.

## Review SOP
Tuesday: inspect latest evidence; pick one reader problem, one primary experiment and content destinations; assign owners; record a skill gap and acceptance criteria if justified.
Friday: compare aligned observations; log keep/change/stop or extend; review quality/workload; test skill revisions before activation. Deliver scorecard, evidence limits, experiment decision, proposed skill change and next actions.
Formal checkpoints: November 2 (day 30), December 2 (day 60), January 1 (day 90). Review at the next scheduled session if the checkpoint falls between sessions. Ninety days improves observation but does not guarantee reliable causal feedback or monetization.

## Measurement
Capture starting and ending followers, free and paid subscribers separately; gross new subscriptions, unsubscribes/cancellations when available; acquisition source; meaningful replies; link clicks; eligible upgrade denominator; subscription revenue; fees/refunds; external AMA revenue separately; fulfillment hours. Avoid adding overlapping free/paid totals without understanding exports. Net change is not gross acquisition; unchanged paid count is not proof of no churn. Conversion requires aligned eligible cohorts. No speculative revenue targets before baseline.

## Promotion gates
Release a skill after metadata validation, normal/missing-data/adversarial task checks and documented limitations. Activate live workflow only after its integration adapter and Mission Control contract are verified. Paid offers require credible recurring benefits, owner, capacity and reader validation. New publishing integrations require current repo status and end-to-end dry-run evidence. Approval is not inferred from a score.

## Day-90 decisions
Which audience returns? Which series earns replies and subscribers? Which paid benefit is used and renewed? Which AMA inquiries are qualified? What is the delivery cost? Retain effective skills, revise weak ones, retire unsupported experiments and set the next quarter from evidence.
