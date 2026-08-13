# doc-bot

AI-assisted authoring kit for documentation that matches Australian BioCommons conventions. This repo provides context files that you load into an AI assistant at the start of a session so it produces drafts that match the target template without manual correction.

## Which files to use

doc-bot supports two documentation types. Pick the folder that matches what you're writing,
each is self-contained and used the same basic way (paste conventions, paste context, work
section by section, run a closing checklist).

| I'm writing... | Use folder | Target output |
|---|---|---|
| A BioCommons how-to guide for a service (e.g. BioShell) | [`service/`](./service) | A guide repo built from the [BioCommons guide template](https://australianbiocommons.github.io/how-to-guide-template/) |
| A README for a Nextflow workflow built from the SIH template | [`workflow/`](./workflow) | The workflow's own `README.md` |

---

## `service/` — BioCommons how-to guides

| File | What it is | How to use it |
|------|-----------|---------------|
| [`service/llm.txt`](./service/llm.txt) | Full BioCommons template conventions — structure, section order, callout syntax, figure syntax, registry linking rules, and a closing checklist | Paste into the AI as the first message of every session |
| [`service/SERVICE_CONTEXT.md`](./service/SERVICE_CONTEXT.md) | A form you fill in before each session — guide title, tool name, target platform, audience, scope, registry metadata, authors, and session goals | Fill in, then paste as the second message of every session |

Full session guidance, multi-session workflow, troubleshooting, and AI limitations for this
pack are documented in [AI_AUTHORING.md](./AI_AUTHORING.md). Read that before your first
session, and see [TESTING.md](./TESTING.md) for how to evaluate the output.

### Quickstart

1. **Fork this repo** (or copy `service/llm.txt` and `service/SERVICE_CONTEXT.md` into your guide template repo)
2. **Fill in `service/SERVICE_CONTEXT.md`** — title, tool name, and target platform are the minimum required fields; write `Not yet known` for anything else
3. **Open a new AI conversation** (Claude, ChatGPT, Copilot, Gemini)
4. **Paste `service/llm.txt`** as message 1:
   > I'm writing an Australian BioCommons how-to guide. Use the conventions in the following file for everything you help me produce today.
   > `<paste service/llm.txt contents>`
5. **Paste your filled-in `service/SERVICE_CONTEXT.md`** as message 2:
   > Here is the context for the specific guide I'm writing today.
   > `<paste service/SERVICE_CONTEXT.md contents>`
6. **Confirm the AI understood both files**, then start with the skeleton:
   > Generate the Quick Start checklist and workflow summary table. Do not write any prose yet.
7. **At the end of every session**, run the closing checklist:
   > Run the closing checklist from the BioCommons llm.txt against the guide we have written today and tell me what is missing or incomplete.

---

## `workflow/` — Nextflow workflow documentation

| File | What it is | How to use it |
|------|-----------|---------------|
| [`workflow/llm.txt`](./workflow/llm.txt) | Conventions for documenting a Nextflow workflow built from the [Sydney Informatics Hub template](https://github.com/Sydney-Informatics-Hub/template-nf), using the [Australian BioCommons workflow documentation guidelines](https://github.com/AustralianBioCommons/doc_guidelines/blob/master/documentation_templates/workflows.md) — README section order, required table formats, Nextflow-specific gotchas (`-` vs `--`, profiles, samplesheet schema), and a closing checklist | Paste into the AI as the first message of every session |

There is no context form to fill in for this pack. Instead of a template, you give the AI the workflow's source files so the documentation is derived from the code. Provide `main.nf`, 
`nextflow.config`, `nextflow_schema.json`, `assets/schema_input.json`, `config/modules.config`, and the contents of `modules/`.

### Quickstart

1. **Open a new conversation**
2. **Paste `workflow/llm.txt`** as message 1:
   > I'm documenting a Nextflow workflow built from the Sydney Informatics Hub template. Use the conventions in the following file for everything you help me produce today.
   > `<paste workflow/llm.txt contents>`
3. **Paste the workflow's source files** as message 2:
   > Here is the code for the workflow I'm documenting: `main.nf`, `nextflow.config`, `nextflow_schema.json`, `assets/schema_input.json`, `config/modules.config`, and `modules/*.nf`.
   > `<paste file contents>`
4. **Generate the workflow summary table first** — one row per process in `modules/`:
   > Generate the workflow summary table (Step | Process | Tool | Description | Inputs | Outputs). Do not write any prose yet.
5. **Work through the remaining README sections one at a time**, in the order given in `workflow/llm.txt`
6. **At the end of every session**, run the closing checklist:
   > Run the closing checklist from `workflow/llm.txt` against the README we have written today and tell me what is missing or incomplete.

---

## What the AI can and cannot do

| Can do | Cannot do |
|--------|-----------|
| Generate guide/README structure and prose in the target markdown format | Take screenshots. You must capture all figures |
| Insert figure/diagram placeholders with capture instructions | Supply registry DOIs, IDs, or benchmarking numbers. Always insert placeholders for you to fill |
| Propose workflow summary tables | Verify command syntax. Always test commands yourself |
| Flag missing sections via the closing checklist | Look up current platform docs, or read code it hasn't been given. Paste relevant excerpts into the session |
| Convert existing drafts to the target template format | Look up ORCID or GitHub handles. Supply these yourself |

## Related resources

- [BioCommons guide template](https://australianbiocommons.github.io/how-to-guide-template/)
- [How-to Hub (existing guides)](https://australianbiocommons.github.io/how-to-hub/)
- [BioCommons documentation guidelines](https://github.com/AustralianBioCommons/doc_guidelines)
- [Guide template GitHub repo](https://github.com/AustralianBioCommons/guide-template)
- [Nextflow DSL2 template (codebase)](https://github.com/Sydney-Informatics-Hub/Nextflow_DSL2_template)
- [Template generator ("Use this template")](https://github.com/Sydney-Informatics-Hub/template-nf)
- [Template user guide](https://sydney-informatics-hub.github.io/template-nf-guide/)
