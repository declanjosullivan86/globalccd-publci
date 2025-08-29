# Datasets for EMF/EMI Mapping in Residential Settings

Here’s a focused, analyst-grade report on **Datasets for EMF/EMI mapping in residential settings**, moving top-down from the big picture to tactical details and sources.

## 1) Executive Summary & Domain Definition

**What this is:** Datasets and methods used to **map electromagnetic fields (EMF)** and **electromagnetic interference (EMI)** inside and around homes. The practical goal is to quantify exposures (ELF: 50/60 Hz power frequencies; RF: \~100 kHz–300 GHz) and locate interference sources that affect health compliance, device performance, and spectrum hygiene.

**Why it matters:**

* **Health & compliance:** Validate that ambient fields are within public exposure limits (ICNIRP/IEEE) and document local “hot spots.” ([ICNIRP][1], [IEEE Standards Association][2])
* **Performance:** Diagnose home-network issues (Wi-Fi/BT/cellular), smart-home device dropouts, or audio/AV noise from conducted/radiated EMI.
* **Planning:** Guide placement of routers, femtocells, baby monitors, induction hobs, EV chargers, and home offices; assess proximity to external transmitters and power lines.

**Scope:**

* **Indoor** measures (in-home surveys, appliance/device emissions, wiring).
* **Outdoor** context (nearby transmitters, base stations, power distribution).
* **Crowd/open data** for RF sources (cell/Wi-Fi databases), **regulatory** measurement reports, and **standards-based** measurement protocols (IEC/IEEE). ([ANSI Webstore][3], [ITU][4])

---

## 2) Hierarchical Taxonomy & Core Concepts

**A. Frequency domains**

* **ELF (0–300 Hz)**: Mainly 50/60 Hz and harmonics from mains supply, transformers, house wiring; mapped via **magnetic flux density (µT)** and **electric field (V/m)**.
* **IF (300 Hz–100 kHz)**: Induction cookers, PLC (power-line communication), some switching supplies.
* **RF (100 kHz–300 GHz)**: Broadcast, cellular (2G–5G), Wi-Fi/BT, DECT, smart meters; mapped by **E-field (V/m)**, **power density (W/m²)**, or **band-selective levels**. (ICNIRP RF scope: 100 kHz–300 GHz; IEEE covers 0 Hz–300 GHz.) ([ICNIRP][1], [IEEE Standards Association][2])

**B. Mapping targets**

* **Ambient fields** (background in rooms).
* **Source-proximal** (near routers, microwaves, induction hobs, EVSE).
* **Propagation context** (building materials, layout, reflections; 3GPP 38.901 for indoor/penetration modeling).

**C. Data classes**

1. **Regulatory/compliance datasets** (campaign reports, site inventories). ([ComReg][5])
2. **Infrastructure/location datasets** (cell sites, Wi-Fi APs, power lines). ([opencellid.org][6], [wigle.net][7])
3. **Crowdsensed RF exposure proxies** (cell/Wi-Fi signal presence/strength). ([opencellid.org][8])
4. **In-home measurement datasets** (spot/band-selective logs, walk-through surveys).
5. **EMI/Compliance test reports** (device emissions from certification filings).
6. **Reference models/standards** (measurement methods, uncertainty). ([ANSI Webstore][3], [ITU][4])

**D. Core concepts**

* **Exposure limit** (public vs. occupational) and **reference levels** (V/m, A/m, W/m²). ([ICNIRP][1])
* **Measurement types:** broadband (total), frequency-selective (band/channel), time-resolved (duty-cycle).
* **Uncertainty chain:** probe factors, positioning, body perturbation, reflections, traffic variability (IEC 62232/related). ([ANSI Webstore][3])

---

## 3) Foundational Theories & Main Arguments

* **Exposure guidelines:**

  * **ICNIRP (2020 RF; 2010 LF)** set public reference levels by frequency; widely adopted by regulators. ([ICNIRP][1])
  * **IEEE C95.1-2019** harmonizes safety levels across 0 Hz–300 GHz. ([IEEE Standards Association][2])
* **Measurement/assessment frameworks:**

  * **IEC 62232** (and case-study TRs) for **evaluating RF field strength/SAR from base stations**, including survey design and uncertainty. ([ANSI Webstore][3])
  * **ITU/IEC TC106** overview on measurement & calculation across 0 Hz–300 GHz. ([ITU][4])
* **Indoor propagation:** **3GPP TR 38.901** supplies **indoor hotspot/office/home** path-loss and penetration models used to predict in-home RF distributions when measurements are sparse.
* **Epidemiology backdrop:**

  * **IARC** classifies **RF EMF** (2011) and **ELF magnetic fields** (2002) as **Group 2B (possibly carcinogenic)**; regulatory limits aim to avoid established acute effects (e.g., tissue heating, nerve stimulation), with epidemiology monitored for long-term risks. ([IARC][9], [IARC Publications][10])

**Implication:** Residential mapping typically demonstrates compliance with reference levels; datasets and methods prioritize **representative, uncertainty-aware sampling** and **combining measured and modeled data** to fill gaps.

---

## 4) Counterarguments, Criticisms & Unresolved Debates

* **Crowdsourced infrastructure datasets** (OpenCelliD, WiGLE): valuable but **approximate**, with positional errors, sampling bias, and API/export limits; not direct exposure values. ([OpenCellID][11], [The OpenCelliD Community][12], [wigle.net][7])
* **Epidemiology interpretation:** Debate persists on **ELF and childhood leukemia** (associations vs causality) and **RF long-term cancer risk**; IARC’s 2B classification reflects uncertainty and need for continuous surveillance. ([World Health Organization][13], [IARC][14])
* **Transferability of outdoor metrics to indoor exposure:** Penetration losses vary by materials; model choice (e.g., 38.901) and parameterization can swing indoor predictions.
* **Temporal dynamics:** Network traffic and duty cycles (e.g., 5G TDD, Wi-Fi beacons vs data bursts) create **time variability**; single snapshots can mislead if not time-averaged per standards (e.g., 6-min RF average in many regimes). (Framework basis: ICNIRP/IEC). ([ICNIRP][1], [ANSI Webstore][3])

---

## 5) Anomalies, Outliers & Niche Contradictions

* **Localized indoor hotspots** near **repeaters, femtocells, or DECT bases** can exceed typical background by orders of magnitude while still generally within limits; mapping resolves these small-scale gradients. (Method guidance via IEC/ICNIRP; field campaigns from regulators illustrate such variability.) ([ComReg][5])
* **Non-intuitive propagation** (e.g., **corridor waveguides**, metallic appliances creating **standing waves**) causing peaks in unexpected locations—captured by dense walk-through logs and spectral scans. (Principles per 38.901 and IEC case studies). ([ANSI Webstore][3])
* **Crowd maps vs reality:** Cell-site databases may show towers where none exist (triangulation centroiding, stale records), requiring on-site verification and/or regulator datasets to ground-truth. ([The OpenCelliD Community][12])

---

## 6) Practical Applications & Implications

**Who benefits & how**

* **Homeowners/tenants:** Room-by-room EMF profiles; router placement; baby-room audits; EV-charger/install checks.
* **Installers/ISPs/IoT vendors:** Pre/post-install surveys; interference root-cause analysis; spectrum planning.
* **Regulators/municipalities:** Evidence-based communication to the public via **open measurement reports** and **site databases** (e.g., ComReg SiteViewer + measurement programme). ([siteviewer.comreg.ie][15], [ComReg][5])
* **Researchers/consultancies:** Combine **open infrastructure data** (OpenCelliD/WiGLE/OSM power lines) with **on-site logs** and **propagation models** to create high-resolution exposure maps, with uncertainties.

---

## 7) Historical Evolution & Future Trajectory

* **1990s–2000s:** Focus on **ELF** near power lines and in homes; early pooled analyses and IARC ELF 2B (2002). ([IARC Publications][10])
* **2010s:** Smartphone era + 3G/4G; **IARC RF 2B (2011)**; rise of crowd databases and regulator portals. ([IARC][9])
* **2020s:** **ICNIRP 2020 RF update**, **IEEE C95.1-2019**, stricter, clearer methods; **5G NR** deployment with TDD/time-slotting; richer national reporting portals (e.g., ComReg measurement reports). ([ICNIRP][1], [IEEE Standards Association][2], [ComReg][5])

**What’s next**

* **Higher-fidelity indoor models** (multi-band, material libraries), bridging measurements with ray-tracing/statistics (per 38.901).
* **Continuous/regulator monitoring** dashboards that **publish raw spectra & time series**, not only PDFs.
* **Validated crowdsensing** (phone-based) with **calibrated devices** or **compensation models**, plus robust **uncertainty metadata**.
* **Integration** of **site inventories + coverage models + in-home surveys** into reproducible pipelines (open source notebooks, GIS layers).

---

## 8) Dataset Landscape (curated, with use-cases)

### A) National/regulatory datasets (best for ground-truth of external sources)

* **Ireland (ComReg):**

  * **SiteViewer** – locations and details for mobile sites; underlying licensed-site schedules include coordinates/technology by operator. ([siteviewer.comreg.ie][15], [ComReg][16])
  * **EMF/Non-Ionising Radiation (NIR) measurement reports** – periodic, site-specific RF compliance surveys with instrumentation detail; useful exemplars for methods and typical levels. ([ComReg][5])
  * **EPA RF EMF monitoring pages** – point to ComReg datasets and explain context. ([EPA Ireland][17])

* **Other EU examples (indicative):** Swiss/German/Italian public EMF monitoring portals and site databases (varies by country); generally aligned to **ICNIRP 2020**. (ICNIRP/GSMA policy overview). ([ICNIRP][1], [GSMA][18])

### B) Infrastructure/crowd location datasets (context for modeling; **not exposure**)

* **OpenCelliD** – global, community-driven **cell site** database; downloadable per-country CSV and full dumps; widely used for coverage studies (note: **approximate locations**). ([opencellid.org][6], [OpenCellID][11])
* **WiGLE** – global **Wi-Fi/Bluetooth AP** sightings; downloadable with account/API constraints; good for indoor RF source density mapping (privacy/completeness caveats). ([wigle.net][7])
* **World Bank rasterized OpenCellID** – a gridded layer of global cell towers for quick context. ([datacatalog.worldbank.org][19])
* **OpenStreetMap power infrastructure** – medium/low-voltage lines, substations; useful proxies for **ELF context** around homes when paired with on-site measurements (download via OSM extracts).

### C) Standards/methods datasets (how to measure & report)

* **IEC 62232** case-study TR – worked examples for RF surveys around base stations, uncertainty handling, and reporting templates (methods transferable to residential). ([ANSI Webstore][3])
* **ITU/IEC TC106 overview** – scope and principles for EMF measurement/calculation from 0 Hz–300 GHz. ([ITU][4])

### D) Regulator measurement reports (PDF tables/appendices as “micro-datasets”)

* Country regulators often publish **spectral scans** and **band-resolved levels** at schools/hospitals/housing estates. In Ireland, ComReg’s 2023–2025 interim reports are directly reusable (copy data; geocode). ([ComReg][20])

### E) In-home survey datasets (research projects; often request-on-ask)

* University/agency studies with **ELF and RF logs** inside residences; availability varies. (IARC and WHO pages summarize key evidence lines and typical levels; contact authors for raw data.) ([World Health Organization][13])

### F) Device-level EMI data

* **Certification test reports** (e.g., FCC/CE) include **radiated/conducted emissions plots** for household devices (CISPR-32 classes). While oriented to compliance, these PDFs can seed spectral fingerprints for **EMI source identification** in homes (obtain per device model from public certification portals).

---

## 9) Methods & Pipelines (how to build a high-quality residential map)

**A. Outdoor context layer**

1. Download **licensed site lists** / **regulatory site viewers** (e.g., ComReg schedules; SiteViewer). Clean coordinates/tech bands. ([ComReg][16])
2. Augment with **OpenCelliD** towers (for redundancy) and **OSM power lines/substations** (ELF context). Flag crowd vs regulator provenance. ([opencellid.org][6])
3. Compute **distance/azimuth** to home; add **3GPP 38.901** penetration loss ranges for candidate materials to bound indoor expectations.

**B. Indoor measurement layer**

* **ELF:** Grid-walk at 0.5–1 m height; log **B-field (µT)** and **harmonics** near panels/appliances; map 2D heatmaps per room.
* **RF:** Do both **broadband** (total) and **frequency-selective** scans per band (e.g., 700/800/900/1800/2100/2600/3500 MHz; Wi-Fi 2.4/5/6 GHz; DECT). Average per standard time windows; add duty-cycle notes for bursty sources. (Methods anchored in **IEC 62232** and **ICNIRP RF**). ([ANSI Webstore][3], [ICNIRP][1])

**C. Data management**

* Store **timestamped logs**, probe metadata, calibration factors, room polygons, photos of measurement points, and uncertainty budgets.
* Export **GIS layers** (points/rasters) + **summary tables** with **reference-level fractions** (e.g., % of ICNIRP public limits) for stakeholder-friendly reporting. ([ICNIRP][1])

**D. QA & uncertainty**

* Replicate key points; vary orientation; document peak/average; keep **chain-of-uncertainty** per IEC/TC106 guidance. ([ITU][4])

---

## 10) Risk & Ethics (using crowd/open data at residential scale)

* **Accuracy & consent:** Crowd datasets **do not** equal exposure and may **mis-locate** hardware; always caveat and verify on-site with calibrated instruments or regulator data. ([The OpenCelliD Community][12])
* **Privacy:** Wi-Fi AP locations can imply household presence; follow WiGLE/OpenCelliD terms and minimize precision in public outputs. ([wigle.net][21])

---

## 11) Quick “Starter Kit” (practical)

* **Regulator base layer (IE):** ComReg **SiteViewer** + **licence schedules** + **NIR measurement PDFs**. ([siteviewer.comreg.ie][15], [ComReg][16])
* **Context augments:** OpenCelliD towers (country extract), WiGLE AP heat, OSM power lines. ([opencellid.org][6], [wigle.net][7])
* **Standards to follow:** ICNIRP RF 2020; IEEE C95.1-2019; IEC 62232 case-study TR for procedures/uncertainty. ([ICNIRP][1], [IEEE Standards Association][2], [ANSI Webstore][3])
* **Modeling:** 3GPP 38.901 indoor/penetration to bracket indoor vs outdoor deltas.

---

## 12) Key Sources & Further Reading (curated)

**Standards & frameworks**

* **ICNIRP RF Guidelines (2020)** and recent research priorities (2025 statement). ([ICNIRP][1])
* **IEEE C95.1-2019** (safety levels 0 Hz–300 GHz). ([IEEE Standards Association][2])
* **IEC 62232** + case-study technical report (methods, examples). ([ANSI Webstore][3])
* **ITU/IEC TC106 overview** (0 Hz–300 GHz measurement/calculation). ([ITU][4])
* **3GPP TR 38.901** (indoor propagation & penetration models).

**Regulator portals (Ireland)**

* **ComReg SiteViewer** (sites) and **measurement programme** (NIR reports). ([siteviewer.comreg.ie][15], [ComReg][5])
* **ComReg licence schedules** (underlying site data; per operator/band). ([ComReg][16])
* **EPA RF EMF monitoring page** (context & links). ([EPA Ireland][17])

**Infrastructure/crowd datasets**

* **OpenCelliD** (global towers; downloads & schema). ([opencellid.org][6], [OpenCellID][11])
* **WiGLE** (Wi-Fi/BT AP mapping; policy/FAQ). ([wigle.net][7])
* **World Bank rasterized cell tower map** (quick global layer). ([datacatalog.worldbank.org][19])

**Health/epidemiology background**

* **IARC**: RF **Group 2B** classification (2011) & ELF **Group 2B** (2002) with context. ([IARC][9], [IARC Publications][10])

---

## Bottom line

High-quality **residential EMF/EMI maps** blend **on-site, standards-based measurements** with **trusted external context** (licensed site inventories, regulator reports), and—where useful—**crowd infrastructure layers** clearly labeled as approximate. The most credible outputs quantify **uncertainty**, report levels as a **fraction of ICNIRP/IEEE limits**, and retain **time-variability** (peak/average) to avoid over- or under-statement.

[1]: https://www.icnirp.org/?utm_source=chatgpt.com "ICNIRP.org"
[2]: https://standards.ieee.org/ieee/C95.1-2019_Cor_2/10321/?utm_source=chatgpt.com "IEEE C95.1-2019/Cor 2-2020 - IEEE SA"
[3]: https://webstore.ansi.org/preview-pages/BSI/preview_30218245.pdf?srsltid=AfmBOopwKobIAWrGpbWmINruzA48UeBoSiV3twPBR9oS_6apthLhBK4s&utm_source=chatgpt.com "[PDF] Case studies supporting IEC 62232 — Determination of RF field ..."
[4]: https://www.itu.int/dms_pub/itu-t/oth/06/4f/t064f0000030023pdfe.pdf?utm_source=chatgpt.com "[PDF] Evaluating RF field strength and SAR from radio base station sources"
[5]: https://www.comreg.ie/?dlm_download=first-interim-report-2024-programme-of-measurement-of-non-ionising-radiation&utm_source=chatgpt.com "Programme of Measurement of Non-Ionising Radiation - ComReg"
[6]: https://opencellid.org/downloads.php?utm_source=chatgpt.com "Data Downloads - OpenCelliD - by Unwired Labs - OpenCelliD"
[7]: https://wigle.net/?utm_source=chatgpt.com "WiGLE: Wireless Network Mapping"
[8]: https://opencellid.org/?utm_source=chatgpt.com "OpenCelliD - Largest Open Database of Cell Towers & Geolocation ..."
[9]: https://www.iarc.who.int/pressrelease/iarc-classifies-radiofrequency-electromagnetic-fields-as-possibly-carcinogenic-to-humans/?utm_source=chatgpt.com "IARC classifies Radiofrequency Electromagnetic Fields as possibly ..."
[10]: https://publications.iarc.fr/Book-And-Report-Series/Iarc-Monographs-On-The-Identification-Of-Carcinogenic-Hazards-To-Humans/Non-ionizing-Radiation-Part-1-Static-And-Extremely-Low-frequency-ELF-Electric-And-Magnetic-Fields-2002?utm_source=chatgpt.com "Non-ionizing Radiation, Part 1: Static and Extremely Low-frequency ..."
[11]: https://wiki.opencellid.org/wiki/Database_format?utm_source=chatgpt.com "Database format - OpenCellID wiki"
[12]: https://community.opencellid.org/t/how-can-i-get-cell-towers-locations/1300?utm_source=chatgpt.com "How can I get Cell Towers locations? - The OpenCelliD Community"
[13]: https://www.who.int/teams/environment-climate-change-and-health/radiation-and-health/non-ionizing/exposure?utm_source=chatgpt.com "Exposure to extremely low frequency fields - Radiation and health"
[14]: https://www.iarc.who.int/wp-content/uploads/2018/07/pr208_E.pdf?utm_source=chatgpt.com "[PDF] IARC classifies Radiofrequency Electromagnetic Fields as possibly ..."
[15]: https://siteviewer.comreg.ie/?utm_source=chatgpt.com "ComReg SiteViewer"
[16]: https://www.comreg.ie/industry/radio-spectrum/licensing/search-licence-type/mobile-licences-2/?utm_source=chatgpt.com "Mobile & WBB-Licensed apparatus & sites - ComReg"
[17]: https://www.epa.ie/environment-and-you/radiation/emf/emf-monitoring-programme/rf-emf-monitoring-programme/?utm_source=chatgpt.com "RF EMF monitoring programme - EPA.ie"
[18]: https://www.gsma.com/solutions-and-impact/connectivity-for-good/public-policy/regulatory-environment/emf-and-health/emf-policy/?utm_source=chatgpt.com "EMF Policy - Public Policy - GSMA"
[19]: https://datacatalog.worldbank.org/dataset/global-opencellid-cell-tower-map?utm_source=chatgpt.com "World Bank OpenCellID Cell Tower Map"
[20]: https://www.comreg.ie/?dlm_download=fourth-interim-report-2023-programme-of-measurement-of-non-ionising-radiation&utm_source=chatgpt.com "Fourth Interim Report 2023 – Programme of Measurement of Non ..."
[21]: https://wigle.net/privacy?utm_source=chatgpt.com "Privacy: Frequently Asked Questions - WiGLE.net"
