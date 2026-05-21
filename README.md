# 🇲🇾 Malaysia Parliamentary Seats Map

Interactive map of all **222 Malaysian parliamentary constituencies** (P.001–P.222) with GE15 (2022) and GE14 (2018) election data.

**Live map:** https://syafiqfaiz.github.io/parlimen-map/index.html

---

## 📂 Data Files

| File | Size | Contents |
|------|------|----------|
| `index.html` | 1.2 MB | Self-contained Leaflet.js map (bundled GeoJSON + data) |
| `parliament_full_data.json` | 137 KB | Full dataset for all 222 seats |

## 📊 Dataset Schema (`parliament_full_data.json`)

Each entry contains:

| Field | Description |
|-------|-------------|
| `code` | Constituency code (P001–P222) |
| `name` | Constituency name |
| `state` | State or Federal Territory |
| `main_town` | Main town/locality in the constituency |
| `city_region` | Broader city or region |
| `registered_electors` | Number of registered voters |
| `majority` | Winning majority votes |
| `turnout` | Voter turnout percentage |
| `mp_2022_name` | Current MP (GE15 2022 winner) |
| `mp_2022_party` | Current MP's party/coalition |
| `mp_2022_opponents` | Opposing candidates in GE15 |
| `mp_2018_name` | Previous MP (GE14 2018 winner) |
| `mp_2018_party` | Previous MP's party/coalition |

## 🗳️ Party Color Legend (Map)

| Color | Coalition |
|-------|-----------|
| 🔴 Red | PH (Pakatan Harapan) — DAP, PKR, AMANAH, UPKO |
| 🟢 Green | PN (Perikatan Nasional) — PAS, BERSATU, GERAKAN |
| 🔵 Blue | BN (Barisan Nasional) — UMNO, MCA, MIC |
| 🫐 Teal | GPS (Gabungan Parti Sarawak) |
| 🟤 Dark Green | GRS (Gabungan Rakyat Sabah) |
| 🟠 Orange | WARISAN |
| 🟣 Purple | MUDA, PBM |

## 🗺️ Source Attribution & Data Quality

### ✅ Primary Sources

| Data | Source | Tier |
|------|--------|------|
| **Constituency boundaries** (GeoJSON) | DOSM Malaysia (data.gov.my) — official open government geodata | **Primary** |
| **Constituency codes & names** | DOSM GeoJSON + Wikipedia cross-check | **Primary** |
| **State assignment** | DOSM GeoJSON | **Primary** |

### ⚠️ Secondary Sources

| Data | Source | Notes |
|------|--------|-------|
| **GE15 (2022)** — MP names, party, registered electors, votes, majority, turnout | Wikipedia — "Results of the 2022 Malaysian general election by parliamentary constituency" | Wikipedia sources SPR/EC data, but I scraped the rendered tables, not the raw SPR dataset. Minor transcription errors possible. |
| **GE14 (2018)** — MP names, party only | Pre-existing data file (origin unclear — likely derived from Wikipedia or SPR publications) | No vote/electors/majority figures for GE14 in this dataset. |

### 🟡 Estimated Data

| Data | Source | Notes |
|------|--------|-------|
| **Main town / locality** | Manually assigned based on constituency names and general geography | **Not authoritative.** E.g., "P.220 Baram" mapped to "Marudi" — these are approximate. For precise coverage areas, refer to DOSM boundary maps or the SPR official constituency gazette. |

### 🔗 Links

- **DOSM GeoJSON source:** https://github.com/dosm-malaysia/data-open/tree/main/datasets/geodata
- **GE15 Wikipedia:** https://en.wikipedia.org/wiki/Results_of_the_2022_Malaysian_general_election_by_parliamentary_constituency
- **SPR (Suruhanjaya Pilihan Raya):** https://www.spr.gov.my (primary source for all election data — consult directly for official use)

> **⚠️ Disclaimer:** This data is compiled for personal reference / research. The election results are once-removed from SPR's official count. Do not use for legal or official purposes without verifying against SPR's gazetted results.

## 🛠️ How to Use

1. Open `index.html` in any browser — **no build step required**
2. Use dropdown to toggle between GE15 (2022) and GE14 (2018)
3. Hover over any seat to highlight; click for full details
4. Legend at bottom-right shows party/coalition colors

---

_Data compiled May 2026. For personal reference / research purposes._
