# H-120 Reagent & Consumables Reference Guide

**Complete specifications, roles, and usage guidelines for Mindray H-120 Analyzer**

---

## 🧪 Reagent Overview

The H-120 uses a **gradient elution system** with 3 main consumables:

| Reagent | Volume | Life | Cost Impact | RFID Tracked |
|---------|--------|------|-------------|--------------|
| **Hemolysis Solution (H-12H)** | 5.6L | ~3000 tests | Low | ✅ Yes |
| **Eluent A (H-12A)** | 1.5L | ~10,000 tests | Medium | ✅ Yes |
| **Eluent B (H-12B)** | 250mL | ~30,000 tests | Low | ✅ Yes |
| **Analytical Column** | N/A | 3,000-10,000 tests | High | ✅ Yes |
| **Filter** | N/A | 3,000 tests | Medium | ✅ Yes |

---

## 1️⃣ HEMOLYSIS SOLUTION (H-12H)

### Purpose
**Lyses (breaks open) red blood cells to release hemoglobin for analysis**

### Chemical Composition
- **Active Component:** Non-ionic detergent + surfactant
- **Buffer:** Carbonate buffer (pH ~10.5)
- **Osmotic Agent:** Maintained to prevent hemoglobin denaturation
- **Preservative:** Sodium azide (prevents bacterial growth)

### Role in Analysis
```
Whole Blood Sample (10µL)
    ↓
+ Hemolysis Solution (100-200µL)
    ↓
RBCs rupture → Release hemoglobin (Hb)
    ↓
Hemoglobin particles remain stable in solution
    ↓
Ready for HPLC column injection
```

### Technical Details
- **Package:** 5.6L container (multiple bottles)
- **Storage:** 2-8°C (refrigerated)
- **Shelf Life:** 12 months from manufacturing date
- **RFID Tag:** Tracks lot #, expiry, volume remaining
- **Consumption:** ~1-2 mL per test (very high efficiency)

### Critical Performance Factors

| Parameter | Specification | Why It Matters |
|-----------|---------------|-----------------|
| **pH** | 10.4-10.6 | Controls Hb charge & separation efficiency |
| **Osmolality** | 270-290 mOsm/kg | Prevents Hb denaturation or precipitation |
| **Clarity** | Crystal clear | Particles interfere with sample injection |
| **Sterility** | Free of bacteria | Prevents column clogging & sample contamination |

### Troubleshooting

**Problem:** Hemolyzed sample looks brown/dark
- **Cause:** Oxidized hemoglobin (old solution or improper storage)
- **Fix:** Replace solution bottle; check storage temp

**Problem:** Inconsistent results between tubes
- **Cause:** Uneven hemolysis (insufficient hemolysis solution)
- **Fix:** Verify tube volume ratio (sample:hemolysate = 1:10-1:20)

**Problem:** Peak heights decreasing over time
- **Cause:** Hemolysis solution concentration drift
- **Fix:** Perform system calibration using quality control samples

---

## 2️⃣ ELUENT A (H-12A) - Primary Buffer

### Purpose
**Provides low-ionic-strength environment to elute weakly-bound hemoglobin (HbA1c first)**

### Chemical Composition
- **Main Component:** Tromethamine buffer (TRIS-HCl)
- **pH:** 8.9-9.1
- **Ionic Strength:** Low (≈0.05 M)
- **Additives:** Small amount of organic modifier (acetonitrile ~3-5%)

### Role in Gradient Elution System
```
Column Surface = Negatively charged resin (strong anion exchanger)

Eluent A (LOW salt) injected first:
  Hb + weak charge → Binds weakly to column
  Result: HbA1c elutes FIRST (~1.5 min)

Gradient transition (Eluent A → B mix):
  Salt concentration increases gradually
  Hb variants elute in middle (~2-5 min)
  
Eluent B (HIGH salt) at end:
  Hb + high charge → Cannot bind
  Result: HbA0 & HbA2 elute LAST (~3-5 min)
```

### Technical Details
- **Package:** 1.5L bottle
- **Storage:** Room temperature (15-25°C), away from light
- **Shelf Life:** 12 months unopened
- **Compatibility:** HPLC-grade purity
- **Consumption Rate:** ~0.15 mL/test (lower than Eluent B)

### pH Sensitivity (CRITICAL ❗)

The H-120's separation depends on pH-controlled charge:
- **pH 8.5:** HbA1c elutes too fast; variants co-elute
- **pH 8.9-9.1:** OPTIMAL separation window
- **pH 9.3:** HbA1c elutes too slowly; resolution lost

**If pH drifts:** System flags "Recalibration Recommended" in software

### Quality Control for Eluent A

| Check | Frequency | How |
|-------|-----------|-----|
| **Visual** | Daily | Clear, no precipitate |
| **pH** | Weekly | pH meter 8.9-9.1 |
| **Reference Run** | Weekly | Inject QC material; compare peaks |
| **Osmolality** | Monthly | Osmometer ~280 mOsm/kg |

---

## 3️⃣ ELUENT B (H-12B) - High-Salt Buffer

### Purpose
**High-salt environment to elute all bound hemoglobin from column (repels Hb from resin)**

### Chemical Composition
- **Main Component:** Sodium chloride (NaCl) in Tromethamine buffer
- **Salt Concentration:** HIGH (~0.3-0.4 M)
- **pH:** ~9.1 (matched to Eluent A for gradient stability)
- **Organic Modifier:** Similar to Eluent A for gradient compatibility

### Role in Gradient Elution
```
During analysis:
- 0-1 min: 100% Eluent A (weakly bound Hb elutes)
- 1-6 min: Gradient mix (A→B ratio changes)
           (Hb variants progressively elute)
- 6+ min:  100% Eluent B (complete column flush)
           (Highly bound Hb elutes; prep for next cycle)
```

### Technical Details
- **Package:** 250mL bottle (concentrates further than Eluent A)
- **Storage:** Room temperature, light-protected
- **Shelf Life:** 12 months unopened
- **Preparation:** May come concentrated; verify dilution ratio
- **Consumption Rate:** Much lower than Eluent A (smaller volume)

### Why Separate A & B?

Mindray uses **gradient elution** (proprietary advantage):
```
Other methods (fixed eluent):
  ❌ Limited separation resolution
  ❌ Can't detect rare variants
  ❌ Higher false-positive rates

H-120 Gradient:
  ✅ Continuously changes salt concentration
  ✅ Each Hb type finds optimal elution point
  ✅ Better separation → Detects HbS/C/D/E/rare variants
  ✅ HbA1c accuracy ±2% (IFCC certified)
```

### Pressure Retention Technology Connection

H-120's **Pressure Storage Device (PSD)** works with Eluent system:

```
Traditional HPLC:
  Build pressure → Inject sample → De-pressurize
  REPEAT every sample = 6 reagent cycles/test

H-120 (Patent ZL201610119446.5):
  Build pressure ONCE → Store in PSD
  Next 20+ samples: Use stored pressure
  Result: 0.3 reagent consumptions/test (vs. 6!)
  
Cost Savings: 95% less eluent waste
```

---

## 4️⃣ ANALYTICAL COLUMN

### Purpose
**Separates hemoglobin variants by electrical charge using ion-exchange chromatography**

### Technical Specifications

| Parameter | Value | Significance |
|-----------|-------|--------------|
| **Type** | Anion-exchange resin (strong) | Binds positively-charged Hb |
| **Particle Size** | ~3 µm (industry-leading) | Finer = better separation |
| **Column Length** | 50-75mm | Standard HPLC dimension |
| **Column Diameter** | 4.6mm | Semi-preparative scale |
| **Resin Capacity** | ~50-100 µmol Hb/mL resin | Can handle 10+ tests before clogging |
| **Maximum Pressure** | 25-30 MPa | H-120 operates at 10-15 MPa |

### Resin Surface Chemistry
```
Column Resin (fixed negative charge):
  -O-SO₃⁻ -O-SO₃⁻ -O-SO₃⁻ -O-SO₃⁻
  (sulfonic acid groups)

When hemoglobin flows through:
  HbA1c (charge +1) ← Binds weakly
  HbS/C (charge +2) ← Binds moderately  
  HbA0 (charge +3) ← Binds strongly

Lower salt (Eluent A):
  → All Hb bound; none elutes

Higher salt (Eluent B):
  → Na⁺ ions compete for charge sites
  → Hb gets pushed off column
```

### Column Variants

The H-120 ships with **one main column type** for all tests:

**Standard Mode + Variant Mode:** Same column
- No need to replace (Mindray's advantage)
- Software automatically switches mode
- Competitors require column changes

### Column Life Expectancy

| Usage | Tests | Duration | Signs of Wear |
|-------|-------|----------|---------------|
| **Light** | 3,000 | ~4 weeks | None |
| **Normal** | 6,000 | ~8 weeks | Slight baseline drift |
| **Heavy** | 10,000 | ~12 weeks | Peak broadening, ↓ resolution |
| **Expired** | >10,000 | >12 weeks | Severe peak degradation, CV >2% |

### Column Contamination & Preventive Measures

**What degrades columns:**

| Contaminant | Source | Prevention |
|------------|--------|-----------|
| **Particulates** | Blood cells, clots | Good hemolysis; filter system |
| **Proteins** | Non-hemoglobin Hb aggregates | Use hemolysis solution correctly |
| **Salts** | Improper buffer pH | Weekly pH checks |
| **Bacterial growth** | Stagnant eluent | Store eluent refrigerated |
| **Air bubbles** | Eluent storage | Purge system daily |

### Column Maintenance Protocol

**Daily:**
- System purge (2-3 cycles with Eluent A)
- Check baseline absorbance
- Verify pressure stability

**Weekly:**
- Inject QC sample; compare to baseline chromatogram
- Perform system suitability test
- Check column pressure (should be stable ±0.5 MPa)

**Monthly:**
- Verify column efficiency (Resolution >1.5 for HbA1c/HbS separation)
- If Resolution <1.5 → Column replacement recommended

---

## 5️⃣ FILTER (In-Line Sample Filter)

### Purpose
**Removes particulates from hemolyzed blood before column injection**

### Specifications
- **Type:** 10 µm pore size (in-line filter)
- **Material:** PTFE (Teflon) membrane
- **Lifespan:** 3,000 tests (same as consumable kit)
- **Flow Rate:** ≥1 mL/min at 15 MPa

### Why Filtration Matters

```
Unfiltered hemolyzed sample:
  Contains: RBC remnants, platelets, fibrin clots
  Result: Column clogs → Pressure ↑↑, Peaks broaden
  
Filtered sample:
  ✅ Clear solution, no particles
  ✅ Column stays clean
  ✅ Consistent peak shapes
  ✅ Reproducible retention times
```

### Filter Saturation Signs

| Sign | Action |
|------|--------|
| System pressure ↑ by >2 MPa | Change filter immediately |
| Chromatogram baseline noisy | Check filter condition |
| Peak broadening across all samples | Replace filter |

---

## 🧬 QUALITY CONTROL & CALIBRATOR

### Hemoglobin A1c Control Material

**Purpose:** Monitor system performance and detect drift

| Item | Specification |
|------|---------------|
| **Format** | Liquid whole blood + preservative |
| **Levels** | Usually Level 1 (low), Level 2 (mid), Level 3 (high) |
| **Volume** | 1mL per vial (30-40 tests/vial) |
| **Storage** | 2-8°C, stable 30-60 days opened |
| **Traceability** | IFCC-traceable or NGSP-certified |

### Calibration Material

**Purpose:** Set system reference for HbA1c% calculation

- **Format:** Lyophilized (freeze-dried) whole blood
- **Target Values:** Assigned by IFCC/NGSP
- **Frequency:** Daily recalibration (or per protocol)
- **Expiry:** Check lot; typically 12-18 months

---

## 📦 REAGENT CONSUMABLES KIT OPTIONS

### H-10 Kit (10,000 Tests)
- **Hemolysis Solution:** 1x 5.6L bottle
- **Eluent A:** 3x 1.5L bottles  
- **Eluent B:** 2x 250mL bottles
- **Analytical Column:** 1x (rated for 10,000 tests)
- **Filter:** 1x (rated for 3,000 tests; replace 3x during kit use)
- **Typical Duration:** ~2 months (120 T/H throughput)
- **Cost:** $$$ (bulk discount available)

### H-6 Kit (6,000 Tests)
- **Partial quantities** of above
- **Typical Duration:** ~4-5 weeks
- **Cost:** $$ 

### H-3 Kit (3,000 Tests)
- **Starter/trial quantities**
- **Typical Duration:** ~2-3 weeks
- **Cost:** $ (best for new installations)

---

## 🔄 REAGENT REPLACEMENT PROCEDURE

### Step 1: Eluent A & B Replacement (EASY ✅)

```
1. Open reagent bay door (front of analyzer)
2. Locate Eluent A bottle (LEFT side, blue cap)
3. Unscrew old bottle (counterclockwise)
4. Place new bottle in holder
5. Screw clockwise until tight
6. RFID automatically detects new lot #
7. System runs self-check (2 minutes)
8. Repeat for Eluent B (RIGHT side, red cap)

Time: <5 minutes per bottle
Error Rate: Very low (design prevents mistakes)
```

### Step 2: Hemolysis Solution (H-12H) Replacement

```
1. Locate Hemolysis solution bay (underneath autoloader)
2. Unscrew connection tube from old bottle
3. Connect tube to new bottle
4. Insert into bay; secure with latch
5. System prime: 2 seconds of hemolysis flow
6. RFID confirms new lot

Time: <3 minutes
Note: Solution drains from previous bottle, so zero spillage
```

### Step 3: Analytical Column & Filter (MODERATE ⚠️)

```
Column Replacement:
1. Shut down system (graceful shutdown = 5 min flush)
2. Open column compartment (blue housing)
3. Loosen inlet & outlet fittings (wrench provided)
4. Slide old column out (careful: may have residual pressure)
5. Slide new column in (align markers)
6. Tighten inlet & outlet (hand-tight + 1/4 turn)
7. Run system flush (purge air bubbles, 10 min)
8. Perform system suitability test

Time: ~20 minutes total
Error Rate: Low (color-coded for correct orientation)

Filter Replacement:
Similar procedure but easier (1-page diagram in manual)
Time: ~5 minutes
```

---

## 🌡️ STORAGE & STABILITY

### Refrigerated (2-8°C)
- Hemolysis Solution: Essential
  - **Why:** Preservative degrades if warm
  - **Duration:** 12 months unopened
  - **Once opened:** Use within 3-6 months (monitor pH)

### Room Temperature (15-25°C)
- Eluent A: Stable
  - **Duration:** 12 months
  - **Tip:** Store in dark cabinet (light degrades)
  
- Eluent B: Stable
  - **Duration:** 12 months
  - **Tip:** Check for salt crystallization (if present = replace)

- Analytical Column & Filter: Stable indefinitely
  - **Expiry based on:** Test count, not calendar date

### Control & Calibration Material
- **Refrigerated:** 2-8°C for stability
- **Duration:** 30-60 days once opened
- **Discard:** If shows crystallization, discoloration, or past lot expiry

---

## 💰 COST OPTIMIZATION FOR HOSPITALS

### Volume Discounts
```
1-5 units (H-120):       → H-3 kit standard (baseline cost)
6-10 units:              → 10% discount on H-6 kits
10+ units (CAL system):  → 20% discount on H-10 kits
```

### Reagent Waste Reduction

**H-120 advantages (vs. Bio-Rad D100, Sebia Capillarys):**

| Feature | H-120 | Competitors |
|---------|-------|-------------|
| **Pressure Storage Device** | Yes (0.3 test consumptions) | No (6 test consumptions) |
| **Sample Volume** | 10µL (4µL pre-diluted) | 15-20µL |
| **Eluent Usage** | Minimal/optimized | Standard consumptions |
| **Annual Savings (per 100K tests)** | ~$15,000-20,000 | Baseline |

### Preventive Maintenance Cost Savings

**Good practice reduces expensive service calls:**

| Action | Prevents | Cost Saved |
|--------|----------|-----------|
| Weekly pH check | Incorrect gradient elution | $0 (DIY) |
| Daily system flush | Column blockage | $500-1000/incident |
| Monthly QC injection | Undetected drift | $2000/missed error |
| Proper hemolysis | Particle contamination | $1500-2000/column |

---

## ⚙️ TROUBLESHOOTING BY REAGENT

### Hemolysis Solution Issues

**Symptom:** Baseline absorbance >0.5 (should be <0.2)
- **Likely Cause:** Contaminated/old hemolysis solution
- **Fix:** Replace H-12H bottle; run 5 blank cycles
- **Prevention:** Change every 6 months even if not expired

**Symptom:** Sample injection fails
- **Likely Cause:** Insufficient hemolysis volume or concentration wrong
- **Fix:** Verify tube fill ratio 1:10-1:20 (blood:hemolysate)

---

### Eluent A Issues

**Symptom:** HbA1c eluting too early or too late
- **Likely Cause:** pH drift (Eluent A pH too high/low)
- **Fix:** Measure pH with calibrated pH meter; replace if <8.8 or >9.2
- **Prevention:** Check pH weekly; don't store in warm sunlight

**Symptom:** Resolution between HbA1c & HbS poor
- **Likely Cause:** Gradient elution not working (Eluent A mixing issue)
- **Fix:** Prime system 10 minutes with fresh Eluent A

---

### Eluent B Issues

**Symptom:** Peaks not returning to baseline after elution
- **Likely Cause:** Insufficient Eluent B salt concentration
- **Fix:** Verify Eluent B level (not running low); if adequate, replace bottle

**Symptom:** Analyzer says "Low Eluent B"
- **Fix:** Check actual volume in bottle; may be false low if air in line
- **Solution:** Remove air bubble or replace bottle

---

### Column Issues

**Symptom:** CV% gradually increasing over weeks
- **Likely Cause:** Column packing degradation
- **Fix:** Replace column; check if sample quality poor (causing contamination)

**Symptom:** Peaks split or broadened
- **Likely Cause:** Air bubbles in column or column contamination
- **Fix:** Run 20-minute purge; if not resolved, replace column

---

### Filter Issues

**Symptom:** High back-pressure (>5 MPa above baseline)
- **Likely Cause:** Filter clogged with particulates
- **Fix:** Replace filter immediately (3,000 test limit)

---

## 📋 REAGENT INVENTORY MANAGEMENT

### Recommended Stock Level

For a typical hospital lab running 300-400 tests/day:

| Item | Stock Level | Reorder Point |
|------|------------|---------------|
| Hemolysis Sol. (H-12H) | 2 bottles | 1 bottle remaining |
| Eluent A | 3 bottles | 2 bottles remaining |
| Eluent B | 2 bottles | 1 bottle remaining |
| Column | 2 spare | Use 1st spare when CV>0.5% |
| Filter | 4 spare | 2 remaining |
| QC Material | 4 levels | 1 level remaining |
| Calibrator | 2 lots | 1 lot remaining |

### RFID Tracking Benefits

✅ **Automatic inventory counting** - No manual logs needed
✅ **Expiry alerts** - System warns 1 month before expiry
✅ **Consumption tracking** - Predicts next order date
✅ **Cost analytics** - Cost per test calculation
✅ **Compliance** - Lot traceability for audit

---

## 🌍 SOURCING & ORDERING

### Official Suppliers
- **Mindray Direct** - mindray.com or sales rep
- **Distributor Network** - Regional medical suppliers
- **Hospital Group Contracts** - Bulk purchasing agreements

### What to Order (Standard Format)

```
Product Code: H-120-REAGENT-H-10
Description: H-120 Analyzer Reagent Kit (10,000 tests)
Components:
  - Hemolysis Solution H-12H (1x 5.6L)
  - Eluent A H-12A (3x 1.5L)
  - Eluent B H-12B (2x 250mL)
  - Analytical Column (1x)
  - Filter (1x)
  
Packaging: Standard carton (20 lbs)
Shipping: Room temperature, 2-day express recommended
Invoice: Request lot #, IFCC traceability cert
```

---

## 📚 REFERENCES & FURTHER READING

**From Your H-120 Documentation:**
- Operator's Manual Section 3: Reagent Handling
- Section 5: Column Maintenance
- Appendix B: Troubleshooting Guide

**External Resources:**
- IFCC Official HbA1c Reference: https://www.ifcc.org/ifcc-reference-measurement-system/
- NGSP Quality Assurance Program: https://www.ngsp.org/
- ISO 18153:2003 - In vitro diagnostic devices for HbA1c measurement

---

**Last Updated:** June 2026 | **Mindray H-120 Series Documentation**

*This guide is intended for laboratory professionals. For clinical decision-making, consult official clinical guidelines (ADA, IDF, WHO) for HbA1c interpretation.*
