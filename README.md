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

## 🗺️ Source

- **Boundary data:** Department of Statistics Malaysia (DOSM) — `electoral_0_parlimen.geojson`
- **Election results:** Wikipedia (GE15, GE14 tables)
- **Map renderer:** Leaflet.js with CARTO basemaps

## 🛠️ How to Use

1. Open `index.html` in any browser — **no build step required**
2. Use dropdown to toggle between GE15 (2022) and GE14 (2018)
3. Hover over any seat to highlight; click for full details
4. Legend at bottom-right shows party/coalition colors

---

_Data compiled May 2026. For personal reference / research purposes._
