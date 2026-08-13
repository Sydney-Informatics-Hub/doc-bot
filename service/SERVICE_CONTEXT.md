# Guide Authoring Context Template

Use this file to set up an AI-assisted guide writing session. Fill in as many fields as you
can before starting, the more context you provide upfront, the less the AI will need to ask,
and the closer the first draft will be to the BioCommons template conventions.

## How to use this file

1. Fill in the fields below (leave any unknowns as `Unknown`)
2. Open a new conversation with your AI assistant (Claude, Copilot, etc.)
3. Paste the full contents of `llms.txt` and say:
   > "I'm writing an Australian BioCommons how-to guide. Use the conventions in the above file for
   > everything you help me produce."
4. Paste the full contents of this filled-in file and say:
   > "Here is the context for the specific guide I'm writing today."
5. Ask the AI to confirm it has understood both files before you start
6. Begin with: "Generate the Quick Start checklist and workflow summary table first,
   before any prose."
7. At the end of your session, ask: "Run the closing checklist from the BioCommons
   llms.txt against the guide we've written and tell me what's missing or incomplete."

---

## 1. Guide identity

**Guide title:**
<!-- A working title is fine — it can change. -->
<!-- Example: "How to run nf-core/proteinfold on Pawsey Setonix" -->


**Tool / workflow name:**
<!-- The primary tool or workflow this guide documents. -->
<!-- Example: nf-core/proteinfold, hifiasm, BioShell -->


**Tool / workflow version:**
<!-- Lock to a specific version where possible for reproducibility. -->
<!-- Example: v1.1.1, v2.0, not yet determined -->


**Target platform:**
<!-- Check all that apply -->
- [ ] Galaxy Australia
- [ ] NCI Gadi (PBS Pro)
- [ ] Pawsey Setonix (Slurm)
- [ ] Nectar Research Cloud
- [ ] Australian Nextflow Seqera Service
- [ ] Bioplatforms Australia Data Portal
- [ ] Other: _______________

**Guide type:**
<!-- Check one -->
- [ ] Single-page guide (default — use `index.md`)
- [ ] Multi-page guide (requires sidebar config in `_data/sidebars/main.yml`)

---

## 2. Audience

**Who is this guide for?**
<!-- Describe the intended reader. Be specific — this affects tone, assumed knowledge, and
     how much background explanation is needed. -->
<!-- Example: "Researchers new to HPC who have some command-line experience but have
     never used a job scheduler before" -->


**What can the reader be assumed to already know?**
<!-- List skills/tools the guide can reference without explaining -->
<!-- Example: basic Linux commands, what FASTA format is, how to log in to an HPC -->


**What should the guide NOT assume the reader knows?**
<!-- List things that need to be explained from scratch -->
<!-- Example: what Nextflow is, what a container is, what a samplesheet is -->

---

## 3. Scope

**What this guide covers:**
<!-- Bullet list of the main tasks the guide will walk through -->
<!--
- Task 1
- Task 2
- Task 3
-->


**What this guide explicitly does NOT cover:**
<!-- Important for keeping the guide focused. Helps the AI avoid scope creep. -->
<!-- Example: "This guide does not cover how to interpret AlphaFold2 output structures.
     See the best-practices guide for that." -->


**Approximate size:**
- [ ] Short (1–2 sections, single page)
- [ ] Medium (3–5 sections, single page)
- [ ] Long (6+ sections, consider multi-page)

---

## 4. Registry metadata

Fill in what you have. For anything not yet available, write `Not yet known` — the AI will
insert a clearly labelled placeholder and remind you to supply the real value before publishing.

**WorkflowHub entry URL:**
<!-- Example: https://workflowhub.eu/workflows/221 -->
<!-- If not yet registered: "Not yet registered" -->


**WorkflowHub DOI:**
<!-- Example: https://doi.org/10.48546/WORKFLOWHUB.WORKFLOW.221.3 -->
<!-- If not yet minted: "Not yet minted" -->


**WorkflowHub collection URL:**
<!-- If this workflow belongs to a collection -->
<!-- Example: https://workflowhub.eu/collections/5 -->


**bio.tools entry URL:**
<!-- Example: https://bio.tools/alphafold_2 -->
<!-- If not yet registered: "Not yet registered" -->


**TeSS training search link:**
<!-- Example: https://tess.elixir-europe.org/search?q=genome+assembly -->
<!-- Generate one by searching for your topic at tess.elixir-europe.org -->


**Zenodo DOI (if a previous version of this guide has been published):**
<!-- Example: https://doi.org/10.5281/zenodo.8210268 -->
<!-- If new guide: "Not yet minted" -->

---

## 5. People

**Authors:**
<!-- Add a row for each author. GitHub handle and ORCID are used in CONTRIBUTORS.yml -->

| Name | GitHub handle | ORCID | Institution |
|------|--------------|-------|-------------|
|      |              |       |             |
|      |              |       |             |

**BioCommons programme or project this guide is connected to:**
<!-- Example: Threatened Species Initiative, ABLeS, Australian Nextflow Seqera Service -->
<!-- If none: leave blank -->


**Funding acknowledgement — any additional funders beyond NCRIS/BioCommons?**
<!-- Example: "Bioplatforms Australia", "ARC grant DP123456" -->
<!-- The standard NCRIS/BioCommons acknowledgement will always be included -->

---

## 6. Related resources

**Related guides already on the How-to Hub:**
<!-- Links to existing guides the reader might need before or after this one -->
<!-- Example: https://australianbiocommons.github.io/how-to-guides/genome_assembly/assembly_qc -->


**Upstream documentation the AI should reference for technical accuracy:**
<!-- Links to the tool's own docs, nf-core page, platform user guide, etc. -->
<!-- The AI cannot fetch these automatically — paste key details into the session if needed -->
<!--
- Tool docs: 
- Platform docs:
- nf-core page:
-->


**Any existing draft content to incorporate:**
<!-- If you have notes, a Google Doc, a previous guide version, or any other draft,
     describe it here. Paste the content into the session after this context file.
     Note: always convert existing content to markdown before asking the AI to work with it. -->

---

## 7. Known constraints or special requirements

**Are there any known technical gotchas for this tool/platform combination?**
<!-- Example: "AlphaFold2 databases are very large and must be pre-staged on Gadi before
     running — this is not obvious from the nf-core docs" -->


**Are there access or eligibility requirements the reader needs to meet first?**
<!-- Example: "Users must have an active ABLeS allocation before following this guide" -->


**Any sections that are optional vs. required in the workflow?**
<!-- Example: "The BAM-to-FASTQ conversion step is optional if data is already in FASTQ format" -->

---

## 8. Session goals

**What do you want to have produced by the end of this session?**
<!-- Check all that apply -->
- [ ] Full draft of the complete guide
- [ ] Quick Start checklist and workflow table only (skeleton)
- [ ] One specific section: _______________
- [ ] Convert existing draft to BioCommons template format
- [ ] Review and fix an existing guide against the template checklist

**Any sections you already have content for and don't need the AI to generate?**
<!-- List them so the AI doesn't regenerate content you're happy with -->

---

*This file is part of the Australian BioCommons guide-template repository.
See `llms.txt` for full template conventions and the closing review checklist.*
