# Draw the line: Software's edge vs. human trust in community storytelling

## Executive Summary

- **Discovery thrives when metadata and UX are done right**: The Oral History Metadata Synchronizer (OHMS) exposes multiple segment-level fields (timestamp, title, subjects, keywords, synopsis, GPS, link) [1], while accessible UX dramatically lifts trust. In a civic tech study, enhanced user-centric design improved System Usability Scale (SUS) scores from 45.2 to 88.5, doubled trust scores from 2.1 to 4.6, and increased task success from 55-70% to 95% [2]. Prioritize a metadata pipeline and invest early in plain-language UX to convert stories into findable, trusted knowledge.
- **AI is a capable first-drafter, not an editor-in-chief**: The Oral History Association (OHA) notes that automated transcription quality "varies drastically" and must be reviewed [3]. AI-mediated digital civic storytelling (AI-DCS) deployments report using multiple LLM passes blended with "three rounds of human editorial oversight" to control hallucinations [4]. Use automated speech recognition (ASR) for draft transcripts and LLMs for draft themes, but require human verification before publishing.
- **Consent, context, and cultural protocols are human-led work**: OHA mandates informed consent, rolling consent, and language choice with participants [5] [6]. Platforms like Mukurtu CMS implement cultural protocol access rules, but they do not decide them [7] [8]. Establish a community governance group to set consent tiers; let software enforce rules, not define them.
- **Geographic storytelling is a software win with geoprivacy guardrails**: OHMS supports GPS coordinates per segment [1], Omeka's Geolocation plugin maps items with point clustering [9] [10], and StoryMapJS enables step-by-step map narratives and historic overlays [11] [12]. Implement configurable geoprivacy and require human review before any point is placed on a public map.
- **Theme surfacing helps researchers, but uncontrolled labels risk erasure**: OHMS separates controlled "Subjects" from free "Keywords" to map natural language to concepts (e.g., tagging "segregation" even if the word is never spoken) [1]. Keep AI-generated themes as suggestions; require humans to confirm subject headings and write synopses using inclusive description guidelines.
- **Translation should be AI-assisted, community-approved**: OHA calls for participant-selected translators and language accessibility [6]. Use machine translation for a first pass, but finalize with bilingual community reviewers to avoid meaning drift.
- **"Weekend prototypes" are valuable for plumbing, not proof of trust**: You can assemble ingestion, ASR, draft theming, and basic map browsing in 48 hours. However, the Knight Foundation found that "few" civic tech organizations are truly sustainable [13], and Code for America projected ~20% lower revenue for 2024 [14] —reminders that adoption hinges on institutions and resourcing, not demos. Frame the prototype as an assistive discovery layer.
- **Efficiency can create distance without relationships**: Human-computer interaction (HCI) research shows civic tech's push for automation can inadvertently "create distance" between residents and officials if it sidelines relationship-building [15]. Embed human touchpoints in the workflow so digital speed doesn't crowd out trust.
- **Archivists and oral historians are irreplaceable adjudicators of risk**: OHA's best practices emphasize trained human judgment for appraisal, accessioning, metadata, rights, and working with vulnerable communities [6]. Position AI and software as tools that help experts move faster, never as replacements.
- **Honest demo framing builds credibility**: The fastest wins are aggregation, search, draft transcripts, theme suggestions, and maps. The riskiest claims are "building trust," "ensuring action," or "replacing trained practitioners." In the demo, pitch "assistive surfacing and organization" and show the human review queue to make the limits explicit.

## Scope and Stakes — Software accelerates organization and access; humans create legitimacy

In the F4 opportunity space of community storytelling, technology's primary value lies in structuring, searching, and visualizing narratives. Software excels at turning scattered audio files into an accessible, searchable archive. However, the legitimacy of that archive depends entirely on human relationships, institutional commitment, and community trust. Software cannot build trust with skeptical residents, ensure that stories influence policy, or replace the ethical judgment of trained oral historians and archivists. The strategic imperative is to use software to accelerate organization and access, while relying on people and institutions for consent, ethics, context, and action.

## Opportunity Spaces: What Software Can Do Reliably

Aggregation, search, guided entry, theming suggestions, and geographic displays are mature capabilities with proven tools. When deployed thoughtfully, these software functions drastically reduce the friction of managing and discovering community stories.

### Aggregation & Ingestion — From scattered files to structured holdings

Software is highly effective at standardizing capture and metadata at the segment level to multiply discovery. OHMS, for example, creates a method to log an oral history interview with descriptive metadata that corresponds to true timecode [1]. It supports timestamped segments with titles, subjects, keywords, synopses, GPS coordinates, and hyperlinks [1]. 
**Action**: Implement OHMS-style segmenting; require minimal fields (title, timestamp, synopsis) with optional enrichment to turn opaque audio into structured data.

### Discovery & Access — Accessible UX doubles success and trust

Findability and accessibility directly drive user adoption and trust. A study on civic tech platforms demonstrated that an enhanced, user-centric, and accessible design improved task success rates from 55-70% to 95%, reduced time on task significantly, and boosted perceived trust scores from 2.1 to 4.6 out of 5 [2]. The same study showed System Usability Scale (SUS) scores jumping from a "Poor" 45.2 to an "Excellent" 88.5 [2].
**Action**: Build plain-language search and browse interfaces. Add progress indicators, transparent disclosures, and WCAG-compliant design to foster a perception of honesty and competence.

### Guided Collection — Checklists and guardrails, not canned interviews

Software can scaffold consistent intake processes, but people must handle rapport. OHA best practices require obtaining informed consent, allowing for rolling consent, and ensuring language choice [5] [6]. 
**Action**: Add pre-interview checklists, consent state tracking, and language preference toggles into the software. Defer the actual relationship-building and trauma-informed interviewing to trained human practitioners.

### Theme Surfacing — Suggest, don't decide

Draft labels generated by software are helpful, but final description must remain a human task. OHA explicitly notes that the quality of automated transcription "varies drastically" and must be reviewed [3]. OHMS separates controlled "Subjects" (like Library of Congress headings) from local "Keywords" to map natural language to concepts [1]. Furthermore, AI-DCS platforms note that human-AI narrative synthesis requires multiple LLM passes and rounds of human editorial oversight to prevent hallucinations and ethical risks [4].
**Action**: Build a pipeline: ASR → LLM keyword/topic draft → human subject headings/synopsis review, utilizing inclusive description guidance.

### Geographic Display — Powerful, if consented and privacy-aware

Maps unlock new audiences and contextualize stories, but geographic precision can harm vulnerable populations. OHMS allows one set of GPS coordinates per segment [1]. Omeka's Geolocation plugin displays locations on maps and supports clustering map points [9] [10]. StoryMapJS allows users to integrate historical and contemporary maps into interactive stories, including gigapixel image mapping [11] [12].
**Action**: Add geoprivacy tiers (hide, fuzz, exact) tied to narrator consent. Require human approval before publishing any coordinates.

| Tool | Key Capabilities | Relevance to F4 Pillar |
| :--- | :--- | :--- |
| **OHMS (Nunn Center)** | 10+ segment-level fields; 3 indexing levels; GPS/link fields [1] | Segment indexing, granular discovery |
| **Omeka + Geolocation** | Browse by items/collections/tags/map; advanced search; point clustering [16] [9] [10] | Collection discovery, geographic mapping |
| **Mukurtu CMS** | Cultural protocol-based access control; community-defined permissions [7] [8] | Enforcing community access rules |
| **StoryMapJS** | Interactive map stories; gigapixel/historic overlay support [11] [12] | Narrative geography and spatial context |

*Takeaway: Leverage existing, proven tools for metadata structuring, mapping, and access control rather than building these capabilities from scratch.*

## What Software Cannot Do (and Must Stay Human-Led)

Trust, consent, appraisal, ethical risk management, and institutional follow-through are strictly human responsibilities. Attempting to automate these areas leads to broken trust and failed adoption.

### Trust & Relationships — "Speed of trust," not speed of code

Ethnographic research in civic tech reveals that an orientation around efficiency can inadvertently "create distance" in the relationships between citizens and governments [15]. OHA's Social Justice Task Force emphasizes that social justice praxis "moves at the speed of trust," empowering the narrator at every step [6]. 
**Action**: Budget time for relationship-building, feedback cycles, and co-review sessions. Do not let digital speed crowd out human connection.

### Consent, Rights, and Cultural Protocols — Software enforces; humans decide

Software can lock a file, but it cannot negotiate the terms of that lock. OHA mandates a full-bodied approach to informed consent, including mutual understanding, shared power, and rolling consent [6]. Mukurtu CMS allows for managing media access with cultural protocols, but the communities themselves must define those protocols [7] [8].
**Action**: Create a community advisory group to define protocol sets and consent tiers; encode them into the platform's permission architecture.

### Appraisal, Description, and Ethics — Professional judgment required

The arrival of interviews at a repository requires appraisal and accessioning—actions that protect materials and collect necessary information consistent with the narrator's intentions [6]. Understanding power dynamics is essential, especially when working with vulnerable communities who might face harm by publicly sharing their experiences [6].
**Action**: Keep archivists and oral historians in the loop. Require professional review before public release to ensure ethical standards are met.

### Ensuring Action and Institutional Commitment — Organizational, not technical

Technology alone does not ensure adoption or policy impact. A Knight Foundation report found that even the most often cited civic tech success stories still struggle with sustainability, and few organizations can truly be described as sustainable [13]. Code for America, a major player in the space, had to restructure and eliminate 35 staff positions due to a shifting landscape and ~20% lower revenue projections for 2024 [14].
**Action**: Secure MOUs, workflows, dedicated staffing, and budget lines before promising community members that their stories will result in action.

| Opportunity Space | What Software Can Do | What Humans Must Do |
| :--- | :--- | :--- |
| **Aggregation & Ingestion** | Bulk import, schema validation, file checksums | Appraisal, selection, rights intake [6] |
| **Discovery & Access** | Search, filters, accessible UI, maps [2] [16] | Plain-language copy, context notes |
| **Guided Collection** | Checklists, consent tracking UI | Rapport, trauma-informed interviewing [6] |
| **Theme Surfacing** | ASR, draft topics/keywords [4] [3] | Final subjects/synopsis; bias checks [1] |
| **Geographic Display** | Map rendering, clustering, overlays [12] [10] | Geoprivacy decisions; place sensitivity |
| **Institutional Action** | Dashboards, data exports | Policy follow-through; governance [13] |

*Takeaway: Software scales the processing of stories, but humans must scale the ethics, consent, and real-world application of those stories.*

## Right Role for AI/LLMs: Appropriate vs Overclaiming

AI and LLMs are powerful tools for drafting, extraction, and translation, but they must be bounded. Humans must remain in charge of meaning, risk, and narrative integrity.

| AI Use Case | Appropriate? | Guardrails / Evidence | Why/When Inappropriate |
| :--- | :--- | :--- | :--- |
| **ASR Transcription** | Yes (First draft) | OHA: automated transcripts "vary drastically" and must be reviewed [3]. | Publishing unreviewed ASR for names, dates, or sensitive content. |
| **Theme/Keyword Extraction** | Yes (Suggestions) | OHMS model: controlled subjects vs local keywords [1]; requires human finalization. | Replacing controlled vocabularies with opaque AI labels. |
| **Summarization/Synopsis** | Yes (Assistive) | AI-DCS: multi-pass with human editorial oversight prevents hallucinations [4]. | Publishing AI summaries without human edits on sensitive topics. |
| **Prompt Generation** | Yes (Scaffold) | Aligns with OHA guidance on preparing open-ended guides [5]. | Using AI to drive live interviews in place of trained interviewers. |
| **Translation Assistance** | Yes (Draft) | OHA: participant-chosen translators [6]; OHMS bilingual tagging example [1]. | Releasing machine translation without bilingual community review. |
| **Sensitive Content Flagging** | Yes (Triage) | Treat as a "review queue," not a final judgment. | Auto-blocking or auto-publishing based solely on AI flags. |
| **Composite Story Generation** | No (For publishing) | AI-DCS warns of consent, hallucination, and ethical risks [4]. | Overwrites authentic voices; violates consent and attribution norms. |
| **Automated Access Decisions** | No | Consent and protocols must be community-defined [7] [8]. | Risks harm to vulnerable communities; bypasses governance. |
| **"Ensuring Action"** | No | Adoption is institutional, requiring funding and governance [13] [14]. | Overclaiming outcomes that software fundamentally cannot control. |

*Takeaway: Frame AI strictly as an assistive engine that prepares drafts for human experts, never as an autonomous decision-maker.*

## Prototype vs Overpromise: What a Weekend Can and Cannot Prove

A weekend prototype is highly valuable for demonstrating technical plumbing and workflow possibilities. It is actively harmful if used to claim that the platform has "solved" trust, adoption, or impact.

| Prototype Module | Can Deliver in 48 Hours | Human Inputs Required | Overpromising to Avoid |
| :--- | :--- | :--- | :--- |
| **Ingestion** | Batch upload, metadata schema, basic validation | Sample CSV, field mapping | "Scales to any archive instantly" without QA |
| **Transcription** | ASR API integration; draft transcripts | 2-3 test audio files | "Publication-ready automated transcripts" |
| **Theme Surfacing** | LLM topic/keyword drafts; review queue UI | Archivist to vet 10-20 segments | "Accurate automated cataloging" |
| **Mapping** | Omeka Geolocation + StoryMap embed [11] [9] | Test consented coordinate points | "Safe for all stories and precise locations" |
| **Consent States** | UI to display consent tiers/protocol locks | Sample policy text | "We've solved community consent and trust" |

*Takeaway: Build the prototype to show the "Draft → Review → Publish" workflow, explicitly highlighting the required human intervention steps.*

## Honest Demo Framing

To build credibility during a demo, pitch the tool as "assistive organization and discovery," not as a silver bullet for "trust" or "impact." 

**Script Pillars for the Demo:**
1. **Aggregation**: "We aggregate and structure stories to make them usable."
2. **Discovery**: "We make them easy to find with accessible, plain-language UX."
3. **Acceleration**: "We help humans work faster by providing AI-generated drafts for transcripts and themes."
4. **Respect**: "We respect consent and cultural protocols by design, locking down access until humans approve."
5. **Quality Control**: "A highly visible human-review step ensures quality, accuracy, and ethical safety."

**What to Show:**
Demonstrate the Draft → Review → Publish lanes. Show the consent badges, the cultural protocol locks (inspired by Mukurtu), the geoprivacy controls, and the audit log. Making the tool's boundaries explicit proves that you understand the F4 domain's ethical stakes.

## Implementation Roadmap and Operating Model

Pair the software tool with governance, staffing, and review practices to ensure sustainable adoption.

### 0-2 Weeks: Standing up the stack
- Deploy the CMS (e.g., Omeka or Mukurtu), enable Geolocation [9], and integrate ASR.
- Define minimal metadata requirements (segment title, timestamp, synopsis) based on OHMS standards [1].
- Form a community advisory group to begin defining consent tiers and cultural protocols.

### 1-3 Months: Human-in-the-loop operations
- Train indexers on OHMS-style practices, utilizing different indexing depths [1].
- Pilot the AI draft → human review workflow and measure error rates and hallucination frequency.
- Run bilingual glossary and translation reviews with community partners to ensure language accessibility [6].

### 6-12 Months: Institutionalization
- Secure MOUs on staffing and funding; establish Quality Assurance SLAs (e.g., 100% review of sensitive content, 30% random audits).
- Publish inclusive description guidelines and run bias audits on AI-generated suggestions.
- Evaluate adoption and trust via usability testing, repeating SUS and trust metrics to ensure the UX remains accessible [2].

## Risk and Ethics Playbook

Anticipate harm and design for minimization and accountability.

- **Consent Drift**: Track "rolling consent" and maintain change logs. Recognize that consent is an ongoing relationship, not a one-time form [6].
- **Cultural Harm**: Implement community-defined protocols (via Mukurtu-style permissions) and clear opt-out paths [7].
- **Privacy**: Set geoprivacy defaults to "hidden" or "fuzzed." Require manual approvals before any exact coordinates are published.
- **AI Risks**: Disable auto-publish features. Audit LLM prompts and outputs regularly. Explicitly disclose to end-users when AI assistance was used to generate summaries or themes [4].

## References

1. *Indexing Interviews in OHMS: An Overview Louie B. Nunn ...*. https://www.oralhistoryonline.org/wp-content/uploads/2013/06/OHMS-Indexing-guide-5-15-14.pdf
2. *The Impact Of UI/UX Design on User Trust and Task ...*. https://rsisinternational.org/journals/ijrsi/uploads/vol12-iss8-pg557-569-202509_pdf.pdf
3. *Archiving Oral History: Manual of Best Practices - Oral History Association*. https://oralhistory.org/archives-principles-and-best-practices-complete-manual/
4. *AI-Mediated Digital Civic Storytelling*. https://www.emergentmind.com/topics/ai-mediated-digital-civic-storytelling-ai-dcs
5. *Oral History Best Practices - Oral History Association*. https://oralhistory.org/best-practices/
6. *OHA Principles and Best Practices*. https://oralhistory.org/wp-content/uploads/2022/08/OHA-Principles-and-Best-Practice-Print-Version-Updated-2022.pdf
7. *Managing media access with cultural protocols | Mukurtu CMS*. https://mukurtu.org/support/managing-media-access-with-cultural-protocols/
8. *Mukurtu CMS: Communities, Cultural Protocols and Categories | The Sustainable Heritage Network*. https://sustainableheritagenetwork.org/digital-heritage/mukurtu-cms-communities-cultural-protocols-and-categories
9. *Geolocation*. https://info.omeka.net/build-a-website/manage-plugins/geolocation/
10. *
        
            Omeka
        
        
            - Geolocation 3.0: Leaflet and more
        
    *. https://omeka.org/news/2018/06/19/geolocation-3/
11. *Displaying a Georeferenced Map in KnightLab’s StoryMap JS | Programming Historian*. https://programminghistorian.org/en/lessons/displaying-georeferenced-map-knightlab-storymap-js
12. *
         StoryMapJS Beta gets a fresh look, MapBox maps, and a new gigapixel image tool | Knight Lab 
    *. https://knightlab.northwestern.edu/2014/03/25/storymapjs-beta-gets-a-fresh-look-mapbox-maps-and-a-new-gigapixel-image-tool/
13. *Scaling Civic Tech – Knight Foundation + Rita Allen Foundation*. https://knightfoundation.org/features/civictechbiz
14. *A Moment of Change on Code for America’s Journey — Code for America*. https://codeforamerica.org/news/moment-of-change-on-our-journey/
15. *(PDF) The Practice of Civic Tech: Tensions in the Adoption and Use of New Technologies in Community Based Organizations*. https://www.researchgate.net/publication/335012264_The_Practice_of_Civic_Tech_Tensions_in_the_Adoption_and_Use_of_New_Technologies_in_Community_Based_Organizations
16. *Omeka Feature List*. https://omeka.org/files/docs/Featurelist.pdf