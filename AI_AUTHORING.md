# AI-assisted guide authoring

This repository includes two files that help you use an AI assistant to write a BioCommons how-to guide faster and with less manual effort:

| File | Purpose |
|------|---------|
| [`service/llm.txt`](./service/llm.txt) | Describes all BioCommons template conventions — the AI reads this to understand what a finished guide should look like |
| [`service/SERVICE_CONTEXT.md`](./service/SERVICE_CONTEXT.md) | A form you fill in before each writing session — tells the AI what you are specifically building |

Using both files together means you spend less time correcting AI output and less time
explaining BioCommons conventions from scratch. The AI handles structure and formatting;
you supply the technical content.

## Before you start

You will need:

- An AI assistant with a chat interface (Claude, ChatGPT, Gemini, GitHub Copilot Chat, or similar)
- A fork of this repository
- 10–15 minutes to fill in `service/SERVICE_CONTEXT.md` before your first session

## Step 1: Fill in `service/SERVICE_CONTEXT.md`

Open [`service/SERVICE_CONTEXT.md`](./service/SERVICE_CONTEXT.md) and work through the fields. You do not need to have every answer. Write `Not yet known` for anything you cannot fill in yet. Fields left blank are ignored by the AI; fields marked `Not yet known` will generate a visible placeholder in the
guide and appear on the closing checklist.

The fields that matter most are:

- **Guide title and tool name**: the AI needs these before it can generate anything useful
- **Target platform**: determines job scheduler syntax, screenshot expectations, and infrastructure-specific callouts
- **Audience**: determines how much background explanation is needed
- **Scope**: what the guide covers and, importantly, what it does not
- **Session goals**: decide upfront whether you want a full draft or just a skeleton

Registry metadata (WorkflowHub DOI, bio.tools, TeSS) can be filled in later, but note that the guide cannot be published without real values in these fields.

## Step 2: Set up your AI session

Open a new conversation with your AI assistant. A new conversation each session is important as carrying over context from unrelated conversations can cause the AI to apply the wrong conventions.

Paste the following in order, waiting for the AI to acknowledge each one:

**Message 1**: paste the full contents of `service/llm.txt`:

```
> I'm writing a BioCommons how-to guide. Use the conventions in the following file for
> everything you help me produce today.
>
> <paste llms.txt contents here>
```

**Message 2**: paste your filled-in `service/SERVICE_CONTEXT.md`:

```
> Here is the context for the specific guide I'm writing today.
>
> <paste filled-in GUIDE_CONTEXT.md contents here>
```

**Message 3**: confirm the AI has understood both:

```
> Based on the two files above, summarise: what sections does my guide need, in what
> order, and what are the three most important things you will need me to supply that
> you cannot generate yourself?
```

Check the response against the section order in `llms.txt`. If it is wrong, correct it before proceeding.

## Step 3: Generate the skeleton first

Do not ask for the full guide in one prompt. Start with the structure:

```
> Generate the Quick Start checklist and the workflow summary table for my guide.
> Do not write any prose yet.
```

Review both carefully before moving on. The Quick Start checklist defines the scope of the entire guide — if a step is missing here, it will be missing everywhere. The workflow table (Process | Workflow | Description | Inputs | Outputs) is the hardest section to write and the most useful to get right early.

Once you are happy with the skeleton, confirm it with the AI:

```
> I'm happy with this structure. Now expand the guide one section at a time, starting
> with the Introduction.
```

## Step 4: Write one section at a time

Work through sections sequentially. After each section, ask:

```
> What figure placeholders should I add to this section, and what should each
> screenshot capture?
```

The AI will insert `![](images/SCREENSHOT_NEEDED.png)` placeholders with captions describing what to capture. Take screenshots as you go rather than leaving them all to the end. It is much harder to reconstruct the exact state of a UI after the fact.

For registry links (WorkflowHub, bio.tools, TeSS), the AI will insert clearly labelled placeholders where you have not yet supplied real values:

```
[WorkflowHub DOI: AUTHOR TO SUPPLY]
```

Do not ask the AI to guess or generate these values, registry IDs and DOIs must come from you. Supply them by saying:

```
> The WorkflowHub DOI for this workflow is https://doi.org/10.48546/WORKFLOWHUB.WORKFLOW.XXX.Y —
> please update all placeholders.
```

## Step 5: Run the closing checklist

At the end of every session, paste this prompt before you close the conversation:

> Run the closing checklist from the BioCommons llms.txt against the guide we have
> written today and tell me what is missing or incomplete.

The AI will work through the checklist and flag gaps. Record anything that comes back incomplete — these are your action items before the guide can be published. Common gaps at this stage are:

- Registry DOIs not yet supplied
- CITATION.CFF not populated
- CONTRIBUTORS.yml entries missing
- Acknowledgement text absent
- Callout boxes using wrong syntax

Do not skip this step. It is much faster to catch these gaps now than during a review.

## Working across multiple sessions

A guide will usually take more than one session to complete. At the start of each new
session:

1. Paste `llms.txt` again — the AI has no memory of previous conversations
2. Paste your updated `GUIDE_CONTEXT.md`
3. Paste the current state of your guide draft and say:
   > Here is my guide so far. Continue from [section name].

Keep your draft in a `.md` file in the repository as you go. Do not work in Google Docs or Word as converting from a word processor introduces formatting errors and adds an extra manual step. If you have existing notes or a draft in another format, paste the content into the session and ask the AI to convert it to BioCommons markdown format before continuing.

## What AI cannot do

Be aware of these limitations regardless of which AI assistant you use:

- **Registry metadata**: The AI does not know your WorkflowHub DOI or bio.tools entry. It will insert placeholders; you must supply the real values.
- **Screenshots**: The AI cannot take screenshots. All figures must be captured by you and saved to `images/<guide_name>/`.
- **Technical accuracy**: The AI will generate plausible-looking command syntax, file paths, and configuration. Always test commands yourself before publishing. Pay particular attention to version numbers, queue names, and resource specifications as these are frequently wrong.
- **Current platform documentation**: The AI's knowledge of NCI Gadi, Pawsey Setonix, Nectar, and Galaxy Australia may be out of date. For anything platform-specific, verify against the current user documentation and paste relevant excerpts into the session if needed.
- **ORCID and GitHub handles**: Supply these yourself. Do not ask the AI to look them up.

## Troubleshooting

### The AI is ignoring the BioCommons conventions and producing generic documentation

Start a new conversation and paste `llms.txt` again as the very first message. Long conversations cause earlier context to be deprioritised.

### The AI is producing content in a word-processor style (bullet points, bold headers, no code blocks)

Remind it: "All output should be valid GitHub-flavoured markdown, using the callout and figure syntax specified in llms.txt."

### The AI invented a WorkflowHub DOI or bio.tools entry that looks real but isn't 

Always verify registry links by visiting the URL before publishing. If the link returns a 404, the AI has hallucinated it.

## The guide is getting very long and the AI is losing track of earlier sections 

Split the guide into a multi-page structure. See the BioCommons guide template documentation for how to configure the sidebar for multi-page guides:
https://australianbiocommons.github.io/how-to-guide-template/add_new_pages

## Getting help

- BioCommons guide template documentation: https://australianbiocommons.github.io/how-to-guide-template/
- How-to Hub (existing guides for reference): https://australianbiocommons.github.io/how-to-hub/
- BioCommons documentation guidelines: https://github.com/AustralianBioCommons/doc_guidelines
- Report issues with this template: https://github.com/AustralianBioCommons/guide-template/issues
