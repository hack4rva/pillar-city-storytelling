# Verification TODO — A City That Tells Its Stories

Items that must be verified before building to avoid wasted work. Each item is a known gap from the rubric working session or a plausible assumption that has not been confirmed.

Check off each item as your team confirms it during the hackathon. Log the result in `evidence_log.md`.

---

## Priority 1 — Verify Before Picking Your MVP Shape

- [ ] **Eventbrite API access**: Register an API key at https://www.eventbrite.com/platform/api. Confirm you can retrieve Richmond-area events with category filtering. Note rate limits.
- [ ] **Facebook Events API status**: Confirm that public event data is not accessible via the Graph API without extensive app review. Do not plan around this.
- [ ] **dorichmond.com coverage**: Visit dorichmond.com and assess what types of events it covers. Does it include gallery openings? Small neighborhood events? Is it actively maintained? This is your most important prior art check.
- [ ] **GeoHub neighborhood data**: Visit https://rvagis.richmond.gov and confirm that neighborhood boundary data exists and is downloadable as GeoJSON or compatible format.
- [ ] **GeoHub arts/cultural district data**: Confirm whether arts or cultural district boundaries exist as a specific layer. If not, note this gap — neighborhood boundaries are the fallback.

---

## Priority 2 — Verify Before Building Data Pipeline

- [ ] **Style Weekly events structure**: Visit https://styleweekly.com/richmond/event-search and assess whether events are in a structured, scrapable, or RSS-accessible format.
- [ ] **RVA Magazine events**: Visit https://rvamag.com/events and assess structure.
- [ ] **VMFA events feed**: Visit https://vmfa.museum and check for iCal or RSS link on their events calendar.
- [ ] **ICA at VCU events**: Visit https://icavcu.org and check for calendar feed.
- [ ] **At least 3 more arts organizations**: Pick 3 mid-size Richmond arts organizations and check each for calendar feed accessibility. Log results in evidence_log.md.

---

## Priority 3 — Verify Before Finalizing Story Collection Design

- [ ] **The Valentine digital collections**: Visit https://thevalentine.org and assess whether any oral history content is publicly accessible online for integration or linking.
- [ ] **VCU Libraries digital collections**: Visit https://library.vcu.edu/collections/digital/ and assess Richmond-focused oral history or neighborhood documentation materials.
- [ ] **StoryCorps Richmond content**: Search https://archive.storycorps.org for Richmond, VA stories. Confirm whether Richmond has coverage and how it is searchable.
- [ ] **Consent language review**: Before launching any story collection feature, have at least one non-engineer read the consent language aloud and confirm it is understandable to a non-technical user.

---

## Priority 4 — Verify Before Demo

- [ ] **All event sources show real Richmond events**: Your demo must show real Richmond data, not placeholder text. Verify each source is returning actual upcoming Richmond events.
- [ ] **Attribution is visible**: Every event card or story submission must trace back to its original source organization. Verify this is visible in your UI.
- [ ] **Representational bias disclaimer**: If your tool shows any aggregated insight from story submissions (themes, counts, maps), verify that a disclaimer is visible: "Based on voluntarily submitted stories — not a representative sample."
- [ ] **Mobile view tested**: Test your demo on a phone. Many judges will use mobile.
- [ ] **Consent flow tested end-to-end**: If building a story collection tool, submit a test story through the full consent flow and confirm it stores correctly.

---

## Items Confirmed as Out of Scope

These items appeared in initial ideation but are confirmed unsuitable for a weekend hackathon. Do not invest time in them:

- Comprehensive manual Richmond arts calendar (requires ongoing City staff curation — will decay)
- Facebook Events data integration (API severely restricted — not accessible in 48 hours)
- Replacing The Valentine's or Black History Museum's oral history work (requires institutional partnership that cannot be established in a weekend)
- Policy recommendation engine from resident stories (overclaims what a weekend prototype can do)
- Automated City procurement or endorsement of any story or event content
