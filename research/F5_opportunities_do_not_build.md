# Richmond F5 Guardrails — What Not To Build (and What To Do Instead)

## Executive Summary

Success at the Opportunity Spaces F5 hackathon requires choosing solvable, durable problems. Teams often gravitate toward ambitious but fundamentally flawed concepts that either violate platform policies, ignore ethical standards, or duplicate existing community infrastructure. This guide establishes seven strict "Do Not Build" guardrails to prevent teams from wasting their 48 hours on unviable projects. 

Key strategic pivots include:
* **Avoid manual calendars**: Richmond already has at least four active arts calendars. Build integration and submission bridges, not new destinations that will decay.
* **Abandon Facebook scraping**: Meta's strict API deprecations and anti-scraping policies make unauthorized event aggregation impossible in a weekend.
* **Reject "all-encompassing" story claims**: Nonprobability samples cannot represent the entire city. Acknowledge bias and build consent-first, ethically scoped collection tools.
* **Respect institutional oral histories**: Do not attempt to replace the rigorous, consent-driven archival processes of The Valentine or the Black History Museum & Cultural Center of Virginia (BHMVA).
* **Drop sentiment-to-policy engines**: Natural Language Processing (NLP) models exhibit documented bias against African American English, making automated policy recommendations actively harmful.
* **Bypass official City endorsements**: Procurement laws and brand guidelines make securing official City of Richmond approval impossible during a hackathon.
* **Mandate explicit consent**: Collecting resident stories without clear, opt-in consent violates modern privacy standards (VCDPA, GDPR) and oral history best practices.

By recognizing the red flags of out-of-scope pitches, teams can pivot to partner-first, consent-centric builds that provide immediate, lasting value to the Richmond community.

## Purpose and Guardrails — Focus the F5 Weekend on What Will Last

The goal of this weekend is to build tools that empower the community, not to create maintenance traps or ethical liabilities. Each of the seven restricted zones below represents a proven dead-end for a 48-hour sprint. Understanding *why* these ideas fail allows teams to pivot toward safe, adjacent lanes that actually solve the underlying problems.

### The Seven "Do Not Build" Commitments, at a Glance

The following table outlines the restricted concepts, the specific reasons they are out of scope, viable alternatives, and the warning signs that a team is drifting off course.

| Idea (Do Not Build) | Why Out of Scope This Weekend | Do This Instead (Viable Pivot) | Red-Flag Pitch Language |
|---|---|---|---|
| **Manually curated "Richmond arts calendar"** | Duplication and decay. Richmond already has 4+ active calendars with established submission pipelines. An ongoing editorial load is unsustainable for a hackathon project. | Build a "submit-once" helper; link/unify ICS/RSS feeds; create a deduplication widget or venue onboarding tool. | "The definitive calendar for all RVA arts," "We'll hand-curate everything," "Replace CultureWorks." |
| **Facebook Events aggregator** | Meta prohibits scraping without written permission [1]. The `user_events` permission is deprecated [2] [3], and Page events require App Review [4], which takes weeks. | Rely on organizer opt-in: accept ICS/Google Cal links; build an email-to-event parser; create a "Share to X calendars" button. | "We'll crawl all FB events," "AI scrapes public events," "Uses Facebook without App Review." |
| **"All Richmond resident stories" without bias note** | Nonprobability samples cannot represent populations [5] [6]. Claiming to represent "all" voices risks amplifying overrepresented groups and causing civic harm. | Narrow the scope; add a prominent bias statement; recruit via partners in specific areas; include optional demographics. | "All voices captured," "Representative of RVA," "We'll map every neighborhood this weekend." |
| **Replacement for museum oral histories** | The Oral History Association (OHA) requires training, consent, and archival planning [7] [8]. The Valentine and BHMVA have established, rigorous programs [9] [10]. | Build a co-branded intake and consent kit aligned to OHA standards; create metadata exports that museums can easily ingest. | "We'll run Richmond's official oral history," "Replace The Valentine/BHMVA workflows." |
| **Sentiment-to-policy engine** | NLP models misclassify dialects like African American English [11] [12]. Using small, biased samples for automated policy triage causes allocational harm [13]. | Provide human-coded themes, quotes, and counts with explicit caveats; publish a limitations section; avoid policy automation. | "AI will tell Council what to do," "Automated policy priorities from stories." |
| **Requires City endorsement or authentication** | City brand use requires authorization [14] [15]. Virginia Public Procurement Act (VPPA) timelines make official endorsement infeasible in 48 hours [16] [17]. | Use neutral branding; launch a community coalition beta; plan a post-hack request for official support. | "Official City platform," "City-sealed app," "Requires.gov auth at launch." |
| **Story collection without explicit consent** | The Virginia Consumer Data Protection Act (VCDPA) requires opt-in for sensitive data [18] [19]. OHA mandates informed consent [7]. | Ship consent as a first-class feature: detail the purpose, license, age gate, and withdrawal/deletion process. | "Implicit consent by submission," "We'll infer consent," "Collect now, add terms later." |

## Richmond Has Calendars—Don't Rebuild; Bridge Them

A common hackathon impulse is to build "one calendar to rule them all." This ignores the reality that Richmond's event infrastructure already exists. Building a new manual calendar creates an immediate maintenance trap that will decay the moment the hackathon ends. Instead of adding overhead, teams should build connective tissue that helps organizers syndicate their events across existing platforms.

### Four Active Calendars You Can Leverage Today

Richmond features multiple established calendars, each with its own editorial focus and submission pipeline.

| Platform | URL | How It's Maintained | Submission/Feed Path |
|---|---|---|---|
| **CultureWorks Events** | calendar.richmondcultureworks.org | Regional arts nonprofit championing arts and culture [20] | Public "Submit an event" form [20] |
| **Visit Richmond (Tourism)** | visitrichmondva.com/events | Professional editorial for regional events and festivals [21] | Finder tool; organizational submissions [21] |
| **VPM Artsline (Public Media)** | vpm.org/artsline | Broadcast and web listings sponsored by Modlin Center [22] | Submit via Style Weekly form (auto-feeds Artsline) [22] |
| **RVAHub** | rvahub.com/calendar | Community news site covering local neighborhoods [23] | Public event listings [23] |

**Action Plan:** Do not build a fifth calendar. Instead, build a "Submit Everywhere" helper that normalizes ICS/RSS feeds, pushes data to the CultureWorks and Style Weekly forms, and deduplicates high-signal events.

## Meta/Facebook Events: Why Aggregation Fails in 48 Hours

Teams frequently pitch tools that aggregate local events by scraping Facebook. This is a technical and legal non-starter for a weekend hackathon. 

Meta's Automated Data Collection Terms (effective October 7, 2024) explicitly prohibit engaging in automated data collection without express written permission, and Meta reserves the right to restrict collection at any time [1]. Furthermore, the Graph API has been severely locked down:
* The `user_events` permission is effectively deprecated, often returning empty arrays even when the permission is granted [2] [3].
* Third-party access to the Facebook Groups API was shut down in 2024 [24].
* Accessing Page events requires the `pages_read_engagement` and `pages_show_list` permissions, alongside Page access tokens [4]. Securing these requires a formal App Review process (including screencasts and business verification) that cannot be completed in 48 hours [4].

**Do Instead:** Ask organizers to provide their own page-managed ICS or Google Calendar feeds. Create a "Post once, syndicate to X calendars" UI, or build an email-to-event parser for organizers who do not use standard feeds.

## Ethical Story Collection: Consent, Bias, and Archiving Realities

Civic storytelling tools must be built on a foundation of trust. Launching a tool that claims to capture "all" Richmond stories without acknowledging bias or securing explicit consent causes active civic harm.

Consent is legally and ethically non-negotiable. The Virginia Consumer Data Protection Act (VCDPA) requires a clear, affirmative act signifying a consumer's freely given, specific, informed, and unambiguous agreement to process personal data, and mandates explicit opt-in for sensitive data (such as race, ethnicity, or precise geolocation) [18] [19]. Furthermore, the Oral History Association (OHA) requires obtaining and documenting the informed consent of the narrator [7] [8]. 

Additionally, the American Association for Public Opinion Research (AAPOR) warns that nonprobability samples (like self-selected hackathon story submissions) cannot be used to make inferences about a larger population [5] [6]. 

**Do Instead:** Ship a consent-first user experience. Include multilingual prompts, optional demographic fields, and a clear explanation of how the data will be used. Prominently feature a bias statement acknowledging that the collected stories represent a qualitative sample, not a comprehensive citywide census.

## Do Not Replace The Valentine or BHMVA Oral Histories

Richmond is home to institutions with deep expertise in preserving community narratives. The Valentine hosts community conversations and interactive history programs [9] [25], while the Black History Museum & Cultural Center of Virginia (BHMVA) actively collects and archives oral histories to preserve the rich culture of African Americans in Virginia [26] [27]. In 2019, BHMVA and the Virginia Museum of History & Culture (VMHC) formed a partnership to catalog and preserve these vital oral histories and artifacts [10].

Hackathon teams cannot replicate the ethical, legal, and archival requirements of these institutions in a weekend. OHA Best Practices dictate that oral historians must seek training, locate an appropriate repository with the capacity to preserve histories, and utilize formal legal release agreements [7] [28] [8]. 

**Do Instead:** Do not build a standalone repository. Instead, co-design a referral on-ramp. Build a consent kit aligned with OHA standards and create a metadata export function that matches the accession fields used by local museums, facilitating a smooth handoff of stories after the hackathon.

## Analytics Guardrails: No Sentiment-to-Policy Engines

Applying automated sentiment analysis to small, self-selected civic datasets is highly dangerous. Teams must not build engines that translate story submissions directly into automated policy recommendations.

Research demonstrates that Natural Language Processing (NLP) models trained on Standard American English frequently misclassify dialectal expressions, particularly African American English (AAE), often labeling neutral or positive AAE as negative or toxic [11] [12]. Relying on biased sentiment analysis tools for civic triaging or policy prioritization can lead to severe allocational harms [13]. Because nonprobability samples do not represent the broader population [6], using them to drive automated citywide policy is an overclaiming risk.

**Do Instead:** Keep analytics descriptive and human-in-the-loop. Provide tools for human-coded tagging, highlight specific quotations, and display theme counts with explicit caveats. Do not automate policy recommendations.

## City Endorsement and Branding Constraints

Teams cannot build tools that require official City of Richmond endorsement, branding, or authentication to function. Official status takes time, and the necessary approvals cannot be secured over a weekend.

The City of Richmond strictly controls its brand. The Office of the Press Secretary prepares and approves all City news releases and communications [29]. Furthermore, the official City logo is registered for protection, and section 2-2.2 of the City Code prohibits its unauthorized use [15]. Finally, any official adoption of a platform by the City would be subject to the timelines and processes of the Virginia Public Procurement Act (VPPA), which takes weeks or months, not days [16] [17].

**Do Instead:** Use neutral, independent branding. Include a clear disclaimer stating the project is "not affiliated with the City of Richmond." Design the tool for community groups first, and prepare a one-pager to request official support after the hackathon concludes.

## Platform Compliance: Never Scrape; Get Feeds with Permission

Scraping social platforms is a severe legal and compliance risk. Meta's Automated Data Collection Terms explicitly forbid automated data collection without express written permission [1]. Meta actively enforces these terms and has engaged in litigation against scraping entities [30]. Even when using approved endpoints, developers report that event retrieval can be brittle and inconsistent [31].

**Do Instead:** Only use approved APIs and owner-provided feeds. Offer "bring your own feed" patterns (such as ICS, Google Calendar, or Mailchimp RSS) and maintain a log verifying that organizers have granted permission to syndicate their content.

## Red-Flag Language Watchlist

Mentors and organizers should listen for the following phrases during team pitches. These signal that a team has drifted into out-of-scope territory and needs immediate coaching to reframe their project:

* "All Richmond stories" / "The official voice of RVA"
* "Scrape all Facebook events" / "AI crawls public events"
* "City-endorsed platform" / "Uses the City seal"
* "Replace The Valentine/BHMVA oral histories"
* "Automated sentiment to policy recommendations"
* "Implicit consent by submission" / "We'll add terms later"
* "The definitive Richmond arts calendar"

## Weekend-Ready Pivots and Build Plan

To ensure teams ship valuable, ethical, and partner-ready tools by Sunday, guide them toward these concrete, shippable alternatives:

* **Calendar Bridge Kit:** A "Submit Everywhere" form that pushes data to CultureWorks and Style Weekly; an ICS normalizer; a venue onboarding PDF; and deduplication logic.
* **Event Intake Pipeline:** A Google Form combined with an email parser that generates ICS feeds and pushes them to partner calendars, complete with an organizer dashboard showing "where listed."
* **Consent-First Story Microtool:** A platform featuring multilingual, plain-language consent, audio upload capabilities, a metadata export formatted for museum ingestion, and a clear data deletion request flow.
* **Qualitative Insights Board:** A dashboard for manual tagging with inter-rater agreement checks, generating a public "insights with caveats" page, and a framework for a future community validation session.
* **Partner Readiness Pack:** A draft MOU template, a data dictionary aligned to OHA standards, and a City-friendly one-pager designed for post-hackathon endorsement requests.

## Reality Check: Permissions and Reviews Timeline

Hackathon teams must design around the reality of external review timelines. Anything requiring third-party approval will not clear in 48 hours:
* **Meta App Review:** Requires screencasts, business verification, and typically takes days or weeks [4].
* **City Approvals:** Communications and brand use require prior approval [29] [15], and procurement cycles take weeks or more [16].
* **Museum Accessions:** Archiving oral histories requires institutional review cycles and formal legal releases [7] [28].

**Action:** Prioritize owner-provided feeds, neutral branding, and exportable artifacts that community partners can easily adopt and review *after* the hackathon concludes.

## References

1. *Automated Data Collection Terms*. https://www.facebook.com/legal/automated_data_collection_terms
2. *Facebook Graph API -> user/events returns empty array - Stack Overflow*. https://stackoverflow.com/questions/55933436/facebook-graph-api-user-events-returns-empty-array
3. *User events list is returning empty data in Graphql api event if ...*. https://developers.facebook.com/community/threads/635328195429961/
4. *Permissions Reference - Graph API - Meta for Developers*. https://developers.facebook.com/docs/permissions/
5. *Non-probability Sampling for Finite Population Inference ...*. https://aapor.org/wp-content/uploads/2023/01/AAPOR-October-Webinar_Presentation_for-participants.pdf
6. *REPORT OF THE AAPOR TASK FORCE ON NON*. https://aapor.org/wp-content/uploads/2022/11/NPS_TF_Report_Final_7_revised_FNL_6_22_13-1.pdf
7. *Oral History Best Practices - Oral History Association*. https://oralhistory.org/best-practices/
8. *OHA Principles and Best Practices*. https://oralhistory.org/wp-content/uploads/2022/08/OHA-Principles-and-Best-Practice-Print-Version-Updated-2022.pdf
9. *Community Conversations - The Valentine Museum*. https://thevalentine.org/explore/programs/community-conversations/
10. *BHMVA & VMHC: A Partnership for the Community*. https://virginiahistory.org/bhmva-vmhc-partnership-community
11. *
"NLP Bias and African American English" by Kenya Roy and Faizan Javed
*. https://scholar.smu.edu/datasciencereview/vol9/iss3/9/
12. *Evaluating and Mitigating Inherent Linguistic Bias of African American English through Inference - ACL Anthology*. https://aclanthology.org/2022.coling-1.124/
13. *
            Potential Pitfalls With Automatic Sentiment Analysis: The Example of Queerphobic Bias - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC10654032/
14. *Brand | Richmond*. https://www.rva.gov/strategic-communications/brand
15. *About Richmond | Richmond*. https://www.rva.gov/mayors-office/about-richmond
16. *Virginia Public Procurement Act*. https://law.lis.virginia.gov/vacodepopularnames/virginia-public-procurement-act/
17. *Procurement_Book_Final.docx*. https://www.vml.org/wp-content/uploads/2017/06/Procurement_Book_Final.docx
18. *Virginia Data Privacy Law Requires Opt-In For Sensitive Personal Data | Loeb & Loeb LLP *. https://www.loeb.com/en/insights/publications/2021/03/va-passes-comprehensive-data-privacy-law-requires-optin-for-sensitive-personal-data
19. *Code of Virginia Code - Chapter 53. Consumer Data Protection Act*. https://law.lis.virginia.gov/vacodefull/title59.1/chapter53/
20. *Events Calendar - Richmond CultureWorks*. https://calendar.richmondcultureworks.org/
21. *Calendar of Events in Richmond | Things To Do*. https://www.visitrichmondva.com/events
22. *Artsline*. https://www.vpm.org/artsline
23. *Events Calendar - RVAHub*. https://rvahub.com/calendar
24. *World launches tool to verify humans behind AI shopping agents | TechCrunch*. https://techcrunch.com/2024/02/05/meta-cuts-off-third-party-access-to-facebook-groups-leaving-developers-and-customers-in-disarray/
25. *Programs*. https://thevalentine.org/explore/programs/
26. *Black History Museum - Richmond*. https://blackhistorymuseum.org/
27. *black history museum in richmond va: Exploring the Enduring Legacy and Cultural Impact - Wonderful Museums*. https://www.wonderfulmuseums.com/museum/black-history-museum-in-richmond-va/
28. *Formal Agreement (release form) - Oral History Association*. https://oralhistory.org/physical-agreement-release-form/
29. *Administrative Regulations Office of the Mayor Title: MEDIA ...*. https://www.rva.gov/sites/default/files/2019-12/AdminRegs1-07.pdf
30. *Major Decision Affects Law of Scraping and Online Data ...*. https://www.fbm.com/publications/major-decision-affects-law-of-scraping-and-online-data-collection-meta-platforms-v-bright-data/
31. *Facebook Graph API - I suddenly am not getting all events ...*. https://www.reddit.com/r/webdev/comments/16o7yeo/facebook_graph_api_i_suddenly_am_not_getting_all/