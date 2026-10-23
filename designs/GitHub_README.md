# High-Gain E-Shaped 2x1 Microstrip Patch Array Antenna with Defected Ground Structure (DGS) for 2.45 GHz ISM Band

## Project Overview
This repository contains the design, full-wave electromagnetic simulation (Ansys HFSS 2025 R2), parametric optimization, and comparative analysis of a series of planar microstrip antennas for the **2.45 GHz ISM Band (2.4000 GHz – 2.4835 GHz)**.

The project traces the evolution from a baseline single patch up to an advanced **E-shaped 2x1 patch array incorporating Defected Ground Structure (DGS)** on a cost-effective FR4 substrate (height h = 2.4 mm, dielectric constant eps_r = 4.4, loss tangent tan_delta = 0.02).

---

## Performance Comparison Table

| Antenna Design | Configuration | Resonant Freq f0 (GHz) | S11 at f0 (dB) | -10 dB Bandwidth (MHz) | Peak Gain (dBi) | Peak Directivity (dBi) | Radiation Efficiency (%) | Status / Remarks |
|---|---|---|---|---|---|---|---|---|
| **Design 1** | Single Patch (Conventional) | 2.450 | -14.20 | 45.0 (1.84%) | 3.50 | 6.50 | ~50.0% | Baseline single-element reference |
| **Design 2** | 2x1 Patch Array (Solid Ground) | 2.450 | -15.50 | 60.0 (2.45%) | 5.50 | 8.20 | 51.5% | Gain boosted via array factor |
| **Design 3** | 2x1 Array + DGS (No Inset) | 2.465 | -14.20 | 89.6 (3.64%) | 5.80 | 8.70 | 52.0% | Wideband DGS, but shifted +15 MHz high |
| **Design 4** | 2x1 Array + DGS + Inset Feed | 2.445 | -16.83 | 86.4 (3.53%) | 6.30 | 9.09 | 52.60% | 100% ISM band coverage (Verified Baseline) |
| **Design 8** | **2x1 E-Shaped Array + DGS (Final)** | **2.445** | **-19.08** | **83.7 (3.42%)** | **6.53** | **9.12** | **55.08%** | **Highest Gain, Best Matching, Peak Efficiency** |

---

## Detailed Design Breakdown: Use & Novelty

### Design 1: Single Rectangular Microstrip Patch (Baseline)
- **Configuration**: Standard rectangular patch (w = 37.41 mm, l = 28.8 mm / 37 mm) with solid copper ground plane on FR4 (h = 2.4 mm).
- **Intended Use**: Fundamental reference model to benchmark radiation properties, impedance behavior, and narrow bandwidth of a standalone thick-substrate microstrip antenna.
- **Novelty**: Conventional reference benchmark (no modifications). Serves as the control for all comparative metrics.

---

### Design 2: 2x1 Microstrip Patch Array with Corporate Feed
- **Configuration**: Two radiating patches spaced center-to-center by d = 70 mm (~0.57 lambda0), excited by a corporate T-junction microstrip power divider (50 Ohm input split into two 70.7 Ohm quarter-wave transformers feeding 100 Ohm patch ports), solid ground plane.
- **Intended Use**: Point-to-point wireless links requiring higher directivity and narrower half-power beamwidth (HPBW) than a single patch.
- **Novelty**: Implementation of an integrated, matched microstrip corporate feed network providing equal-amplitude, in-phase excitation, delivering a **+2.0 dBi gain increase** over Design 1.

---

### Design 3: 2x1 Array with Defected Ground Structure (DGS)
- **Configuration**: 2x1 array with etched rectangular defect slots in the ground plane directly below the radiating patches (W_dgs = 7 mm, L_dgs = 1 mm), without inset feed compensation.
- **Intended Use**: Investigating surface-wave suppression and equivalent circuit capacitance/inductance loading via ground plane defects.
- **Novelty**: Etching periodic DGS slots disturbs ground return currents, acting as a parallel LC resonator. This widened the -10 dB bandwidth from **60 MHz to 89.6 MHz (+49.3% increase)**, though it caused a slight frequency offset (f0 = 2.465 GHz).

---

### Design 4: 2x1 Array with DGS and Inset Feed Matching (Verified Baseline)
- **Configuration**: Dual-patch array combining DGS ground slots with recessed inset feeds (fi = 9.2 mm - 10 mm, w70 = 1.65 mm - 2.0 mm) directly cut into each patch.
- **Intended Use**: Full-compliance 2.45 GHz ISM band transceivers (Bluetooth, Wi-Fi 802.11 b/g/n, Zigbee, RFID) requiring continuous S11 < -10 dB from 2.4000 GHz to 2.4835 GHz.
- **Novelty**: Synergistic co-optimization of DGS reactive loading with inset feed position. Re-centered the resonance to exactly **2.4450 GHz** while maintaining **86.4 MHz bandwidth (2.3986 GHz – 2.4850 GHz)**, achieving 100% coverage of the ISM band with Peak Gain of **6.30 dBi** and Directivity of **9.09 dBi**.

---

### Design 8: 2x1 E-Shaped Patch Array with Defected Ground Structure (Final Proposed)
- **Configuration**: Dual symmetrical rectangular parallel slots (E-slots: L_eslot = 15 mm, W_eslot = 2 mm, spacing S_eslot = 7 mm) etched into the top radiating edge of each patch, combined with DGS ground slots and fine-tuned patch dimensions (l = 37.78 mm).
- **Intended Use**: High-performance, high-efficiency, planar directional terminal for modern 2.45 GHz wireless systems and IoT gateways where maximum gain and power transfer efficiency are critical.
- **Novelty**:
  1. **Hybrid E-Slot and DGS Integration**: Combining top-side E-shaped patch perturbation with bottom-side DGS creates a complex current path that optimizes current concentration along the outer patch arms.
  2. **Enhanced Radiation Efficiency**: Increased radiation efficiency to **55.08%** (+2.48% improvement over Design 4), overcoming typical dielectric losses in commercial FR4.
  3. **Peak Gain Maximization**: Achieved the highest gain across all designs at **6.53 dBi** (Directivity = **9.12 dBi**).
  4. **Superior Impedance Matching**: Achieved return loss of **-19.08 dB** at 2.4450 GHz (VSWR ≈ 1.25, accepted power > 98.8%), with the 83.7 MHz operational band aligned across the 2.45 GHz ISM spectrum.

---

## Substrate & Geometric Specifications

- **Substrate Material**: FR4_epoxy
- **Relative Permittivity (eps_r)**: 4.4
- **Loss Tangent (tan_delta)**: 0.02
- **Substrate Height (h)**: 2.4 mm
- **Substrate Dimensions (SubX x SubY)**: 140 mm x 70 mm
- **Patch Spacing (d)**: 70 mm (~0.57 lambda0 at 2.45 GHz)
- **Patch Width (w)**: 37.41 mm
- **Patch Length (l)**: 37.78 mm
- **50 Ohm Feed Line Width (wf1)**: 3.02 mm
- **Quarter-Wave Transformer Width (w70)**: 2.0 mm
- **Quarter-Wave Transformer Length (l70)**: 15.15 mm
- **Inset Depth (fi)**: 10.0 mm
- **Inset Gap (g)**: 1.0 mm
- **DGS Dimensions (W_dgs x L_dgs)**: 7.0 mm x 1.0 mm
- **E-Slot Dimensions (L_eslot x W_eslot)**: 15.0 mm x 2.0 mm
- **E-Slot Spacing (S_eslot)**: 7.0 mm
