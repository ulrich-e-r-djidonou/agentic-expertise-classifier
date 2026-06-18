# Project log

## 2026-06-18

### Project initialization

- Initially explored a static self-assessment for agentic coding expertise.
- Selected HTML, embedded CSS, and vanilla JavaScript.
- Selected Netlify as the deployment target.

### Product correction

- Rejected the questionnaire approach because it measures self-perception rather than observed behavior.
- Reframed the product as an installable skill that reads the current conversation.
- Kept the static site as public documentation for the skill.

### Anthropic alignment

- Identified the source as Anthropic's [Agentic coding and persistent returns to expertise](https://www.anthropic.com/research/claude-code-expertise), published June 16, 2026.
- Retrieved and reviewed the official [methodological appendix](https://cdn.sanity.io/files/4zrzovbb/website/ef87578c3828dc79d711f6d9c52eff39ac4e3be0.pdf).
- Aligned the five labels with the report: Novice, Beginner, Intermediate, Advanced, and Expert.
- Added the `Unclear` outcome for sessions with no substantive expertise signal.
- Preserved the three co-equal signals: setup specificity, verification type, and direction of correction.
- Excluded title, writing fluency, visible file names, generic verification, task difficulty, and agent performance from the construct.
- Defined the current conversation as the sole source of the primary verdict.
- Defined memory as separate historical context only.

### Outputs created

- `skill/assess-agentic-expertise/SKILL.md`
- `skill/assess-agentic-expertise/references/anthropic-rubric.md`
- `skill/assess-agentic-expertise/agents/openai.yaml`
- `index.html`

### Next step

Validate the skill structure, test the website on desktop and mobile, commit, push, and deploy to Netlify.

### Validation

- Skill structure validated with the official `quick_validate.py` utility.
- Embedded JavaScript parsed successfully.
- Desktop page reviewed at the default 1280 x 720 browser viewport.
- Mobile page reviewed at 390 x 844.
- No horizontal overflow or browser console errors detected.
- Copy-prompt behavior tested, including the fallback used when the Clipboard API is unavailable.

### Anthropic fidelity correction

- Restricted each invocation to one primary task and one verdict.
- Removed the option to produce concurrent domain classifications from a single session.
- Other observed domains may be mentioned only as scope limitations.
