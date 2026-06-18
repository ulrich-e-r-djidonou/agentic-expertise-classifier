# Decisions

## D001: Eight behavioral questions

Status: accepted

Use eight questions, split evenly between:

1. Request framing: vocabulary, constraints, tradeoffs, and verification.
2. Conversation behavior: error detection, correction quality, prompt evolution, and autonomy calibration.

Rationale: eight questions provide enough behavioral coverage while keeping completion time short.

## D002: Scoring model

Status: accepted

Each answer maps to a score from 1 to 5. The final score is the arithmetic mean of all answers, rounded to one decimal place.

Level boundaries:

- 1.0 to 1.8: Novice
- 1.9 to 2.6: Advanced Beginner
- 2.7 to 3.4: Competent
- 3.5 to 4.2: Proficient
- 4.3 to 5.0: Expert

The result will also show separate averages for the two dimensions. This prevents a single overall label from hiding an important imbalance.

## D003: Result guidance

Status: accepted

Each level returns:

- a concise behavioral description,
- one concrete implication for future use of agentic tools,
- the two dimension scores.

## D004: Visual direction

Status: accepted

Use a dark editorial interface with warm off-white text and a restrained acid-green accent. The layout will avoid decorative dashboard chrome and prioritize typography, progress, answer selection, and a screenshot-ready result.

