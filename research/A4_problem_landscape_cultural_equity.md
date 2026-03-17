# From Broad Street to the Bottom: Fixing Richmond's Cultural Visibility Gap

## Executive Summary

Richmond’s cultural visibility infrastructure is currently optimized for well-resourced, downtown-centric institutions, inadvertently silencing the narratives of historically marginalized neighborhoods. Mainstream discovery channels heavily favor the Broad Street Arts District, while systemic barriers—ranging from digital gatekeeping to historical displacement—obscure the cultural output of the East End, Jackson Ward, and Shockoe Bottom. 

This report investigates the dominant narrative problem in Richmond's civic storytelling tools. Key findings reveal that "self-submission" pipelines quietly gatekeep visibility, as 9.7% of Richmond residents lack internet access and face significant trust barriers. Furthermore, historical patterns of erasure, such as the paving of the Shockoe Bottom African Burial Ground and the intentional displacement of Black residents in Church Hill, continue to shape whose stories are told today. To prevent civic tech tools from accelerating gentrification and narrative flattening, developers must implement equity-by-design principles, including low-tech submission on-ramps, algorithmic equity weighting, and community-governed editorial boards.

## Problem Definition — Richmond's current discovery pipes over-index on downtown institutions

The city’s dominant arts visibility flows through a Broad Street–centered infrastructure that inherently favors well-resourced organizations with dedicated marketing capacity. 

### Downtown concentration drives discovery
Mainstream cultural promotion in Richmond is heavily concentrated in the downtown core. The region boasts about 70 galleries, with a massive concentration participating in First Fridays, an event specifically centered "on and around Broad Street in Richmond’s Arts District" [1]. This geographic clustering means that suburban and outer-neighborhood cultural events must compete against a dense, highly visible downtown gravity center.

### Incentive zoning nudges attention and investment
The City of Richmond has formally established Downtown Richmond’s Arts District as an "Arts and Cultural District Incentive Zone" [2] [3]. Properties within this overlay district receive special incentive programs, such as facade improvement grants [3]. This policy choice directs both municipal investment and public attention toward a specific corridor, amplifying the visibility of the businesses and galleries located there while leaving other cultural hubs without similar institutional backing.

### Submission stack is centralized and digitally exclusive
The pipelines feeding Richmond's major cultural calendars require digital fluency and proactive submission. VPM's Artsline, a major curator of local arts and culture events, relies on users submitting their events through the *Style Weekly* event submission page [4] [5]. Similarly, Richmond CultureWorks requires users to navigate to their website and use a digital event submission form [6]. These "self-submission" models act as quiet gatekeepers, filtering out grassroots organizers, elders, and low-income residents who lack the time, digital assets, or internet access to navigate these platforms.

## Who's Seen vs. Who's Missing — A Richmond-specific visibility gap map

To understand the cultural visibility gap, we must map current presence in mainstream channels against historical and ongoing systemic barriers. The following table categorizes the visibility status of key Richmond neighborhoods and communities.

| Neighborhood / Community | Current Presence in Mainstream Calendars | Historic Erasure / Gentrification Status | Barriers Observed | Label |
| :--- | :--- | :--- | :--- | :--- |
| **Arts District / Broad St.** | High presence; heavily promoted | Established as an incentive zone; revitalization in the 2000s [3] | Low digital barriers; high institutional support | Verified |
| **East End South** | High media/amenity buzz | Rapid gentrification; white population increased 44% (2010-2016) [7] | Rising costs; cultural displacement of legacy residents | Verified |
| **East End North** | Low presence | Long considered a food desert until 2019; double the unemployment of East End South [7] | Affordability stress; digital divide; lack of commercial anchors | Verified |
| **Jackson Ward** | Heritage sites present, but shifting demographics | Once the "Harlem of the South," now roughly 23% African-American [8] | Narrative flattening; risk of heritage commodification | Verified |
| **Brookland Park Blvd** | Black businesses anchor culture [8] | Housing market undergoing significant change [8] | Potential underrepresentation in regional digital calendars | Inference |
| **Fulton (Greater Fulton)** | Unknown | Massive destruction and urban renewal history [9] | Requires field audit to determine current digital visibility | Unknown |
| **Gilpin Court / Public Housing** | Unknown | Concentrated poverty; created via low-income housing policies [10] | Digital access; privacy/safety concerns; stigma | Unknown |

**Key Takeaways:** East End North, legacy Jackson Ward residents, and small BIPOC-led organizations are structurally underrepresented. Meanwhile, areas experiencing rapid gentrification (East End South) see their visibility artificially inflated through amenity marketing, which often excludes the narratives of displaced legacy residents.

## Historical Erasure Case Files — How policy reshaped who tells Richmond's story

Urban renewal, concentrated public housing, and targeted "restoration" have rewired Richmond's neighborhood demographics and narratives. Understanding this history is critical to building tools that do not repeat past harms.

### Church Hill: "Restoration" as Renter Removal
In 1956, the Historic Richmond Foundation formed to "restore" the neighborhood around St. John's Church, which intentionally meant pushing out African American renters to make room for white renters [9]. This sparked decades of gentrification. By 1981, the assessed value of the restored area had increased 673%, compared to a 282% increase citywide [9]. Between 2000 and 2015, African American households in Church Hill declined by 20%, and Black homeowners dropped by 23%, while white homeowners increased by 159% [8]. Home values jumped 30% from 2010 to 2014 alone [8]. This demographic flip drastically shrank the number of local Black storytellers with platform access, risking total narrative replacement.

### Jackson Ward: The Commodification of Heritage
Jackson Ward, historically celebrated as the "Harlem of the South," has transformed into a majority-white community where African-Americans now comprise only about 23% of the population [8]. While trailblazers like Maggie Lena Walker and Oliver Hill remain historical staples [8], there is a profound risk that their legacies are framed merely as "heritage backdrops" for new, wealthier audiences. Without contemporary Black stewardship, the neighborhood's cultural narrative is flattened.

### Shockoe Bottom: Paving Over Sacred Ground
The African Burial Ground in Shockoe Bottom, labeled "Burial Ground for Negroes" on an 1809 city map, was active from 1799 to 1816 [11] [12]. Following its abandonment, the site was eventually demolished for Interstate 95 in the late 1950s and paved over in the 1970s to serve as a parking lot for VCU [11] [12]. It took a massive community struggle, including the formation of the Sacred Ground Historical Reclamation Project in 2004, to reclaim the site [11]. The asphalt was finally removed in 2011 [11]. This demonstrates how physical erasure becomes narrative erasure until communities intervene.

### East End: Concentrated Poverty and Political Dilution
The city intentionally created a concentrated pocket of poverty in the East End, which houses 60% of Richmond's public housing units (including Creighton, Mosby, Fairfield, and Whitcomb Courts) [9] [7] [10]. Because these units fall within a single district, a disproportionate percentage of the city's poor share only one city council member and one school board representative, severely limiting their political power and influence over cultural policy [7]. 

## Digital Gatekeeping and Trust — Why access ≠ adoption

The city's push for digital equity meets a profound trust and literacy gap that directly maps onto cultural exclusion. Civic tech tools that assume universal digital fluency will inherently exclude marginalized voices.

### The Adoption and Trust Gap
Approximately 9.7% of Richmond residents do not have an internet subscription [13]. While Comcast asserts that there is 100% access to broadband services throughout the city, they note that the actual issue is a lack of adoption [13]. People are either unaware of discounted service programs or simply do not trust them [13]. 

### Civic Tech Defaults Filter Out Grassroots Groups
Because mainstream platforms like CultureWorks and Artsline rely on digital web forms and polished assets [4] [6], groups without high-speed internet, digital marketing skills, or English proficiency are filtered out. The actionable fix requires human intermediaries, low-tech submission options (like SMS or paper), and offline distribution channels.

## Design Patterns That Amplify Dominant Narratives — What to avoid

When building civic storytelling tools, certain default design choices inevitably preference resourced actors and accelerate displacement.

### Failure Patterns in Discovery Tools
Algorithms that rank events by "most popular near you" or require Instagram-grade visual assets inherently favor downtown institutions and well-funded organizations. Long lead times for event submissions also penalize grassroots organizers who operate on shorter, more flexible timelines. These patterns are currently observable in the pipelines of Venture Richmond, Artsline, and CultureWorks.

### The Danger of Amenity Marketing
Visibility can accelerate displacement if framed as "discovering the next hot neighborhood." In the East End, a racialized wave of gentrification is moving from south to north [7]. East End South has seen the emergence of a "bakery district" anchored by Sub Rosa, WPA Bakery, and Proper Pie, alongside restaurants like Dutch & Company [7]. This amenity branding coincides with higher incomes and rising housing costs, masking the replacement of low-to-moderate-income Black residents with wealthier white residents [7]. Tools that blindly promote these amenity clusters without context contribute to this harm.

## Equity-by-Design Principles — Build visibility with, not for, communities

To make story collection and arts discovery tools more equitable, developers must embed safeguards directly into the product architecture.

* **Community Governance:** Establish paid stewardship seats by ZIP code to ensure curation is driven by residents, not just algorithms.
* **Low-Friction Submissions:** Support multilingual, low-bandwidth, and offline/phone intake methods to bypass the digital divide.
* **Contextualization:** Provide automated historical context for historically Black neighborhoods and sacred sites to prevent narrative flattening.
* **Algorithmic Equity:** Implement equity weighting and share-of-voice caps to prevent downtown events from monopolizing feeds.
* **Safety and Consent:** Ensure trauma-informed storytelling and strict consent workflows, particularly for vulnerable populations in public housing.
* **Anti-Displacement Framing:** Link cultural discovery with community benefits, such as tenant rights information and land-trust resources.

## Feature Blueprint — Concrete capabilities mapped to barriers

Specific features can directly counter known gatekeeping mechanisms. The following blueprint maps barriers to actionable product features.

| Barrier | Feature Solution | How It Works | Pilot Partner | Success Metric |
| :--- | :--- | :--- | :--- | :--- |
| **No internet / Lack of trust** | SMS/voice hotline & paper intake | Deploy paid "story sherpas" to collect paper intake at libraries/churches; allow SMS event submission. | Richmond Public Libraries, RPS, local churches | 40% of posts originate from low-connectivity ZIP codes |
| **Asset-polish bias** | Low-asset submission flows | Allow no-photo submissions; integrate AI-assisted copy clean-up and auto-translation. | CultureWorks, RVA nonprofits | 50% increase in submissions from small-budget organizations |
| **Downtown overexposure** | ZIP-weighted feeds | Algorithmically cap Broad Street dominance; rotate neighborhood spotlight slots weekly. | Venture Richmond, VPM | Share-of-voice parity achieved across target ZIP codes |
| **Sacred site risk** | Sensitive-geo tagging | Suppress promotional event marketing at burial grounds; require descendant review workflows. | Sacred Ground Historical Reclamation Project | 0 unvetted listings published at protected historical sites |
| **Gentrification acceleration** | Impact prompts & legacy badges | Cap repeated promotion of amenity clusters; highlight legacy Black-owned businesses. | Jackson Ward & Brookland Park orgs | Balanced coverage index between new amenities and legacy spaces |

## Partnerships and Power-Sharing — Who must be in the room

Legitimacy and reach depend entirely on resident editors and trusted intermediaries. A tool built in isolation will fail to gain adoption in the communities it aims to serve.

### Core Partners
Development must involve the Sacred Ground Historical Reclamation Project, Jackson Ward community organizations, East End tenant groups, Brookland Park business associations, Richmond Public Schools (RPS), and local churches. 

### Governance Structure
The platform should establish a compensated resident editorial board. Curation duties should rotate among community stewards monthly, and the platform must maintain public decision logs to ensure transparency in how stories and events are amplified.

## Risk Register for Hackathon Tools — How good intent goes wrong

Speed without safeguards can widen equity gaps or cause active harm to vulnerable communities. Hackathon teams must be aware of the following Richmond-specific risks:

* **Algorithmic Snowballing:** Popularity metrics will inevitably snowball downtown content, reinforcing the Arts District's dominance at the expense of the East End and Northside.
* **Accelerating Displacement:** Uncritical amenity marketing (e.g., promoting the East End South "bakery district") signals gentrification and increases pressure on legacy residents.
* **Sacred Site Harm:** Promoting inappropriate events on reclaimed land, such as the Shockoe Bottom African Burial Ground, repeats historical disrespect.
* **Extractive Storytelling:** Pressuring elders in gentrifying areas like Church Hill for their stories without offering compensation or platform control is extractive.
* **Privacy Violations:** Exposing the locations or routines of vulnerable residents, particularly in public housing contexts like Mosby or Creighton Court, poses severe safety risks.

**Mitigations:** Implement strict equity weighting, mandate content review with descendant communities, enforce consent workflows, and red-team all marketing copy for "up-and-coming" neighborhood signals.

## Policy and Infrastructure Alignment — Ride the broadband momentum

Product rollout should be paired with digital inclusion initiatives to convert internet access into actual adoption. 

### Leveraging City Initiatives
In 2024, the Richmond City Council adopted a resolution declaring high-speed internet a public necessity [14] [13]. Furthermore, the city's Strategic Plan for Equitable Economic Development (SPEED) includes the Richmond Public Telecommunications Infrastructure Initiative (RPTI) to ensure universal broadband [15]. Civic tech tools should align with these efforts by negotiating zero-rated data for the app, hosting device drives, and deploying offline kiosks at recreation centers.

### Addressing the Trust Deficit
To overcome the trust barriers cited by providers [13], training must be co-branded with trusted community pillars like libraries and churches. Providing stipends for community digital navigators will ensure that adoption efforts are led by familiar faces.

## Metrics and Accountability — Define success beyond clicks

Success must be measured by how effectively the tool reallocates visibility, not just by total user engagement. 

* **Geographic Equity:** Increase the share of surfaced events from underrepresented ZIP codes (e.g., 23223, 23222) by 20 percentage points within 6 months.
* **Representation:** Ensure that 40%+ of posts originate from BIPOC-led organizations and legacy businesses.
* **Accessibility:** Track language diversity counts and the share of low-bandwidth/offline submissions.
* **Compliance:** Achieve a 100% review rate for content related to tagged sacred sites.
* **Trust:** Conduct a quarterly pulse survey to measure resident satisfaction and trust, reviewed openly with the resident board.

## Appendix — Evidence Pack and Open Questions

To maintain a living evidence base, the following table tracks the status of key claims and outlines a 60-day field research plan to close remaining knowledge gaps.

| Claim / Data Point | Source | Status | Next Validation Step |
| :--- | :--- | :--- | :--- |
| 9.7% of Richmond residents lack internet | ACS 2023 / VA Mercury [13] | Verified | Monitor annual ACS updates |
| 60% of public housing is in the East End | NCRC [7] | Verified | Cross-reference with RRHA redevelopment plans |
| Church Hill assessed values rose 673% (1956-1981) | VCU ETD [9] | Verified | Analyze current property tax relief utilization |
| Jackson Ward is now ~23% African American | RVA Mag [8] | Verified | Engage Jackson Ward legacy organizations |
| Brookland Park Blvd is underrepresented in regional calendars | RVA Mag [8] | Inference | Conduct a 30-day scrape of Artsline/CultureWorks for 23222 events |
| Fulton (Greater Fulton) visibility in mainstream channels | N/A | Unknown | Add to discovery sprint; interview Fulton legacy residents |
| Gilpin Court community event visibility | N/A | Unknown | Add to discovery sprint; partner with tenant councils |

## References

1. *The Richmond Gallery Scene | Local Art, First Fridays & Culture*. https://www.visitrichmondva.com/things-to-do/arts-and-culture/galleries-and-first-fridays
2. *Arts and Cultural District Incentive Zones | Richmond GeoHub*. https://richmond-geo-hub-cor.hub.arcgis.com/datasets/cor::arts-and-cultural-district-incentive-zones/about
3. *Richmond Arts District | Venture Richmond*. https://venturerichmond.com/live-downtown/historic-neighborhoods/arts-district/
4. *Artsline*. https://www.vpm.org/artsline
5. *Artsline*. https://www.vpm.org/tags/artsline
6. *Events Calendar - Richmond CultureWorks*. https://calendar.richmondcultureworks.org/
7. *In Richmond, Virginia, gentrification is colonization » NCRC*. https://ncrc.org/gentrification-richmondva/
8. *There Goes The Neighborhood: Combating Displacement in Richmond's Historically Black Neighborhoods - RVA Mag*. https://rvamag.com/politics/richmond-politics/there-goes-the-neighborhood-combating-displacement-in-richmonds-historically-black-neighborhoods.html
9. *A Case Study of Gentrification in Church Hill*. https://scholarscompass.vcu.edu/cgi/viewcontent.cgi?article=5150&context=etd
10. *A Policy Guide for Richmond Connects*. https://rva.gov/sites/default/files/2022-02/PTE%20FINAL%202.18.pdf
11. *Shockoe Bottom African Burial Ground*. https://www.sacredgroundproject.net/p/richmonds-african-burial-ground.html
12. *SHOCKOE BOTTOM MEMORIALIZATION*. https://preservationvirginia.org/wp-content/uploads/2019/11/Shockoe-Bottom-Memorialization-Community-and-Economic-Impacts.pdf
13. *Richmond City Council wants to increase internet speeds, close ‘digital divide’ • Virginia Mercury*. https://virginiamercury.com/2024/09/17/richmond-city-council-wants-to-increase-internet-speeds-close-digital-divide/
14. *
	City of Richmond - File #: RES. 2024-R026
*. https://richmondva.legistar.com/LegislationDetail.aspx?ID=6791846&GUID=7A3D4E77-4A39-4BAE-AB85-985C3B881BA5
15. *strategic plan for equitable economic development (speed)*. https://www.rva.gov/sites/default/files/2022-05/Richmond%20SPEED%20-%20051822%20-%20Clean%20Final%20For%20Introduction.pdf