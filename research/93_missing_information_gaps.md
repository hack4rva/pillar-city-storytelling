# Richmond Arts Discovery, Fast-Tracked: Closing 7 Gaps in 48 Hours

## Executive Summary

To successfully build a viable arts discovery or storytelling prototype during this 48-hour hackathon, the team must immediately close seven critical information gaps. The data reveals that community demand is not the issue; 85.3% of surveyed attendees acknowledge the vital role of arts and culture in their communities [1]. The true challenge lies in fragmented discovery and digital exclusion. 

One citywide aggregator already exists: CultureWorks runs a region-wide Arts & Culture Calendar powered by Localist, supported by a newsletter and four social channels (Instagram, Facebook, YouTube, LinkedIn) [2]. The strategy must be to integrate with this existing infrastructure rather than duplicate it. For storytelling initiatives, voice-first intake is essential to include older and low-connectivity residents, as research highlights significant digital exclusion barriers for older adults in long-term care [3]. Seed content for a neighborhood history explorer is readily available today at The Valentine, which hosts a robust Richmond Stories hub featuring podcasts, audio guides, and an online collection database [4] [5] [6]. Success depends on locking in a specific output type in the first hour, validating data sources, and securing a named champion for post-hackathon continuation.

## Hackathon North Star — Ship one useful tool that survives Monday

Success for this weekend is defined by a crisp output choice, a completed `evidence_log.md` addressing all seven gaps, and a named champion ready to adopt the prototype. Without a clear owner, even the most elegant technical solution will become abandonware by Monday morning.

### Weekend Objectives with KPIs — 1 tool, 3 data validations, 1 champion

The team must commit to either an "Aggregator Lite" or a "Story Hotline + Map" within the first hour. Key performance indicators include aggregating 50 upcoming events or capturing 10 recorded stories, validating three distinct data channels, and securing one explicit commitment from a local institutional leader.

## Gap 1: Arts Organization Calendar Data — 15–20-site audit with a Localist backbone

An arts aggregator cannot be built without knowing which organizations have accessible structured data. CultureWorks already operates a comprehensive calendar [2]. The team must use this as a primary source and fill long-tail gaps via a manual audit of smaller venues.

### Localist as Source-of-Truth — Confirm feeds and embed options in hour 1

CultureWorks utilizes Localist Event Calendar Software [2]. In the first hour, the technical team must verify whether this Localist implementation exposes ICS, RSS, or JSON endpoints. If it does, use it as the backbone to avoid duplicative crawling and focus manual auditing on organizations not listed there.

### High-Yield Audit Targets — 9 named orgs to check first

At least nine prominent visual and multidisciplinary organizations require immediate manual checks. The team must prioritize the Virginia Museum of Fine Arts (VMFA), ICA at VCU, 1708 Gallery, Visual Arts Center, Gallery5, Richmond Public Library galleries, Quirk Gallery, Candela Books + Gallery, and Elegba Folklore Society. 

### Table — Org-by-Org Calendar/Feed Status

A single glance shows where structured data exists and where manual entry is needed. Assign two teammates 90 minutes to test each site and log the results.

| Organization | Official URL | Calendar URL | ICS/iCal | RSS | Notes | Owner |
| VMFA | TBD | TBD | TBD | TBD | Prioritize structured feed search | Tech Lead |
| ICA at VCU | TBD | TBD | TBD | TBD | Check for JSON endpoints | Tech Lead |
| 1708 Gallery | TBD | TBD | TBD | TBD | Likely requires manual scrape | Data Lead |
| Visual Arts Center | TBD | TBD | TBD | TBD | Check class vs. exhibition feeds | Data Lead |
| Gallery5 | TBD | TBD | TBD | TBD | High priority for live events | Tech Lead |
| RPL Galleries | TBD | TBD | TBD | TBD | Check city library system | Data Lead |
| Quirk | TBD | TBD | TBD | TBD | Commercial gallery check | Data Lead |
| Candela | TBD | TBD | TBD | TBD | Photography focus | Data Lead |
| Elegba Folklore Society | TBD | TBD | TBD | TBD | Cultural events focus | Tech Lead |

*Takeaway: Organizations exposing iCal or RSS feeds will be ingested automatically, while those without structured data will require manual entry for the weekend prototype.*

## Gap 2: How Residents Discover Events — Validate channels via quick intercepts

Understanding current discovery channels validates the problem statement and informs which failure modes the tool should address. Local media and social presences suggest audiences rely heavily on Instagram, Facebook, and niche calendars, but coverage remains inconsistent.

### 3–5 Intercepts Script and Capture Plan

Run 3–5 informal interviews during the hackathon orientation session. Ask a single question: "How did you find out about the last arts event you attended in Richmond?" Probe for specific platforms and log all quotes and identified channels directly into `evidence_log.md`.

### Triangulation with Local Outlets (RVAHub, City Cultural Arts, CultureWorks)

Contrast resident responses with known local outlets. RVAHub actively curates city happenings on Instagram [7]. The City of Richmond's Parks and Recreation Cultural Arts division runs long-standing programs, including the Festival of Arts which has operated since 1956 [8]. CultureWorks promotes its calendar across four major social channels [2]. 

### Table — Discovery Channels vs. Strengths/Failures

Decide which two failure modes to fix first in the prototype based on the intersection of resident habits and platform limitations.

| Channel | Strength | Failure Mode | Accessibility Notes | Relevance to Elderly/LEP |
| Instagram (e.g., RVAHub) | Wide reach and visual appeal [7] | Algorithmic limits and throttling | Visual-only interface | Mixed to Low |
| Facebook Events | Group discovery and sharing | Duplicates and out-of-date info | Requires active account | Mixed |
| CultureWorks Calendar | Centralized regional data [2] | May miss small/underground orgs | Web literacy required | Good with print options |
| City Cultural Arts | Official municipal backing [8] | Limited to city-run facilities | Web only | Good with printouts |
| Word of Mouth | High trust and curation | Non-scalable | N/A | Strong |

*Takeaway: If intercepts confirm social media dominance, the prototype must prioritize social cross-post automation and a clean, mobile-first landing page that bypasses algorithmic filtering.*

## Gap 3: Arts/Cultural District Boundary Data — Timebox search; default to neighborhoods

A geographic arts discovery tool depends on usable boundary data. However, current findings did not confirm an official arts or cultural district layer on the Richmond GeoHub. The team must not stall on map scaffolding.

### 20-Min GeoHub Protocol

Spend exactly 20 minutes searching rvagis.richmond.gov using keywords "arts," "cultural," and "district." If no verified boundary layer surfaces, switch immediately to fallback layers.

### Table — Map Layer Options and Fit

Neighborhoods or council districts serve as highly viable substitutes that align with resident mental models.

| Layer | Availability | Pros | Cons | Use in Demo |
| Arts/Cultural District | TBD on GeoHub | On-brand and specific | May not exist digitally | Only if found in 20 mins |
| Neighborhoods | Likely available | Intuitive to residents | Varies greatly in size | Default fallback |
| Council Districts | Likely available | Official civic boundaries | Large, imprecise polygons | Secondary filter |

*Takeaway: Adopt Neighborhoods as the default mapping scaffold to maintain momentum, noting in the documentation that the tool can be upgraded to district boundaries when data becomes available.*

## Gap 4: Oral History Collections & Access — Seed content from The Valentine now; verify others

A neighborhood history explorer tool needs immediate seed content. The Valentine provides extensive, publicly accessible digital collections right now, allowing the team to build the prototype while verifying access at other institutions.

### The Valentine: Richmond Stories, Podcasts, Audio Guides, Database

The Valentine's Richmond Stories hub offers multiple public entry points. It includes a podcast archive with at least four pages of episodes, audio tours like "Sculpting History," and an actively growing online collection database [4] [5] [6]. The museum's research library also houses robust oral histories capturing firsthand accounts and community memories [9]. Furthermore, projects like *Voices from Richmond’s Hidden Epidemic* feature specific oral histories collected from survivors and activists [10].

### Outreach Checklist: BHMVA, VCU Libraries, VMHC

While The Valentine provides immediate seed data, the team must contact the Black History Museum & Cultural Center of Virginia (BHMVA), VCU Libraries, and the Virginia Museum of History & Culture (VMHC) via email or webforms during the hackathon to clarify what is digitally accessible versus what requires on-site institutional access.

### Table — Institution Access Matrix

Know exactly what content can be legally surfaced and mapped for the Sunday demo.

| Institution | Public Digital Content | Formats | Access Notes | Link |
| The Valentine | Yes | Podcast, audio guide, catalog [5] [6] | Public browse; attribution needed | thevalentine.org |
| BHMVA | TBD | TBD | Contact needed during hackathon | TBD |
| VCU Libraries/SC&A | TBD | TBD | Contact needed during hackathon | TBD |
| VMHC | TBD | TBD | Contact needed during hackathon | TBD |

*Takeaway: Curate 10–20 items from The Valentine's public assets into a lightweight story map immediately, documenting licensing rules and flagging what needs institutional approval before scaling.*

## Gap 5: Storytelling Channels for Target Populations — Voice-first, bilingual, minimal-step design

A story collection tool designed without understanding target population preferences will default to formats that exclude the most valuable contributors, particularly elderly residents, those with limited digital access, and non-English speakers.

### Evidence Synthesis: Voice access works if supported

Research indicates a "digital push" to increase technology adoption among older adults, but barriers like lower digital literacy, functional impairment, and outdated infrastructure persist [3]. However, older adults show behavioral intentions toward using voice assistants [11]. A telephone-based support program successfully engaged 27 older adult callers, though only two interviews were conducted in Spanish, underscoring a critical need for better language access [12]. StoryCorps guidelines emphasize asking follow-up questions that require descriptive answers [13].

### Design Pattern Pack

To lower friction, the team must stand up a dial-in story line (e.g., via Twilio) with a 2-minute voice capture limit, bilingual (English/Spanish) menus, and an optional callback feature. Pair this with WhatsApp voice-note intake for users without traditional carrier plans.

### Table — Channel Options vs. Barriers/Mitigations

Choose channels that lower friction immediately and plan to add complex integrations later.

| Channel | Barrier | Mitigation | Weekend Feasibility |
| Phone hotline | Language access, call length [12] | Bilingual IVR, 2-min hard cap | High |
| WhatsApp voice | App dependency | QR code flyers, library help | Medium |
| Web recorder | Browser permissions, digital literacy [3] | Single-button UI, fallback phone number | Medium |
| In-person kiosk | Staffing and physical access | Library partners, volunteer hours | Low–Medium |

*Takeaway: A voice-first telephone hotline with bilingual prompts is the most inclusive and feasible intake channel to build during the 48-hour window.*

## Gap 6: Continuation Champion — Map prototypes to named owners with explicit asks

Without a confirmed, named departmental or institutional champion, even a successful hackathon prototype has no home post-event. Both targeted problem statements currently lack a continuation pathway.

### Table — Prototype-to-Champion Fit

Increase adoption odds by aligning the built tool with the champion's current operations and mission.

| Prototype | Best-Fit Champion | Why | The Ask on Demo Day |
| Aggregator Lite | CultureWorks (Todd Waldo) | Operates the existing region calendar [2] | Host/maintain the tool, provide feed access, integrate with newsletter |
| Story Explorer | The Valentine (Meg Hughes) | Curates Richmond Stories and oral histories [9] [5] | Provide curatorial guidance, manage content rights, oversee ongoing ingest |
| Neighborhood Oral Histories | BHMVA / VMHC (Sylvio Lynch III / Chaya Braxton) | Mission-aligned with community history | Lead outreach to specific communities, provide archive/storage |

*Takeaway: Tailor the champion to the specific build. Make the continuation ask explicit during the final pitch on stage.*

## Gap 7: Output Type Specification — Decide in Hour 1; pick one of two scoped demos

The project brief lacks an output specification. Output type determines architecture, scope, and demo strategy. Indecision will kill weekend velocity.

### Option A: Arts Aggregator Lite

Focus on data consolidation. The deliverable is a web-based calendar view powered by 1 Localist feed integration plus 5 manually audited organizations, featuring an email export function.

### Option B: Story Hotline + Map

Focus on inclusive civic engagement. The deliverable is 1 functional phone line, 10 pre-recorded stories seeded from The Valentine, 1 map layer (neighborhoods), and a public listening page.

### Table — Option Tradeoffs

Choose the output based on team skills, data availability, and champion alignment.

| Option | Data Dependency | Inclusion Impact | Demo "Wow" Factor | Monday Sustainment |
| Aggregator Lite | Feeds and manual entry | Medium | High (live, populated calendar) | High (if adopted by CultureWorks) |
| Story Hotline + Map | Content rights and audio files | High (voice-first access) | Medium (voices playing on a map) | High (if adopted by The Valentine) |

*Takeaway: Make an irreversible decision in the first hour, document it in `working_direction_note.md`, and constrain the scope to these exact numeric goals.*

## Execution Plan — 48-hour timeline, roles, and tools

Timebox the seven gaps to ensure parallel progress across auditing, interviewing, and building.

### Day 1 (AM): Decide output, confirm Localist feeds, start 15–20-site audit, run 3–5 intercepts
Lock the output type immediately. The tech lead investigates Localist endpoints while the data team begins the 15-20 site manual audit. Simultaneously, the design/research lead conducts 3-5 intercept interviews to validate discovery channels.

### Day 1 (PM): Build MVP data ingest/map, stand up hotline, seed 10–20 Valentine items
Based on the morning's decision, either build the calendar ingest pipeline or stand up the Twilio hotline. Extract 10-20 audio assets from The Valentine's public podcast or audio tour archives [4] [6] to populate the map prototype.

### Day 2: Polish UI, prep demo narrative, secure champion quotes/attendance
Finalize the user interface. Draft the pitch deck focusing on the AEP6 demand statistics [1]. Reach out to the selected champion to secure a quote or confirm their attendance for the live ask.

## Risks & Mitigations — Avoid the common hackathon traps

Pre-commit to fallbacks and non-digital channels to maintain momentum when dependencies fail.

### Table — Top Risks and Fast Mitigations

Keep the project moving even if a primary data source or dependency breaks.

| Risk | Impact | Mitigation |
| Localist feed unavailable | Severe data gap for Aggregator | Pivot to manual 5-org entry and CSV import |
| No arts-district layer | Mapping stall | Use Neighborhoods immediately; label "upgrade later" |
| Content rights unclear | Blocked stories for Map | Use only public Valentine assets [5]; get written OKs |
| Champion no-show | No continuation pathway | Pre-ask via email; record a quote to play during pitch |

*Takeaway: Do not let missing ideal data stop the build; immediately execute the documented mitigations to ensure a working demo.*

## Demo-Day Narrative — Problem, proof, product, partner, plan

Lead with the discovery pain, show the working product, cite the massive community demand, and make the explicit continuation ask.

### Slide Flow (Problem → Evidence → Solution → Impact → Ask)

Anchor the presentation on the AEP6 data showing 85.3% of attendees value arts in their community [1]. Demonstrate how the prototype solves the fragmentation problem (via Localist integration) or the digital exclusion problem (via inclusive voice channels). Conclude by directly addressing the chosen champion (e.g., Todd Waldo or Meg Hughes) to adopt the continuity-ready solution.

## References

1. *From Inspiration to Impact: The Comprehensive Benefits of Arts and Culture in Richmond and the Tri-Cities   — CultureWorks*. https://richmondcultureworks.org/blog/frominspirationtoimpact-aep6
2. *CultureWorks (Richmond)*. https://richmondcultureworks.org/
3. *
            Using Voice-Activated Technologies to Enhance Well-Being of Older Adults in Long-Term Care Homes - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC11630282/
4. *Podcast Archive - Page 2 of 4 - The Valentine Museum*. https://thevalentine.org/explore/richmond-stories/podcast/page/2/
5. *Richmond Stories® - The Valentine Museum*. https://thevalentine.org/explore/richmond-stories/
6. *Sculpting History - Audio Tour - The Valentine Museum*. https://thevalentine.org/explore/richmond-stories/audio-guide/sculpting-history-audio-tour/
7. *RVAHub (@rvahub) • Instagram photos and videos*. https://www.instagram.com/rvahub/
8. *Cultural Arts | Richmond*. https://www.rva.gov/parks-recreation/cultural-arts
9. *The Valentine Museum: Uncovering Richmond's Deep-Rooted History and Evolving Urban Tapestry - Wonderful Museums*. https://www.wonderfulmuseums.com/museum/the-valentine-museum/
10. *25 Years and Counting Voices from Richmond's ...*. https://thevalentine.org/wp-content/uploads/2023/11/19VAL1778_AutumnWinterTimeline_r4.pdf
11. *Older adults’ intention to use voice assistants: Usability and emotional needs - ScienceDirect*. https://www.sciencedirect.com/science/article/pii/S2405844023091405
12. *Implementing a telephone‐based support program to address loneliness in older adults - Perissinotto - 2025 - Annals of the New York Academy of Sciences - Wiley Online Library*. https://nyaspubs.onlinelibrary.wiley.com/doi/full/10.1111/nyas.70029
13. *Some guidelines on how to conduct a good oral history ...*. https://archive.storycorps.org/question-lists/some-guidelines-on-how-to-conduct-a-good-oral-history-interview/