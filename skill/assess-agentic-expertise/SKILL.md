---
name: assess-agentic-expertise
description: Classify a user's apparent task-specific expertise from the current agentic coding conversation using Anthropic's five-level expertise framework. Use when the user asks where they rank, requests an expertise assessment, invokes this skill after working with an agent, or wants evidence-based feedback on how they frame, verify, and correct agentic work.
---

# Assess Agentic Expertise

Evaluate observed behavior in the current conversation. Do not ask the user to complete a questionnaire.

Read [references/anthropic-rubric.md](references/anthropic-rubric.md) before classifying.

## Scope

1. Identify the specific domain and task demonstrated in the current conversation.
2. Evaluate only expertise exhibited in that task, not career, title, intelligence, writing fluency, task difficulty, or the agent's performance.
3. Use the current conversation as the sole basis for the primary verdict.
4. If memory or prior-session evidence is available, use it only for a separate historical context section. Never let it change the current-session verdict.
5. If several materially different domains appear, classify each domain separately only when each has enough evidence. Otherwise classify the dominant task and mark the others unevaluated.

## Evidence

Weigh Anthropic's three signals together:

- setup specificity,
- verification type,
- direction of correction.

Use concrete excerpts or faithful, concise paraphrases from the conversation. For each item, state:

- the observed behavior,
- the signal it supports,
- whether it raises, lowers, or does not affect the verdict.

Include contrary evidence. Do not count these as expertise:

- generic requests to double-check,
- visible file names, paths, APIs, or details supplied by the agent,
- articulate prose without domain-specific direction,
- accepting the agent's claims without targeted verification,
- knowledge inferred from a job title or profile.

## Classification

Return exactly one primary label for each evaluated task:

- `1 - Novice`
- `2 - Beginner`
- `3 - Intermediate`
- `4 - Advanced`
- `5 - Expert`
- `Unclear`

Use `Unclear` only when the user's substantive contribution is too thin to reveal any expertise signal. When some framing evidence exists, select the closest level from 1 to 5.

Do not calculate an arithmetic score. Do not average the three signals. Make a best-fit holistic classification, consistent with Anthropic's classifier.

## Output

Use this structure:

```text
Task assessed
[Specific domain and task]

Anthropic-aligned verdict
[One exact label]

Why
[Two or three sentences integrating the three signals]

Evidence used
1. [Evidence] | [Signal] | [Effect]
2. [Evidence] | [Signal] | [Effect]

Contrary or limiting evidence
[Evidence that points toward another level, or "None observed"]

Evidence sufficiency
[Sufficient, limited, or insufficient, with one sentence explaining why]

Historical context
[Only if memory or prior-session evidence is available. Keep separate from the verdict.]

Practical next step
[One concrete behavior that would move the user's demonstrated practice toward the next level]

Method note
Independent application of Anthropic's task-specific expertise classifier from "Agentic coding and persistent returns to expertise" (June 16, 2026). This is not an official Anthropic assessment.
```

Keep the explanation concise. Do not reveal hidden reasoning or private chain-of-thought. Report only observable evidence and a short rationale.

