# Assess Agentic Expertise

An installable skill that classifies the task-specific expertise a user demonstrates while working with an agentic coding tool. It evaluates the current conversation, cites the evidence used, and returns one of five levels or `Unclear`.

The skill is independently adapted from Anthropic's report [Agentic coding and persistent returns to expertise](https://www.anthropic.com/research/claude-code-expertise), published June 16, 2026, and its [methodological appendix](https://cdn.sanity.io/files/4zrzovbb/website/ef87578c3828dc79d711f6d9c52eff39ac4e3be0.pdf). It is not an official or validated Anthropic classifier.

## Stack

- Skill instructions in Markdown
- Static HTML, embedded CSS, and vanilla JavaScript
- No backend or build step

## Use

Install the folder [`skill/assess-agentic-expertise`](skill/assess-agentic-expertise) in the skills directory supported by your agentic coding tool.

Invoke it after or during a substantive conversation:

```text
Use $assess-agentic-expertise to classify my task-specific expertise from this conversation.
```

The primary verdict uses only the current conversation. Memory or prior-session evidence may appear in a separate historical context section, but it cannot change the session-level verdict.

## Deployment

The public explanatory page is a single `index.html` deployed to Netlify.

## Documentation

- [Project log](docs/project-log.md)
- [Decisions](docs/decisions.md)
