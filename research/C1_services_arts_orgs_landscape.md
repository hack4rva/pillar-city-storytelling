# Unlocking Richmond Arts: Where Event Data Lives and How to Ingest It

## Executive Summary

* **Structured data is patchy across major institutions**: Three of five sampled majors expose some iCal hooks (Richmond Symphony offers a global ICS export [1]; Richmond Ballet provides "iCalendar/Outlook" links on its season [2]; Firehouse Theatre offers per-event Google/ICS links [3]). Conversely, the Virginia Museum of Fine Arts (VMFA) and the Institute for Contemporary Art (ICA) at VCU show no obvious site-wide ICS/RSS feeds [4] [5]. Prioritize ICS-ready organizations for Phase 1 ingestion, and queue lightweight scrapers alongside a partner ask for VMFA/ICA to provide.ics endpoints.
* **Eventbrite is the de facto CMS for key community venues**: Gallery5's Eventbrite organizer page boasts 1.6k followers, 640 total events, and 17 upcoming events [6]. Stand up an Eventbrite integration keyed to verified organizer IDs to quickly expand community coverage while cultivating direct feeds from non-Eventbrite organizations.
* **"Add to Calendar" does not equal a true feed**: Firehouse Theatre exposes per-event Google/ICS links [3] and Richmond Ballet offers a season-level iCal [2], but neither constitutes a continuously updated, organization-wide feed. Build a crawler to capture per-event ICS when present, but concurrently offer partners a free, hosted organization-level.ics/JSON feed to reduce maintenance overhead and errors.
* **University and institution calendars are rich but closed**: ICA at VCU lists numerous upcoming items with robust tagging and filtering, but lacks a visible export [5]. VMFA emphasizes its on-site calendar and email newsletter signups [7] [8]. Implement structured HTML scraping with schema.org/Event microdata detection, and approach ICA/VMFA with a low-lift add-on (.ics export) to convert them into high-fidelity sources.
* **Marketplace proximity creates misattribution risk**: Eventbrite surfaces "events near VMFA" that are not official museum programs [9]. Restrict marketplace ingestion to verified organizers (e.g., Gallery5's organizer page) and official domains to avoid location-only queries that pollute data and damage trust.
* **Underrepresented-community programming risks under-coverage without partnerships**: Elegba Folklore Society's events live on its own site [10], and the Latin Ballet of Virginia maintains an internal calendar [11]; neither shows obvious RSS/ICS feeds. Launch a community inclusion track: assign a curator, subscribe to their lists, and provide a no-cost "publish-once to.ics/JSON" tool to these organizations to ensure representation.
* **Email still carries weight across majors**: VMFA promotes newsletter signups on its calendar [7]; Richmond Symphony's calendar prompts newsletter subscriptions [1]; ICA includes a "Join Our List" call-to-action [5]. Build a "newsletter-to-events" parser (subject/date/time detectors plus human QA) so email announcements do not become blind spots.
* **Seasonality enables proactive seeding**: Richmond Ballet's 25/26 season spans September 11, 2025, through May 24, 2026, with named programs and a VMFA venue tie-in [2]. Pre-seed season shells for majors (ballet, symphony, theater) 6–9 months ahead, and backfill exact times as announced to boost perceived completeness.
* **Channel fragmentation complicates deduplication and UX**: Richmond Ballet tickets via eTix [2], the Symphony runs its own calendar and exports [1], and Gallery5 uses Eventbrite [6]. Maintain a source-of-truth registry mapping organizer, venue, and ticketing endpoints per organization, and deduplicate by organizer ID and canonical URL rather than event titles.
* **Tagging and category sprawl demand normalization**: ICA uses dozens of tags [5], Firehouse marks events as Mainstage/Fringe/New Plays [3], and VMFA mixes social, music, and shop events on one page [4]. Define a normalized taxonomy (Exhibition/Lecture/Film/Performance/Class/Community) and maintain organization-specific mapping rules to ensure consistent filtering and alerts.

## Purpose & Scope

This report maps the landscape of arts organizations, galleries, venues, and cultural institutions in Richmond, Virginia, to determine how they publish event information and where structured data lives. The objective is to build an ingestible map of Richmond arts organizations and their event data formats. By inventorying who publishes events where, identifying which sources are machine-readable, and highlighting gaps in coverage, we can design an ingestion plan that maximizes coverage with minimal custom work. This strategy ensures that major institutions, mid-size organizations, and underrepresented community spaces are accurately and comprehensively aggregated.

## Landscape Snapshot

The Richmond arts landscape reveals a fragmented approach to event publishing. Major institutions are mixed on their adoption of open feeds, while community venues heavily skew toward Eventbrite. Across the board, newsletters and proprietary websites remain the primary communication channels.

### Majors: VMFA, ICA at VCU, Richmond Symphony, Richmond Ballet, Firehouse

Three of the five sampled major institutions expose some form of iCal hooks, while two rely entirely on web calendars and email. The ingestion strategy must start with ICS-capable organizations and convert web-only calendars to feeds via scraping or strategic partnerships.

| Organization | Primary Channels | Structured Feed Availability | Ticketing | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Virginia Museum of Fine Arts (VMFA)** | Website calendar, newsletters, social | No visible org-level ICS/RSS | Internal | Featured events listed on homepage; newsletter signup prominent [7] [4]. |
| **ICA at VCU** | Website calendar with filters/tags, social, email list | No visible ICS/RSS | Free/open | Rich tagging system; no export observed [5]. |
| **Richmond Symphony** | Website calendar | Global ICS export (.ics, Outlook, Google) | Internal | Explicit "Export.ics file" and subscription links available [1]. |
| **Richmond Ballet** | Season/performance pages | Season "iCalendar/Outlook 365" links | eTix | 25/26 season spans Sep 11, 2025–May 24, 2026 [2]. |
| **Firehouse Theatre** | Events page | Per-event Google/ICS links | Internal | Many event types including Mainstage, Fringe, and New Plays [3]. |

*Key Takeaway*: The presence of global ICS exports at the Richmond Symphony provides an immediate ingestion win, whereas the VMFA and ICA will require custom scrapers or direct outreach to unlock their rich, web-bound event data.

### Community & Underrepresented-serving: Gallery5, Elegba Folklore Society, Latin Ballet, Richmond Triangle Players

Eventbrite drives structured data for some community organizations, but others rely strictly on their own websites, necessitating scrapers or the provision of new feed tools to ensure they are not left behind.

| Organization | Community Served | Primary Channels | Structured Feed Availability | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Gallery5** | Broad community arts | Eventbrite organizer, website | Yes (Eventbrite API) | Clean organizer ID for ingestion; 1.6k followers, 640 total events [6]. |
| **Elegba Folklore Society** | African World arts | Website events page | Not evident | Likely requires manual scrape and partnership for feed [10] [12]. |
| **Latin Ballet of Virginia** | Latino communities | Website calendar | Not evident | Calendar present; no visible export [11]. |
| **Richmond Triangle Players** | LGBTQ+ theatre | Website season pages | Not evident in sample | Requires direct check for feeds; 2024-25 season noted [13] [14]. |

*Key Takeaway*: Gallery5's robust Eventbrite presence allows for immediate API integration, but organizations like Elegba Folklore Society and Latin Ballet of Virginia will require proactive inclusion strategies to prevent their events from being omitted from the aggregator.

## Publishing Channels & Data Structures

Understanding the specific channels and data structures used by Richmond arts organizations dictates the technical approach. Eventbrite and ICS feeds represent low-effort wins, while university and major web calendars require scrapers and partnerships.

| Channel Type | Example Org(s) | Feed Availability | Integration Path | Key Risk |
| :--- | :--- | :--- | :--- | :--- |
| **Eventbrite Organizer** | Gallery5 | Yes | Eventbrite API by organizer ID | Proximity noise if using venue search instead of ID [9] [6]. |
| **Org ICS Feed** | Richmond Symphony | Yes | Direct.ics ingestion | Timezone and recurrence quirks [1]. |
| **Per-event ICS** | Firehouse, Ballet season | Partial | Page crawl + ICS parse | Fragile if URLs or titles change [3] [2]. |
| **Web Calendar (no export)** | VMFA, ICA | No | Structured HTML scraping + partner ask for.ics | Layout changes; missing metadata [4] [5]. |
| **Email Newsletters** | VMFA, Symphony, ICA | No | NLP parser + manual QA | Date extraction errors; latency [7] [1] [5]. |

*Key Takeaway*: The integration path must be bifurcated: utilize APIs and direct feeds where available (Eventbrite, Symphony), and deploy resilient scrapers for the rest while actively lobbying for standardized exports.

## Aggregation Gaps & Risks

Relying solely on easily accessible feeds will result in significant blind spots. Without scrapers and partnerships, an aggregator will miss website-only and community events, and risk misattributing marketplace listings.

* **Newsletter-only drops**: Organizations like VMFA frequently use email announcements [7]. If email parsing is not in place, exclusive or early-access events will be missed.
* **Website-only calendars**: The ICA, Elegba Folklore Society, and Latin Ballet of Virginia rely on their websites [5] [10] [11]. Without scrapers or provided feeds, these organizations will be entirely absent from the platform.
* **Per-event ICS limitations**: Firehouse Theatre and Richmond Ballet offer ICS links per event or season [3] [2], but lacking a dynamic, organization-wide feed inflates maintenance costs and risks missing newly added events.
* **Eventbrite location queries**: Searching Eventbrite for events "near VMFA" surfaces unrelated activities [9], causing brand misattribution and degrading the quality of the aggregated data.

## Inclusion Strategy

To ensure underrepresented communities are covered, technical ingestion must be paired with relationship-building and feed enablement.

* **Community partner program**: Offer free, hosted.ics/JSON feeds to organizations like Elegba Folklore Society and Latin Ballet of Virginia. This removes the technical burden from the organizations while guaranteeing structured data for the aggregator.
* **Ambassador curation**: Institute a monthly 2–4 hour manual sweep of community calendars and social media confirmations to catch events that fall through the automated cracks.
* **Distribution value**: Provide sharable calendar embeds to partners to incentivize their participation and regular updating of their event data.

## Technical Plan

The build order should prioritize immediate value through existing APIs, followed by custom scrapers, and finally partner enablement.

* **Sprint 1 (Weeks 1–3)**: Focus on Eventbrite organizer ingestion (e.g., Gallery5) and direct ICS ingestion (e.g., Richmond Symphony). Establish the base taxonomy and deduplication logic.
* **Sprint 2 (Weeks 4–6)**: Develop the per-event ICS crawler for Firehouse Theatre and Richmond Ballet. Build HTML scrapers for the ICA and VMFA. Launch an MVP for the newsletter parser.
* **Sprint 3 (Weeks 7–9)**: Roll out the partner feed program, including an.ics generator and onboarding kit. Implement QA dashboards and alerting systems for when scraper layouts break.

## Data Quality & Taxonomy

Normalizing data and preventing misattribution are critical for user trust.

* **Deduplication**: Deduplicate events by organizer ID and canonical URL, not by event titles, which frequently change or vary across platforms.
* **Normalization**: Map organization-specific labels (e.g., Firehouse's "Fringe" [3] or ICA's extensive tags [5]) to a common schema: Exhibition, Lecture, Film, Performance, Class, and Community.
* **Confidence scoring**: Downgrade or flag events that do not originate from verified organizers to prevent marketplace noise from polluting the core calendar.

## Partnerships & Governance

Simple, low-lift asks can unlock high leverage and significantly improve data reliability.

* **Technical Outreach**: Provide a template email and code snippet to organizations like VMFA and ICA, demonstrating how easily they can add an.ics export to their existing web calendars.
* **Reciprocity**: In exchange for structured data, offer these organizations analytics on event views, calendar embeds for their own sites, and cross-promotion opportunities.

## KPIs & Milestones

Measure the success of the aggregation strategy through coverage and reliability metrics.

* **Coverage**: Track the percentage of major, mid-size, and community organizations that have automated feeds established.
* **Freshness**: Measure the median hours from when an organization publishes an event to when it appears in the aggregator.
* **Quality**: Monitor the duplicate rate and track any misattribution incidents.
* **Inclusion**: Count the number of underrepresented-serving organizations successfully onboarded with automated feeds.

## Appendix

Initial source links inventory confirming feasibility and gaps:

* VMFA calendar and featured events [7] [4]
* Richmond Symphony calendar with.ics exports [1]
* ICA at VCU calendar (no visible export) [5]
* Richmond Ballet 25/26 season (iCalendar/Outlook links; eTix ticketing) [2]
* Firehouse Theatre events (per-event Google/ICS) [3]
* Gallery5 Eventbrite organizer (1.6k followers; 640 total events; 17 upcoming) [6]
* Elegba Folklore Society events page [10]
* Latin Ballet of Virginia calendar [11]

## References

1. *Events from March 17, 2026 – February 28, 2015 – Richmond Symphony*. https://www.richmondsymphony.com/calendar
2. *25/26 Season - Richmond Ballet*. https://richmondballet.com/event/25-26-season/
3. *Tickets — FIREHOUSE THEATRE*. https://www.firehousetheatre.org/events
4. *Virginia Museum of Fine Arts*. https://www.vmfa.museum/
5. *Calendar - Institute for Contemporary Art*. https://icavcu.org/calendar
6. *
    Gallery5 Events - 17 Upcoming Activities and Tickets | Eventbrite
*. https://www.eventbrite.com/o/gallery5-34329158675
7. *Calendar - Virginia Museum of Fine Arts*. https://www.vmfa.museum/calendar
8. *Program and Event Calendar - Virginia Museum of Fine Arts*. https://www.vmfa.museum/press/program-and-event-calendar
9. *events and things to do near virginia museum of fine arts*. https://www.eventbrite.com/poi/va--richmond/virginia-museum-of-fine-arts--lkHMN/
10. *Events | Elegba Folklore Society*. https://efsinc.org/events/
11. *Calendar of Events — The Latin Ballet of Virginia*. https://www.latinballet.com/calendar
12. *Elegba Folklore Society*. https://efsinc.org/
13. *Richmond Triangle Players – Richmond Triangle Players*. https://rtriangle.org/
14. *Production Page – 2024-25_Season*. https://rtriangle.org/2024-25_season/