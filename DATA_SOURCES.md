# Data Sources — Malaysia Parliament Seats (4 Elections)

This document traces the provenance of every data field in
`parliament_full_data.json`, following the SPR data citation chain to ground
truth wherever possible.

---

## Field-by-Field Provenance

| Field | Source | Tier | How Retrieved |
|-------|--------|------|--------------|
| `code` (P001–P222) | DOSM GeoJSON + Wikipedia cross-check | **Primary** | Directly from DOSM `electoral_0_parlimen.geojson` |
| `name` | DOSM GeoJSON | **Primary** | Directly from DOSM |
| `state` | DOSM GeoJSON | **Primary** | Directly from DOSM |
| `geometry` (boundary) | DOSM GeoJSON | **Primary** | Directly from DOSM |
| `main_town` | Manual assignment by researcher | **Estimated** | Inferred from constituency name + general geography |

### Election Data

#### GE15 (2022)

| Field | Source | Tier | Notes |
|-------|--------|------|-------|
| `pru15.winner` | Wikipedia: "Results of the 2022 Malaysian general election by parliamentary constituency" | **Secondary** | Scraped from rendered Wikitext. |
| `pru15.party` | Same Wikipedia page | **Secondary** | Party+coalition extracted from table rows |
| `pru15.votes` | Same Wikipedia page | **Secondary** | Votes won by the winning candidate |
| `pru15.majority` | Same Wikipedia page | **Secondary** | Winning majority |
| `pru15.electors` | Same Wikipedia page | **Secondary** | Registered electors |
| `pru15.turnout_pct` | Same Wikipedia page | **Secondary** | Voter turnout % |

#### GE14 (2018)

| Field | Source | Tier | Notes |
|-------|--------|------|-------|
| `pru14.winner` | SPR (data.gov.my) — official open data CSV | **Primary** | Downloaded from data.gov.my `ge14_parlimen` dataset |
| `pru14.party` | Wikipedia (cross-referenced) | **Secondary** | **Important:** SPR CSV records ALL PH winners as "PKR" in Peninsular Malaysia, lumping DAP, PKR, PPBM, and AMANAH together. The actual component party is resolved from Wikipedia data. |
| `pru14.votes` | SPR CSV | **Primary** | Winning candidate vote count |
| `pru14.majority` | SPR CSV (computed) | **Primary** | Winner votes − runner-up votes |
| `pru14.total_valid_votes` | SPR CSV (computed) | **Primary** | Sum of all candidate votes |

#### GE13 (2013)

| Field | Source | Tier | Notes |
|-------|--------|------|-------|
| `pru13.winner` | Wikipedia: "Results of the 2013 Malaysian general election by parliamentary constituency" | **Secondary** | Scraped from rendered Wikitext. SPR has not published open data for GE13. |
| `pru13.party` | Same Wikipedia page | **Secondary** | Party+coalition from table rows |
| `pru13.votes` | Same Wikipedia page | **Secondary** | Winning candidate votes |
| `pru13.majority` | Same Wikipedia page | **Secondary** | Winning majority |
| `pru13.electors` | Same Wikipedia page | **Secondary** | Eligible voters count |
| `pru13.turnout_pct` | Same Wikipedia page | **Secondary** | Voter turnout % |

#### GE12 (2008)

| Field | Source | Tier | Notes |
|-------|--------|------|-------|
| `pru12.winner` | Wikipedia: "Results of the 2008 Malaysian general election by parliamentary constituency" | **Secondary** | Scraped from rendered Wikitext. SPR has not published open data for GE12. |
| `pru12.party` | Same Wikipedia page | **Secondary** | Party+coalition from table rows |
| `pru12.votes` | Same Wikipedia page | **Secondary** | Winning candidate votes |
| `pru12.majority` | Same Wikipedia page | **Secondary** | Winning majority |
| `pru12.electors` | Same Wikipedia page | **Secondary** | Eligible voters count |
| `pru12.turnout_pct` | Same Wikipedia page | **Secondary** | Voter turnout % |

---

## 🔍 Wikipedia's Own Sources (Primary Sources Referenced)

We traced the citation chains from the Wikipedia articles we used:

### SPR Official Resources

The Wikipedia *main* election articles (not the constituency-results page) cite these direct SPR sources:

| Source | URL | Data Available |
|--------|-----|---------------|
| SPR Dashboard | `https://dashboard.spr.gov.my/` | Real-time results, electorate data, voter turnout |
| SPR PRU14 Portal | `https://pru14.spr.gov.my/` (archived at `web.archive.org`) | GE14 results by constituency |
| SPR Official Site | `https://www.spr.gov.my/` | Candidate lists, registered parties, election acts |

### Government Gazette

| Source | URL | What |
|--------|-----|------|
| Federal Gazette (P.U. (A) 139) | `http://www.federalgazette.agc.gov.my/outputp/pua_20180613_P.U.%28A%29139.pdf` | Proclamation of election results — **the official gazetted result** |
| Federal Constitution | `http://www.agc.gov.my/images/Personalisation/Buss/pdf/Federal%20Consti%20%28BI%20text%29.pdf` | Constitutional basis for electoral districts |
| Constituency boundary proclamation | `http://www.federalgazette.agc.gov.my/outputp/pub_20200915_PUB463.pdf` | 2020 constituency boundary changes |
| Election Act (Akta 5) | `http://www.spr.gov.my/sites/default/files/perundangan/akta-5-cetakan-semula-2016.pdf` | Election laws and regulations |

---

## 📊 Source Quality Summary

```
Primary (from government)       35% — boundaries, codes, state, GE14 votes
Secondary (from Wikipedia)      55% — GE15, GE13, GE12 winners & votes, GE14 component parties
Estimated (manual assignment)   10% — town mapping
```

## ✅ Best Path to Primary Data

To get **true primary** election data:

1. **GE14 (2018):** Already primary — SPR CSV from https://data.gov.my/data-catalogue/ge14_parlimen
2. **GE12, GE13, GE15:** Visit **https://dashboard.spr.gov.my/** — SPR's official results dashboard (if historical data is available)
3. Check **https://www.spr.gov.my/ms/pilihan-raya/penjalanan-pilihan-raya/calon** — official candidate lists
4. For gazetted (legally binding) results: **Federal Gazette** (`www.federalgazette.agc.gov.my`) — look for P.U. (B) proclamation publications post-election
5. For the **most authoritative** parliamentary constituency map: DOSM GeoJSON (already used here) + SPR's official constituency boundaries at `www.spr.gov.my`

---

*Documented May 2026. Sources verified from Wikipedia citation chains, SPR open data portal, and direct government URLs.*
