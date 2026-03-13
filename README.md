# Installation
**Via Clawdhub:**
```bash
clawdhub install research-planner
```
**Manual Installation:**
```bash
npx skills add https://github.com/NKZ55/research-planner/tree/main/skills/research-planner
```


# Research Planner Skill

Market and user research **planning** skill for Claude-style agents.  
This skill helps design research projects (methods + materials), but **does not analyze data**.

## Inspiration and related work

This skill is strongly inspired by:

- Neal Caren’s **social‑data‑analysis** marketplace, especially the phased, methodical design of skills like `interview-analyst` (`https://github.com/nealcaren/social-data-analysis`).
- Odette Jansen’s public **UX research templates** in Figma/FigJam and Notion, and her emphasis on reusable research plans, boards, and protocols (`https://odettejansen.nl/ux-research-templates/`).

The goal is to bring similarly systematic, template‑driven workflows to research **planning** (methods + artifacts), while delegating analysis to specialized skills.

## What this skill does

- Clarifies research goals, decisions, users, and constraints.
- Chooses appropriate methods (interviews, usability tests, surveys, diary studies, etc.).
- Produces execution‑ready artifacts:
  - Research plans and stakeholder kickoffs.
  - Recruitment screeners and invitations.
  - Interview / focus group guides.
  - Usability test scripts and RITE plans.
  - Surveys and customer‑satisfaction questionnaires.
  - Templates for diary studies, contextual inquiry, card sorting, tree testing, journey maps, personas, Kano, A/B tests, and more.

**Out of scope:** data collection, analysis, and reporting. Those should be handled by dedicated analysis skills (e.g., qualitative/quantitative analysis skills like the `social-data-analysis` library).

## Repository layout

Target structure for the GitHub repository:

```text
research-planner
├── .claude-plugin/
│   └── marketplace.json
├── skills/
│   └── research-planner/
│       ├── phases/
│       ├── templates/
│       └── SKILL.md
├── LICENSE
└── README.md
```

In this Cursor workspace you are currently inside the inner `skills/research-planner/` directory.
When publishing to GitHub, create a repo root directory (e.g., `research-planner`) and place this
`skills/research-planner/` directory under it, alongside `.claude-plugin/`, `LICENSE`, and this `README.md`.

## Installing the skill locally

Once published to GitHub, a typical installation flow will look like:

```bash
git clone https://github.com/NKZ55/research-planner.git
cp -R research-planner/skills/research-planner ~/.agents/skills/research-planner
```

Or, if your environment already expects a `skills/` subdirectory, point it directly at the cloned repo.

## Using the skill

The skill should trigger when users ask for things like:

- “Plan a user research study for…”
- “Help me design an interview + usability test for…”
- “Draft a screener + survey for…”
- “Create a research plan and materials for…”

High‑level usage pattern:

1. The agent uses **Phase 1–3** files in `phases/` to structure the workflow.
2. For the chosen methods, the agent reads the relevant files in `templates/` to decide structure and output format.
3. The agent generates tailored plans and materials, but defers all **analysis** to separate analysis/reporting skills.

