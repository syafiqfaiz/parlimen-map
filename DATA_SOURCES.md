# Data Sources — Malaysia Parliament Seats

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
| `mp_2022_name` | Wikipedia: "Results of the 2022 Malaysian general election by parliamentary constituency" | **Secondary** | Scraped from rendered Wikitext. Underlying data likely compiled from news reports; this specific page does **not** directly cite SPR |
| `mp_2022_party` | Same Wikipedia page | **Secondary** | Party+coalition extracted from table rows |
| `registered_electors` | Same Wikipedia page | **Secondary** | "Registered electors" column from tables |
| `votes` | Same Wikipedia page | **Secondary** | Votes won by the winning candidate |
| `majority` | Same Wikipedia page | **Secondary** | Winning majority |
| `turnout` | Same Wikipedia page | **Secondary** | Voter turnout % |

#### GE14 (2018)

| Field | Source | Tier | Notes |
|-------|--------|------|-------|
| `mp_2018_name` | Pre-existing data file (`ge14_results.json`, provenance unclear) | **Secondary** | Likely derived from Wikipedia or SPR publications; no vote figures available |
| `mp_2018_party` | Same file | **Secondary** | |

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
| SPR Registered Party Symbols | `https://www.spr.gov.my/sites/default/files/SIMBOL%20PARTI%20YANG%20BERDAFTAR%20DENGAN%20SPR%20SEHINGGA%2017%20OKTOBER%202022.pdf` | PDF of all registered party logos |
| SPR Voter Registration | `https://www.spr.gov.my/sites/default/files/KM%20BIL%2019%20PENDAFTARAN%20PENGUNDI%2018THN.pdf` | Voter registration data |
| SPR Electoral Roll | `https://www.spr.gov.my/sites/default/files/Senarai%20BPR%2010.09.2019.pdf` | Electoral roll listing |
| SPR Deposit Pricing (PRU14) | `http://www.spr.gov.my/sites/default/files/HargaDPIST42017_PRU14.pdf` | Candidate deposit amounts by constituency |

### Government Gazette

| Source | URL | What |
|--------|-----|------|
| Federal Gazette (P.U. (A) 139) | `http://www.federalgazette.agc.gov.my/outputp/pua_20180613_P.U.%28A%29139.pdf` | Proclamation of election results — **this is the official gazetted result** |
| Federal Constitution | `http://www.agc.gov.my/images/Personalisation/Buss/pdf/Federal%20Consti%20%28BI%20text%29.pdf` | Constitutional basis for electoral districts |
| Constituency boundary proclamation | `http://www.federalgazette.agc.gov.my/outputp/pub_20200915_PUB463.pdf` | 2020 constituency boundary changes |
| Election Act (Akta 5) | `http://www.spr.gov.my/sites/default/files/perundangan/akta-5-cetakan-semula-2016.pdf` | Election laws and regulations |

### News Media (Wikipedia's Secondary Sources for This Page)

The "Results by parliamentary constituency" page directly cites:
- Free Malaysia Today
- New Straits Times
- The Star

---

## 📊 Source Quality Summary

```
Primary (from government)       30% — boundaries, codes, state
Secondary (from Wikipedia)      40% — GE15 winner, party, votes, electors
Estimated (manual assignment)   10% — town mapping
Unknown provenance              20% — GE14 winner/party (from pre-existing file)
```

## ✅ Best Path to Primary Data

To get **true primary** election data:

1. Visit **https://dashboard.spr.gov.my/** — SPR's official results dashboard (real-time + historical)
2. Visit **https://pru14.spr.gov.my/** — GE14 official results (via archive)
3. Check **https://www.spr.gov.my/ms/pilihan-raya/penjalanan-pilihan-raya/calon** — official candidate lists
4. For gazetted (legally binding) results: **Federal Gazette** (`www.federalgazette.agc.gov.my`) — look for P.U. (B) proclamation publications post-election
5. For the **most authoritative** parliamentary constituency map: DOSM GeoJSON (already used here) + SPR's official constituency boundaries at `www.spr.gov.my`

---

*Documented May 2026. Sources verified from Wikipedia citation chains and direct government URLs.*
