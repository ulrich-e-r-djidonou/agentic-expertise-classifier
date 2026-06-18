# Anthropic expertise rubric

Source:

- Anthropic, "Agentic coding and persistent returns to expertise", June 16, 2026
- Report: https://www.anthropic.com/research/claude-code-expertise
- Appendix: https://cdn.sanity.io/files/4zrzovbb/website/ef87578c3828dc79d711f6d9c52eff39ac4e3be0.pdf

This file summarizes the published classifier. Consult the official appendix when exact wording matters.

## Construct

Classify apparent expertise exhibited in the specific domain and task of the session. Do not classify general ability, profession, task difficulty, or agent performance.

Return one classification for the session's primary task. Do not create a multi-domain profile in the primary assessment.

## Co-equal signals

### Setup specificity

Assess whether the user frames the work with domain knowledge that is not simply visible in the interface or repository. Strong evidence includes non-obvious constraints, invariants, edge cases, conventions, failure modes, and practitioner terminology.

File names, paths, visible APIs, and details supplied by the agent do not by themselves demonstrate domain expertise.

### Verification type

Assess what the user chooses to verify.

- Generic checking shows caution, not expertise.
- Targeted checking shows knowledge of the weak point, state, mechanism, invariant, or failure mode that matters.

### Direction of correction

Assess who corrects whom on domain matters.

- Agent correction of the user's terminology, model, or approach lowers the classification.
- User detection of the agent's domain error, with technically grounded redirection, raises it.
- No correction in either direction is neutral.

## Levels

### 1 - Novice

Framing is generic or imprecise. Domain terminology and targeted verification are absent. The agent supplies or corrects basic concepts, and the user does not detect incorrect output.

### 2 - Beginner

Some terminology is correct but loose. Goals are specified at a high level without important constraints or invariants. Verification is mostly generic. The user may catch obvious problems, while the agent still corrects parts of the user's domain model.

### 3 - Intermediate

Directions are operationally precise, but methodology and tradeoffs are mostly implicit. Verification mixes generic and targeted checks. The user catches meaningful errors, but neither participant consistently corrects the other on domain matters.

### 4 - Advanced

Framing demonstrates structural domain knowledge through a non-obvious constraint, edge case, invariant, version behavior, or known failure mode. Verification or correction targets a specific mechanism. The user catches at least one domain mistake or redirects a wrong approach without needing their domain model corrected.

### 5 - Expert

The user speaks and steers like a practitioner working with an equal. Evidence may include insider terminology, unprompted tradeoff analysis, surgical verification, authoritative correction using specific technical reasoning, preemptive edge-case handling, or tests aimed at known failure modes. One or two strong signals can be enough. On domain matters, correction runs from user to agent, not the reverse.

### Unclear

Use only when the user's substantive contribution is so limited that no direction-of-expertise signal exists. If any meaningful framing exists, choose the closest level from 1 to 5.

## Adaptation boundaries

The following are useful additions but are not outputs of Anthropic's published classifier:

- evidence sufficiency wording,
- historical context from memory,
- separate domain profiles across sessions,
- practical improvement advice.

Keep these additions visibly separate from the primary classification.
