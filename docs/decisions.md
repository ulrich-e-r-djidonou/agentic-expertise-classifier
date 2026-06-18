# Decisions

## D001: Conversation evidence instead of a questionnaire

Status: accepted

The product will not ask users to self-report behavior through multiple-choice questions. The skill will evaluate behavior already observed in the current conversation.

Rationale: Anthropic's classifier reads complete session transcripts. A questionnaire would measure self-perception rather than demonstrated expertise.

## D002: Anthropic classification model

Status: accepted

Use one holistic best-fit verdict for the specific task:

- 1 - Novice
- 2 - Beginner
- 3 - Intermediate
- 4 - Advanced
- 5 - Expert
- Unclear

Do not calculate averages or weighted sub-scores. Anthropic describes three co-equal signals that must be considered together.

## D003: Evidence and result

Status: accepted

Each evaluation returns:

- the specific task and domain assessed,
- one Anthropic-aligned verdict,
- concrete evidence from the conversation,
- contrary or limiting evidence,
- evidence sufficiency,
- one practical next step.

## D004: Visual direction

Status: accepted

Use a dark editorial interface with warm off-white text and a restrained acid-green accent. The page explains the skill, method, levels, example output, and installation without presenting an interactive questionnaire.

## D005: Anthropic research basis

Status: accepted

The assessment is adapted from Anthropic's June 16, 2026 report, [Agentic coding and persistent returns to expertise](https://www.anthropic.com/research/claude-code-expertise).

The report's classifier uses three principal signals:

1. precision in how the user frames directions,
2. what the user asks Claude to verify,
3. whether the user corrects Claude or Claude corrects the user.

This skill applies those transcript-level observations directly to the current conversation. It must be described as an independent adaptation, not as an official or validated Anthropic assessment.

## D006: Current session versus memory

Status: accepted

The primary verdict uses only the current conversation, consistent with Anthropic's session-level construct.

If memory or prior-session evidence is accessible, it can appear only as a separately labeled historical context section. It cannot modify the primary verdict.

## D007: Domain specificity

Status: accepted

Classify expertise for the task at hand, not for the person globally. If multiple domains are present, classify them separately only when each has sufficient evidence.
