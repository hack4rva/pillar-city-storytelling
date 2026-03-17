# Richmond Arts Data Playbook — Buildable Feeds, Blocked APIs, and Partner Paths

## Executive Summary

For hackathon teams tackling the "A City That Tells Its Stories" pillar, the path to a working prototype requires navigating a fragmented digital landscape. Public event data in Richmond is findable but scattered. CultureWorks operates a Localist-powered calendar [1], and VPM directs audiences to Style Weekly’s Artsline [2]. However, relying on Facebook Events is a dead end, as structured access is now restricted to Marketing Partners [3]. 

Audience discovery remains highly multi-channel, relying heavily on community-led platforms like Reddit's r/rva weekend threads [4], Instagram, and in-person rituals like First Fridays [5]. Fortunately, the region's arts network is robust enough to support direct partner ingestion, with the nonprofit arts sector generating $329.9 million in economic impact in 2022 and encompassing 93 organizations [6]. 

The most time-sensitive and "shovel-ready" civic opportunity for a 48-hour hackathon is arts aggregation. Story collection, while urgent due to neighborhood change, requires parallel scoping for consent protocols and institutional agreements that are not yet documented. Teams should build an aggregation MVP using accessible feeds while drafting a comprehensive consent framework for future oral history pilots.

## Events Data Landscape — Localist and Style Weekly are immediate ingestion anchors; Facebook is not

Start with buildable feeds, not proprietary social media APIs. CultureWorks and Style Weekly provide the most validated and immediately useful starting points for event aggregation.

| Source | Platform/Notes | Machine-readable outputs (status) | Integration action |
| :--- | :--- | :--- | :--- |
| CultureWorks Arts & Culture Calendar | Localist-powered ("Widget powered by Localist") [1] | Localist typically offers RSS/iCal; confirm in UI or via standard endpoints | Attempt RSS/ICS discovery; if absent, parse HTML widget; request partner access |
| Style Weekly Artsline | Media calendar promoted by VPM [2] | Feed unknown; likely HTML list | Parse event cards; seek syndication/data-sharing to stabilize |
| Visit Richmond events | DMO/tourism listing | Feed unknown | Check for iCal/RSS; if none, limited scrape as tertiary source |
| VMFA calendar | Major institution | Feed unknown | Contact for ICS/RSS; if none, HTML parse with caching |
| Richmond Public Library events | Library system | Feed unknown | Check for ICS; otherwise HTML parse; library often supports iCal |

**Key Takeaway:** An MVP can cover a meaningful share of high-interest events with just two connectors (CultureWorks and Artsline) plus a public submission form. Run a brief feed discovery pass for the remaining institutional sources.

## DoRichmond Coverage & Gaps — Needs verification; assume complementary rather than comprehensive

Attempts to profile dorichmond.com’s coverage, categories, and feeds yielded no analyzable data in this research cycle. Betting on opaque coverage risks duplicating effort or missing underserved arts niches, such as small galleries, BIPOC organizations, and neighborhood events.

**Action:** Execute a 1-day gap audit. Sample 100 events across CultureWorks, Artsline, and major institutions, then check their presence on DoRichmond. Document missing categories and any feed/export options before deciding whether to augment or differentiate from their platform.

## How Richmond Residents Discover Events — Media calendars + Reddit + Instagram + in-person rituals

Event discovery in Richmond is not platform-unified; it is community-led. Design your tools for multi-channel discovery and user-generated content (UGC) capture.

| Channel | Evidence | Strengths | Gaps |
| :--- | :--- | :--- | :--- |
| Style Weekly Artsline | VPM directs audiences here for a "full calendar... every day" [2] | Broad, updated, media-backed | Feed unknown; potential scraping fragility |
| r/rva Weekend Thread | Weekly open call for events on Reddit [4] | Hyperlocal, participatory | Unstructured; ephemeral |
| Instagram/Meetup/FB groups | Reddit advice cites IG (e.g., RestlessRVA), Meetup, FB [5] | Fast, scene-centric | Hard to ingest; platform silos |
| First Fridays/Gallery walks | Reddit mentions First Fridays as a go-to [5] | High signal for arts crowd | Offline; requires manual data entry |

**Key Takeaway:** Build distribution alongside aggregation. Publish a weekly digest, auto-post highlights to r/rva, and feature First Fridays to align with existing community habits.

## Facebook Events API Reality Check — Events data restricted to Marketing Partners; plan around it

Treat Facebook as a distribution channel, not a data source. Meta has universally restricted the ability to import Facebook events to external sites for general use [7]. 

Currently, access to Events on Users and Pages via the Graph API is strictly limited to Facebook Marketing Partners [3]. Furthermore, Meta's Graph API v25 introduces ongoing deprecations and changes, underscoring the fragility of relying on their proprietary endpoints [8]. 

**Action:** Exclude Facebook ingestion from the hackathon scope. Favor open standards (RSS/ICS/email ingests) and human-in-the-loop curation.

## Partner Network for Data & Stories — AEP6 identifies 93 orgs; target 10–20 for data-sharing

Partnership beats scraping for data quality and sustainability. The Richmond and Tri-Cities nonprofit arts sector is massive, generating $329.9 million in economic activity in 2022 and supporting 6,742 jobs [6]. The recent AEP6 study collected financial data from 93 local nonprofit arts and culture organizations [6].

| Organization (AEP6 participant) | Type | Likely data channel | Next step |
| :--- | :--- | :--- | :--- |
| Virginia Museum of Fine Arts (VMFA) | Museum | Site calendar | Request ICS/RSS; map schema |
| Virginia Museum of History & Culture (VMHC) | Museum | Site calendar | Outreach for feed/export |
| The Valentine | Museum/History | Exhibits/events | Co-design story pilot scope |
| Afrikana Film Festival | Festival | Seasonal schedule | Explore Eventbrite/own site |
| Firehouse Theatre | Performing arts | Performance calendar | Request season schedule/feeds |
| Visual Arts Center of Richmond | Arts education | Class/event calendar | ICS export or CSV email |
| Richmond Symphony | Performing arts | Season calendar | Bulk season import |
| Studio Two Three | Community arts | Programs/events | Feed request + submission SOP |

**Key Takeaway:** Stand up a "Top 20 Partners" program. Offer a 30-minute onboarding session and a simple submission template (RSS/iCal/email) to secure reliable data pipelines.

## Oral History & Neighborhood Story Collections — Visibility unknown; validate digital accessibility first

The specific digital oral-history portals and rights frameworks for The Valentine, Black History Museum, VCU Libraries, and VMHC are currently undocumented in this research cycle. 

**Action:** Before building tools, inventory access and rights. Create a discovery worksheet tracking collection names, URLs, digital accessibility, rights/consent, and bulk export options. Schedule brief calls with each institution to identify pilot content.

## Inclusive Storytelling Channels for Older, Non-digital, LEP Residents — Hypotheses to test locally

Reliance on digital-first channels risks excluding older residents, non-digital users, and those with limited English proficiency (LEP). 

**Action:** Pilot low-tech capture modes with trusted intermediaries (libraries, senior centers). Test phone hotline/voicemail stories, paper postcards with scan-and-upload capabilities, and bilingual in-person recording pop-ups to measure participation and consent clarity.

## Consent & Privacy Frameworks for Story Collection — Borrow from StoryCorps/Historypin; design for city use

Consent for civic story collection must be explicit, revocable, and written in plain language. 

**Action:** Compile reference policies from established platforms like StoryCorps and Historypin. Draft a framework that includes tiered consent (public, community-only, private), a clear revocation workflow, media releases, language access (EN/ES), and strict data retention policies. Review this with city legal teams before any collection begins.

## Named Champions & Institutional Capacities — Validate roles and secure commitments

Champions such as Todd Waldo, Meg Hughes, Sylvio Lynch III, and Chaya Braxton have been identified, but their specific institutional capacities for post-hackathon continuation need validation.

**Action:** Confirm each champion's institutional home, decision authority, and availability. Propose specific roles (e.g., data partnership lead, consent advisor) and secure 60–90 day commitments to ensure project continuity after the hackathon.

## Time-Sensitive Opportunity: Aggregation Now, Story Collection Scoped Next — De-risk with a two-track plan

For the hackathon timeline, arts aggregation is the immediate win, while story collection requires careful, parallel scoping.

| Dimension | Arts aggregation | Story collection |
| :--- | :--- | :--- |
| Data readiness | High: CultureWorks (Localist) [1], Style Weekly Artsline [2] validated | Low-Medium: Unknown digital access/rights at key institutions |
| External dependencies | Medium: partnerships help but not required to start | High: requires consent framework + institutional MOUs |
| Community urgency | Ongoing: constant need to know "what's on" | High but sensitive: aging residents imply urgency, but consent is critical |
| Build effort (hackathon) | Low-Medium: 2-3 connectors + submission form + digest | Medium-High: capture UX, consent flows, storage, governance |

**Key Takeaway:** Ship an aggregator MVP in the first 2-4 weeks using Localist and Artsline connectors. Simultaneously, draft the story-collection consent framework and hold stakeholder reviews with key museums to define a 60-90 day pilot.

## References

1. *CultureWorks (Richmond)*. https://richmondcultureworks.org/
2. *Explore Virginia's Arts and Culture with VPM | Documentaries, Events & More*. https://www.vpm.org/arts-and-culture
3. *Event - Graph API Reference - Meta for Developers*. https://developers.facebook.com/docs/graph-api/reference/event/
4. *Reddit - el corazón de la conversación*. https://www.reddit.com/r/rva/comments/1rlfspo/weekend_event_thread/
5. *What places/events would you recommend to get into the ...*. https://www.reddit.com/r/rva/comments/y969ez/what_placesevents_would_you_recommend_to_get_into/
6. *Arts & Economic Prosperity 6 Study - Richmond*. https://richmondcultureworks.org/economic-impact-aep6
7. *Important Facebook API Changes | The Events Calendar*. https://theeventscalendar.com/blog/news/important-facebook-api-changes/
8. *Introducing Graph API v25.0 and Marketing API v25.0I*. https://developers.facebook.com/blog/post/2026/02/18/introducing-graph-api-v25-and-marketing-api-v25/