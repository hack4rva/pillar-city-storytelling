# Evidence Log — A City That Tells Its Stories

Log all sources here. Every factual claim in your project should trace back to an entry in this log. Add rows as you research. Flip status from Unverified to Verified when you have personally confirmed the source.

---

## Evidence Log

### Confirmed
| ID | Claim | Source | URL | Date accessed | Notes |
|----|-------|--------|-----|---------------|-------|
| | | | | | |

### Likely but unverified
| ID | Claim | Basis for inference | What needs confirmation |
|----|-------|---------------------|------------------------|
| E-001 | Eventbrite API allows public event search by location | Eventbrite developer docs exist publicly | Confirm current rate limits and Richmond event coverage quality |
| E-002 | Style Weekly maintains a searchable events section | Style Weekly is a known Richmond publication with event coverage | Confirm structured data or RSS availability |
| E-003 | The Valentine has an oral history collection | The Valentine is Richmond's history museum | Confirm scope, digital accessibility, and public use terms |
| E-004 | dorichmond.com is an existing Richmond events aggregator | Prior art mentioned in pillar context | Confirm current coverage, maintenance status, and gaps |
| E-005 | Facebook Events API is heavily restricted post-2018 | Widely documented industry change | Confirm current state of access for third-party apps |
| E-006 | Richmond GeoHub has neighborhood boundary data | City of Richmond operates a public GIS portal | Confirm arts/cultural district boundaries exist as a specific layer |
| E-007 | Arts/cultural event data is absent from Richmond open data catalog | Rubric working session notes identified this as a gap | Confirm by searching the open data catalog |

### Missing
| ID | Item | Why it matters | How to resolve |
|----|------|---------------|----------------|
| M-001 | List of Richmond arts organizations with confirmed RSS/iCal feeds | Essential for aggregator data pipeline | Manual research during hackathon — visit each organization's website |
| M-002 | Documentation of how Richmond residents currently discover arts events | Validates the problem statement | User interviews or survey (1-2 hours of quick research) |
| M-003 | Scope and format of oral history collections at The Valentine, Black History Museum, VCU | Needed for story tool and neighborhood history explorer | Contact institutions directly or check their websites |
| M-004 | Whether Richmond has a named arts and cultural district boundary layer in GeoHub | Needed for map-based tools | Check GeoHub directly |
| M-005 | Comfortable storytelling channels for older/non-digital residents | Critical for story collection tool design | Research on accessible civic tech patterns; brief user research if possible |

### Useful datasets
| ID | Dataset | URL | Format | Status |
|----|---------|-----|--------|--------|
| D-001 | Eventbrite Richmond events | https://www.eventbrite.com/platform/api | JSON (REST API) | Unverified |
| D-002 | Richmond GeoHub — neighborhoods | https://rvagis.richmond.gov | GeoJSON | Unverified |
| D-003 | StoryCorps Archive | https://archive.storycorps.org | Web + possible API | Unverified |

### Useful source documents
| ID | Document | URL | Status |
|----|----------|-----|--------|
| S-001 | Richmond Civic Hackathon Pillar 7 rubric | [internal doc] | Confirmed — this repo |
| S-002 | Perplexity Prompting Guide | https://docs.perplexity.ai | Confirmed |

### Prior art
| ID | Tool | City | URL | Relevance |
|----|------|------|-----|-----------|
| P-001 | dorichmond.com | Richmond VA | https://dorichmond.com | Direct prior art — existing Richmond aggregator |
| P-002 | Historypin | International | https://historypin.org | Model for neighborhood history explorer |
| P-003 | StoryCorps | National | https://storycorps.org | Model for oral history collection with consent |

### Risks
| ID | Risk | Severity | Mitigation |
|----|------|----------|------------|
| R-001 | Facebook Events API inaccessibility | High | Do not plan MVP around Facebook data |
| R-002 | Story tool without consent mechanism | High | Require consent screen before any story submission |
| R-003 | Claiming to represent "all" Richmond voices | High | Explicit disclaimer on any insight or aggregate view |
| R-004 | Manual curation decay | Medium | Design for automated feeds; no human curation dependencies |
| R-005 | Copyright of arts event content | Medium | Always link to original source; do not copy content wholesale |
