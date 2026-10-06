# Training Package Context Template

Use this file to set up an AI-assisted session for building or restructuring a training package. Fill in as many fields as you can before starting. The more context you give upfront, the less the AI needs to ask, and the closer the first draft will be to the conventions in `training/llm.txt`.

## How to use this file

1. Fill in the fields below. Write `Not yet known` for anything you cannot answer yet
2. Open a new conversation with your AI assistant
3. Paste the full contents of `training/llm.txt` and say:
   > "I'm building a training package. Use the conventions in the following file for everything you help me produce today."
4. Paste the full contents of this filled-in file and say:
   > "Here is the context for the specific training package I'm working on today."
5. If you are restructuring existing materials, also paste the existing `mkdocs.yml` and a file listing (`find . -type f -not -path './.git/*' | sort`)
6. Ask the AI to confirm it has understood, then begin with:
   > "Generate the folder tree, the mkdocs.yml nav block, and the lesson plan table for each part. Do not write any lesson prose yet."
7. At the end of the session, ask:
   > "Run the closing checklist from training/llm.txt against the package and tell me what is missing or incomplete."

---

## 1. Package identity

**Workshop name:**
<!-- Used as site_name and the learner home page H1. -->
<!-- Example: Nextflow for the Life Sciences -->


**Short code:**
<!-- Used in the repository name and setup README title. -->
<!-- Example: nf4ls -->


**Repository:**
<!-- GitHub org and repository name for the template repo. -->
<!-- Example: Sydney-Informatics-Hub/nf4ls-materials -->


**Subject area:**
<!-- The tool, method, or skill being taught. The AI only uses subject-specific terminology for what you list here. -->


**One-paragraph summary:**
<!-- What the workshop teaches and why it matters to the audience. -->


---

## 2. Audience

**Who are the learners?**
<!-- Example: Bioinformaticians and life scientists who already run simple Nextflow pipelines and want to scale them on HPC -->


**Level:**
- [ ] Introductory
- [ ] Intermediate
- [ ] Advanced

**Prerequisites (what learners can be assumed to know):**


**Prerequisite workshop (if any, with URL):**


**What should NOT be assumed:**


---

## 3. Structure

**Number of parts:**


**Lessons per part:**
<!-- One line per lesson: number, title, approx. minutes. Leave timing as Not yet known if unsure. -->
<!--
Part 1 – <Part title>
  1.0 Introduction – 10 min
  1.1 <Title> – 20 min
Part 2 – <Part title>
  2.0 Introduction – 10 min
-->


**Overarching learning outcomes:**
<!-- 4–8 bullets. These feed .zenodo.json and the trainer home page. -->


**Explicitly out of scope:**
<!-- Feeds the "What Part N is not" lists in the trainer guides. -->


---

## 4. Delivery

**Original delivery format:**
<!-- Example: two 3-hour online sessions -->


**Supported delivery modes:**
- [ ] Online
- [ ] In-person
- [ ] Hybrid
- [ ] Self-paced

**Time zone for schedules:**


**Learner support channel:**
<!-- Example: Slack, shared Google Doc -->


---

## 5. Training environment

**Where learners work:**
- [ ] Their own computer only
- [ ] Cloud VMs (e.g. Nectar, NCI Nirin)
- [ ] HPC (list systems): _______________
- [ ] Other platform: _______________

**Multiple platforms shown as tabs?**
<!-- If learners use more than one system, list the exact tab labels in the order they should appear. Example: Gadi, Setonix -->


**Per-learner hardware:**
<!-- CPU, RAM, disk -->


**Software learners install locally:**


**Software in the training environment (with pinned versions):**


**Is there a `setup/` provisioning folder?**
- [ ] Yes — scripts exist
- [ ] Yes — to be written
- [ ] No — environment is provided by: _______________

**Data:**
<!-- What data learners use, how big it is, and where it lives (in-repo materials/ folder, external data repo, staged on HPC). -->


---

## 6. Existing materials (for restructuring)

**Source repositories / folders:**
<!-- Paths or URLs of the material being migrated. -->


**Previous iterations (URLs, oldest first):**


**Known gaps or stub lessons:**


**Trainer notes currently embedded in learner pages?**
<!-- Yes/No, and where. -->


---

## 7. People and citation

**Authors (name, affiliation, ORCID):**


**Facilitators / contributors to acknowledge:**


**Developing organisation(s):**


**Funding / enabling statement:**
<!-- Example: enabled by Australian BioCommons' BioCLI Platforms Project (NCRIS via Bioplatforms Australia) -->


**Compute provider acknowledgement:**


**Zenodo DOI:**
<!-- Not yet known is fine before the first release. -->


**Contact email:**


---

## 8. Session goals

**What do you want from this session?**
- [ ] Skeleton only (folder tree, nav, lesson plan tables)
- [ ] Migrate existing pages into the new structure
- [ ] Draft specific pages (list): _______________
- [ ] Trainer guides
- [ ] Metadata files (CITATION.cff, .zenodo.json, README)
- [ ] Full closing-checklist review

**Anything the AI should not touch?**

