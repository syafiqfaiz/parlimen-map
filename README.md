# 🇲🇾 Malaysia Parliamentary Seats Map

Interactive map of all **222 Malaysian parliamentary constituencies** (P.001–P.222) with **4 election cycles**: GE12 (2008), GE13 (2013), GE14 (2018), and GE15 (2022).

**Live map:** https://syafiqfaiz.github.io/parlimen-map/index.html

---

## 📂 Data Files

| File | Size | Contents |
|------|------|----------|
| `index.html` | 1.4 MB | Self-contained Leaflet.js map (bundled GeoJSON + data) |
| `parliament_full_data.json` | 422 KB | Full dataset for all 222 seats × 4 elections |
| `boundaries.geojson` | 1.4 MB | GeoJSON with enriched election data properties |

## 📊 Dataset Schema (`parliament_full_data.json`)

Each entry contains fields for all 4 elections:

| Field | Description |
|-------|-------------|
| `code` | Constituency code (P001–P222) |
| `name` | Constituency name |
| `state` | State or Federal Territory |
| `main_town` | Main town/locality in the constituency |
| `city_region` | Broader city or region |
| `pru12` | GE12 (2008) — winner, party, votes, majority, electors, turnout, opponents |
| `pru13` | GE13 (2013) — winner, party, votes, majority, electors, turnout, opponents |
| `pru14` | GE14 (2018) — winner, party, votes, majority, opponents |
| `pru15` | GE15 (2022) — winner, party, votes, majority, electors, turnout, opponents |

Each election entry also includes a `source` field indicating data provenance (SPR primary vs Wikipedia secondary).

## 🗳️ Party Color Legend (Map)

| Color | Coalition |
|-------|-----------|
| 🔴 Red | PH (Pakatan Harapan) / PR (Pakatan Rakyat) — DAP, PKR, AMANAH |
| 🟢 Green | PN (Perikatan Nasional) / GS (Gagasan Sejahtera) / PR-PAS — PAS, BERSATU, GERAKAN |
| 🔵 Blue | BN (Barisan Nasional) — UMNO, MCA, MIC, PBB, SUPP, PRS, etc. |
| 🫐 Teal | GPS (Gabungan Parti Sarawak) |
| 🟤 Dark Green | GRS (Gabungan Rakyat Sabah) |
| 🟠 Orange | WARISAN |
| 🟣 Purple | MUDA, PBM, PEJUANG |

📄 See **[`DATA_SOURCES.md`](./DATA_SOURCES.md)** for complete field-by-field provenance, SPR source URLs, and Federal Gazette references.

## 🗺️ Source Attribution & Data Quality

### ✅ Primary Sources

| Data | Source | Tier |
|------|--------|------|
| **Constituency boundaries** (GeoJSON) | DOSM Malaysia (data.gov.my) — official open government geodata | **Primary** |
| **Constituency codes & names** | DOSM GeoJSON + Wikipedia cross-check | **Primary** |
| **State assignment** | DOSM GeoJSON | **Primary** |
| **GE14 (2018)** — winner name, votes, opponents, majority | SPR (data.gov.my) — official open data CSV | **Primary** |

### ⚠️ Secondary Sources

| Data | Source | Notes |
|------|--------|-------|
| **GE14 (2018) — component party** | Wikipedia (cross-referenced) | SPR CSV records all PH winners as "PKR" in Peninsular Malaysia. Wikipedia data used to resolve actual component parties (DAP, PKR, PPBM, AMANAH). |
| **GE12 (2008) & GE13 (2013)** — winners, parties, votes, majority, turnout | Wikipedia — "Results of the __ Malaysian general election by parliamentary constituency" | SPR has not published open data for these elections. Wikipedia is the best available secondary source. |
| **GE15 (2022)** — MP names, party, registered electors, votes, majority, turnout | Wikipedia — "Results of the 2022 Malaysian general election by parliamentary constituency" | SPR has not released GE15 open data as of May 2026. |

### 🟡 Estimated Data

| Data | Source | Notes |
|------|--------|-------|
| **Main town / locality** | Manually assigned based on constituency names and general geography | **Not authoritative.** For precise coverage areas, refer to DOSM boundary maps or the SPR official constituency gazette. |

### 🔗 Links

- **DOSM GeoJSON source:** https://github.com/dosm-malaysia/data-open/tree/main/datasets/geodata
- **SPR GE14 open data:** https://data.gov.my/data-catalogue/ge14_parlimen
- **GE15 Wikipedia:** https://en.wikipedia.org/wiki/Results_of_the_2022_Malaysian_general_election_by_parliamentary_constituency
- **GE14 Wikipedia:** https://en.wikipedia.org/wiki/Results_of_the_2018_Malaysian_general_election_by_parliamentary_constituency
- **GE13 Wikipedia:** https://en.wikipedia.org/wiki/Results_of_the_2013_Malaysian_general_election_by_parliamentary_constituency
- **GE12 Wikipedia:** https://en.wikipedia.org/wiki/Results_of_the_2008_Malaysian_general_election_by_parliamentary_constituency
- **SPR (Suruhanjaya Pilihan Raya):** https://www.spr.gov.my (primary source for all election data — consult directly for official use)

> **⚠️ Disclaimer:** This data is compiled for personal reference / research. The election results are once-removed from SPR's official count for all elections except GE14 (where SPR open data was used directly). Do not use for legal or official purposes without verifying against SPR's gazetted results.

## 🛠️ How to Use

1. Open `index.html` in any browser — **no build step required**
2. Use dropdown to toggle between GE12 (2008), GE13 (2013), GE14 (2018), and GE15 (2022)
3. Hover over any seat to highlight; click for full details including all 4 election winners
4. Source badges (PRIMARY / SECONDARY) shown per election in each popup
5. Legend at bottom-right shows party/coalition colors for the selected year

---

_Data compiled May 2026. For personal reference / research purposes._
