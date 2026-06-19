# Test Summary Report: Pro Guitar Tuner App (Beta v6.0.9)

## 1. Document Control & Identification
* **Report ID:** TSR-UAT-01
* **Test Level:** User Acceptance Testing (UAT)
* **Object Under Test:** Pro Guitar Tuner App Beta (Version 6.0.9)
* **Date of Issue:** 05 June 2026
* **Lead Tester:** Annalie Prinsloo

## 2. Executive Summary
During the UAT cycle conducted between 1 June and 5 June 2026, the application underwent functional, graphical layout, and real-world acoustic performance testing. 

* A critical initial failure regarding frequency detection (**BUG-UAT-01**) was investigated and successfully **Closed as Invalid** following real-instrument integration testing. The application algorithm functions correctly when exposed to physical instruments with natural harmonic overtones.
* One layout defect (**BUG-UAT-02**) remains **Open**. The application displays significant UI clipping on specific flagship devices when running the ad-supported tier in portrait mode.
* Multiple premium-tier features were explicitly descoped from this test cycle due to account configuration constraints.

## 3. Test Environment & Execution Scope

### 3.1 Test Infrastructure
* **Hardware Matrix:** 
  * Samsung Galaxy S25 FE (Android 16)
  * Samsung Galaxy S21 FE (Android 16)
  * Samsung Galaxy A53 5G (Android 16)
* **Acoustic Baselines:** Verified via Decibel Meter App v3.0.1.
  * Controlled Environment (Studio): Noise floor of 20 dB.
  * High-Noise Environment: Simulated background chatter at 80 dB.

### 3.2 Testing Scope
* **In-Scope:** Pitch-detection accuracy (synthetic vs acoustic), standard tuning configurations, responsive UI scaling across screen profiles, ad-rendering layout impacts, and state preservation.
* **Out-of-Scope (Descoped):** Premium tier exclusives (Half-step down D# tuning, raw Hz readout widgets, cent needle accuracy meters).

## 4. Test Metrics & Execution Summary

### 4.1 Test Case Status Breakdown
A total of **14 test procedures and exploratory charters** were logged over the 4-day testing period.


| Status | Count | Percentage |
| :--- | :--- | :--- |
| **Passed** | 8 | 57.1% |
| **Failed** | 2 | 14.3% |
| **Descoped** | 4 | 28.6% |
| **Blocked** | 0 | 0.0% |
| **Total Logged Actions** | **14** | **100%** |

### 4.2 Detailed Activity Timeline
* **2026-06-01 (Session 1):** Focus on synthetic pitch validation (`PROC-PT-01`). All 3 devices logged a failure due to unrecognised E2, A2, and D3 tones. Defect **BUG-UAT-01** (referenced internally as `BUG-UAT-01`) was opened.
* **2026-06-02 (Session 2):** Focus on UI layout and advertisement containers (`PROC-UI-01`, `PROC-UI-02`). S25 FE and S21 FE failed layout alignment in portrait orientation. Defect **BUG-UAT-02** was opened.
* **2026-06-03 (Session 3):** Evaluation of UI formatting features. 4 items were flagged as out of scope due to premium paywall locks. Core features (Solfège display, active string highlighting) passed.
* **2026-06-05 (Session 4):** Integration testing using physical instruments across varied noise levels (`PROC-INT-01`, `CHARTER-UI-01`, `CHARTER-UI-03`). The app successfully isolated and picked up all real acoustic and electric guitar string frequencies instantly.

## 5. Defect Summary & Status Report

### 5.1 Open Defects
* **BUG-UAT-02: Bottom navigation bar truncates vertically when an interstitial advertisement renders in portrait mode.**
  * *Severity:* Medium | *Priority:* Medium
  * *Current Status:* **Open**
  * *Impact:* Distorts usability on the S21 and S25 screen layouts during ad rendering. Requires dynamic viewport calculation adjustments by development.

### 5.2 Resolved / Closed Defects
* **BUG-UAT-01 (BUG-PT-01): Synthetic frequency matrix targets (E2, A2, D3) not detected for standard tuning.**
  * *Severity:* Major | *Priority:* High
  * *Current Status:* **Closed / Rejected (Not a Bug)**
  * *Resolution Reason:* Environment Issue / Testing Artifact.
  * *Justification:* On 2026-06-05, real instrument validation verified that physical steel-string acoustic, classical nylon, and electric guitars are picked up instantly across all frequency profiles. The initial failure was an artifact of using the Szynalski website, which outputs pure sine waves. The application’s core algorithm requires natural acoustic harmonic overtones to safely process lower frequencies.

## 6. Deviations & Lessons Learned
1. **Testing Methodology Constraint:** Utilizing synthetic tone web-generators introduces a high risk of false-positive defects for audio-processing software. Pure sine waves lack the acoustic complexity of real physical instrument strings. 
2. **Action Item:** Update future Test Plans to mandate physical instruments or high-fidelity recorded acoustic samples as primary test inputs, deprecating generic web-based tone generators.

## 7. Quality Assessment & Recommendation
The core pitch-detection engine of the Pro Guitar Tuner App Beta (Version 6.0.9) is stable, robust against external noise floors up to 80 dB, and handles physical instrumentation with high precision. 

**Recommendation:** **Conditional Release.** The build can be advanced, provided that **BUG-UAT-02** is scheduled for immediate hotfix resolution to fix the visual layout clipping on S21 and S25 devices before full commercial deployment to the free tier audience.
