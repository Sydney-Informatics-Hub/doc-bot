# doc-bot

AI-assisted authoring kit for Australian BioCommons how-to guides. This repo provides two context files that you load into an AI assistant at the start of each writing session so it produces guide drafts that match BioCommons template conventions without manual correction.

**Note:** This repo is being tested ahead of conversion to an MCP server. For now, use the manual paste workflow described below.

## Files in this repo

| File | What it is | How to use it |
|------|-----------|---------------|
| `llm.txt` | Full BioCommons template conventions — structure, section order, callout syntax, figure syntax, registry linking rules, and a closing checklist | Paste into the AI as the first message of every session |
| `GUIDE_CONTEXT.md` | A form you fill in before each session — guide title, tool name, target platform, audience, scope, registry metadata, authors, and session goals | Fill in, then paste as the second message of every session |
| `AI_AUTHORING.md` | Step-by-step instructions for running an AI-assisted guide writing session | Read this before your first session |

## Quickstart

1. **Fork this repo** (or copy the files into your guide template repo)
2. **Fill in `GUIDE_CONTEXT.md`** — title, tool name, and target platform are the minimum required fields; write `Not yet known` for anything else
3. **Open a new AI conversation** (Claude, ChatGPT, Copilot, Gemini — any chat interface works)
4. **Paste `llm.txt`** as message 1:
   > I'm writing a BioCommons how-to guide. Use the conventions in the following file for everything you help me produce today.
   > `<paste llm.txt contents>`
5. **Paste your filled-in `GUIDE_CONTEXT.md`** as message 2:
   > Here is the context for the specific guide I'm writing today.
   > `<paste GUIDE_CONTEXT.md contents>`
6. **Confirm the AI understood both files**, then start with the skeleton:
   > Generate the Quick Start checklist and workflow summary table. Do not write any prose yet.
7. **At the end of every session**, run the closing checklist:
   > Run the closing checklist from the BioCommons llm.txt against the guide we have written today and tell me what is missing or incomplete.

Full session guidance, multi-session workflow, troubleshooting, and AI limitations are documented in [AI_AUTHORING.md](./AI_AUTHORING.md).

## What the AI can and cannot do

| Can do | Cannot do |
|--------|-----------|
| Generate guide structure and prose in BioCommons markdown format | Take screenshots. You must capture all figures |
| Insert figure placeholders with capture instructions | Supply registry DOIs or IDs. Always insert placeholders for you to fill |
| Propose workflow summary tables | Verify command syntax. Always test commands yourself |
| Flag missing sections via the closing checklist | Look up current platform docs. Paste relevant excerpts into the session if needed |
| Convert existing drafts to BioCommons template format | Look up ORCID or GitHub handles. Supply these yourself |

## Related resources

- [BioCommons guide template](https://australianbiocommons.github.io/how-to-guide-template/)
- [How-to Hub (existing guides)](https://australianbiocommons.github.io/how-to-hub/)
- [BioCommons documentation guidelines](https://github.com/AustralianBioCommons/doc_guidelines)
- [Guide template GitHub repo](https://github.com/AustralianBioCommons/guide-template)
