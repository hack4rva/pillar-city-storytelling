# Post-Event Research Index — A City That Tells Its Stories

**Pillar:** A City That Tells Its Stories
**GitHub:** [hack4rva/pillar-city-storytelling](https://github.com/hack4rva/pillar-city-storytelling)
**Problem Statements:**
- PS1: Arts & Cultural Event Discovery — Aggregate Richmond's arts and cultural events into one discoverable place
- PS2: Resident Stories as Civic Insight — Give residents a trusted, accessible way to share lived experiences so community narratives can inform City decisions

**For AI agents:** Read this file to locate any post-event research artifact. Do not list the directory.

---

## Shared Research (Cross-Demo, Per Problem Statement)

| Dir | JTBD | Pain Points | Prior Art |
|-----|:----:|:-----------:|:---------:|
| [`_shared-arts-discovery/`](_shared-arts-discovery/) | ✅ | ✅ | ✅ |
| [`_shared-resident-stories/`](_shared-resident-stories/) | ✅ | ✅ | ✅ |

These files synthesize the problem statement across all demos in that PS. Read them before reading any per-project file.

---

## Per-Project Research Inventory

| Project | Problem Statement | JTBD | Pain | Prior Art | Solution Ideas |
|---------|------------------|:----:|:----:|:---------:|:--------------:|
| [`community-story-popup-kit/`](community-story-popup-kit/) | PS2: Resident Stories | ✅ | ✅ | — | — |
| [`displacement-memory-archive/`](displacement-memory-archive/) | PS2: Resident Stories | ✅ | ✅ | — | — |
| [`explorerva/`](explorerva/) | PS1: Arts Discovery | ✅ | ✅ | — | — |
| [`fulton-oral-history/`](fulton-oral-history/) | PS2: Resident Stories | ✅ | ✅ | — | — |
| [`planning-commission-story-feed/`](planning-commission-story-feed/) | PS2: Resident Stories | ✅ | ✅ | — | — |
| [`richmond-stories-online/`](richmond-stories-online/) | PS2: Resident Stories | ✅ | ✅ | — | — |
| [`vecina/`](vecina/) | PS2: Resident Stories | ✅ | ✅ | — | — |
| [`whats-on-rva/`](whats-on-rva/) | PS1: Arts Discovery | ✅ | ✅ | — | — |

---

## Research Answers (`_research-answers/`)

Parallel AI queries that answered the JTBD open questions. Read `QUERY_MAP.md` to see which file answers which question.

| File | Problem Statement | Questions Answered |
|------|------------------|-------------------|
| [`QUERY_MAP.md`](_research-answers/QUERY_MAP.md) | Both | Full map of JTBD questions → query files |
| [`ad_q1_data.md`](_research-answers/ad_q1_data.md) | PS1 | CultureWorks data, event feed formats, JSON-LD schema |
| [`ad_q2_equity.md`](_research-answers/ad_q2_equity.md) | PS1 | Equity gaps, language access, comparable event aggregators |
| [`rs_q1_data.md`](_research-answers/rs_q1_data.md) | PS2 | Oral history formats, GDPR/consent, archive infrastructure |
| [`rs_q2_equity.md`](_research-answers/rs_q2_equity.md) | PS2 | Trust, voice, community consent patterns, access equity |

---

## Agent Reading Sequence

```
1. Read this file (INDEX.md) — orient
2. For PS1 context: _shared-arts-discovery/jtbd_analysis.md
3. For PS2 context: _shared-resident-stories/jtbd_analysis.md
4. For a specific project: <project>/jtbd_analysis.md → <project>/pain_points.md
5. For answered research questions: _research-answers/QUERY_MAP.md → relevant query file
```
