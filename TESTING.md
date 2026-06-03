# Testing doc-bot efficacy

This document describes a standardised method for evaluating whether the files in this repo produce consistent, useful, and correctly formatted BioCommons guide drafts across different AI assistants and guide types. Feel free to take a different approach, this was the best I could come up with. 

## Before you start

You will need:

- An AI assistant with a chat interface. Test with at least one of: Claude, ChatGPT, Gemini, GitHub Copilot Chat
- A copy of this repository (fork or download)
- A real or realistic guide topic to use as your test case (see suggested scenarios below)
- 30–60 minutes per test run


## Step 1: Fill in `GUIDE_CONTEXT.md`

Open `GUIDE_CONTEXT.md` and fill it in for your chosen scenario. Use realistic but minimal values, you do not need to have every answer. For anything unknown, write `Not yet known`.

Before moving on, note:
- Were any fields confusing or ambiguous?
- Were any fields missing that you expected to see?
- Were any fields irrelevant to your scenario?

## Step 2: Run the AI session

Open a new conversation with your AI assistant. Follow the session steps from [AI_AUTHORING.md](./AI_AUTHORING.md) exactly as written, sending each message in order and waiting for a response before continuing.

Run through to the end of Step 3 (skeleton generation) at minimum. If time permits, continue through to a full first-section draft.

**Record how long the session takes** from pasting `llm.txt` to having a skeleton you are satisfied with.

## Step 3: Evaluate the output

Score each item below on a 1–3 scale:

- **1** if did not meet expectation (wrong, missing, or required significant correction)
- **2** if partially met (present but needed minor correction)
- **3** if met expectation without correction needed

### Structure and conventions

| # | Check | Score (1–3) | Notes |
|---|-------|-------------|-------|
| 1 | Guide sections appear in the correct order (Introduction → Quick Start → How to cite → Workflow → In-depth steps → Acknowledgements → References) | | |
| 2 | Quick Start checklist is present and numbered | | |
| 3 | Workflow summary table has the correct columns: Process \| Workflow \| Description \| Inputs \| Outputs | | |
| 4 | Callout boxes use correct blockquote syntax (`> **Note:**`, `> **Warning:**`, etc.) | | |
| 5 | Code blocks have language identifiers (` ```bash `, ` ```yaml `, etc.) | | |
| 6 | Figure placeholders are inserted with captions describing what to capture | | |
| 7 | Registry link placeholders are clearly labelled (not invented DOIs) | | |

### Tone and style

| # | Check | Score (1–3) | Notes |
|---|-------|-------------|-------|
| 8 | Second person used throughout ("you", "your") | | |
| 9 | Steps are imperative ("Click", "Select", "Run") | | |
| 10 | Tool names are in backticks | | |
| 11 | Output reads like a BioCommons guide, not generic documentation | | |

### Context files

| # | Check | Score (1–3) | Notes |
|---|-------|-------------|-------|
| 12 | The AI correctly reflected the target platform in its output (right scheduler, right UI) | | |
| 13 | The AI respected the scope boundaries from `GUIDE_CONTEXT.md` | | |
| 14 | The AI used the audience description to calibrate assumed knowledge | | |

**Total score: __ / 42**

## Step 4: Assess overall usability

Answer the following questions in a few sentences each:

1. **How long did filling in `GUIDE_CONTEXT.md` take?** Was it faster or slower than you expected?

2. **How many corrections did you need to make to the AI output?** Were they minor (wording, formatting) or structural (wrong sections, wrong conventions)?

3. **Did you need to re-prompt the AI to apply the conventions?** If so, at what point in the session?

4. **How does this compare to writing the guide without these context files?** (If you have done this before — even a rough estimate is useful.)

5. **Were there any moments where the instructions in `AI_AUTHORING.md` were unclear or missing guidance you needed?**

6. **Which AI assistant did you use?** Did you notice any meaningful differences if you tested more than one?

## Step 5: Note specific failures

For each item you scored 1 or 2, copy the AI output that caused the issue and describe what was wrong. This is the most useful feedback for improving the context files.

Example format:

> **Check 4 — callout syntax**
> AI produced: `**Note:** Check your allocation before running.`
> Expected: `> **Note:** Check your allocation before running.`
> Likely cause: convention not prominent enough in llm.txt
