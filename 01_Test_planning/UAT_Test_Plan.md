# User Acceptance Test (UAT) Plan: Pro Guitar Tuner (Beta)

**Project Name:** Pro Guitar Tuner App Validation  
**Test Level:** User Acceptance Testing (UAT) / Beta Phase  
**Version:** Aligned with ISTQB® Foundation Level Syllabus v4.0.1  
**Author:** Annalie Prinsloo 

---

## 1. Introduction & Test Objectives
The objective of this UAT cycle is to validate the production readiness of the Pro Guitar Tuner (Beta) application from an end-user perspective. Testing focuses on real-time pitch detection accuracy across 12 core 6-string guitar tunings using an external frequency reference. This cycle will verify boundary-value frequency adjustments, notation toggles, UI responsiveness across screen orientations and microphone reliability in varying acoustic environments using 3 designated physical test devices before public deployment.

---

## 2. Test Scope

### 2.1 In-Scope Features
* **6-String physics constraint:** Audio testing restricted exclusively to physically standard 6-string guitars.
* **Pitch detection accuracy verification:** Real-time frequency validation vian the *Online Tone Generator from T.P. Szynalski* across 12 prioritized tunings:
***Standard Tuning:*** E2 (82.41 Hz) | A2 (110.00 Hz) | D3 (146.83 Hz) | G3 (196.00 Hz) | B3 (246.94 Hz) | E4 (329.63 Hz)
***Drop D:*** D2 (73.42 Hz) | A2 (110.00 Hz) | D3 (146.83 Hz) | G3 (196.00 Hz) | B3 (246.94 Hz) | E4 (329.63 Hz)
***Half-step down D#:*** D#2 (77.78 Hz) | G#2 (103.83 Hz) | C#3 (138.59 Hz) | F#3 (185.00 Hz) | A#3 (233.08 Hz) | D#4 (311.13 Hz)
***DADGAD:*** D2 (73.42 Hz) | A2 (110.00 Hz) | D3 (146.83 Hz) | G3 (196.00 Hz) | A3 (220.00 Hz) | D4 (293.66 Hz)
***Open G:*** D2 (73.42 Hz) | G2 (98.00 Hz) | D3 (146.83 Hz) | G3 (196.00 Hz) | B3 (246.94 Hz) | D4 (293.66 Hz)
***Open D:*** D2 (73.42 Hz) | A2 (110.00 Hz) | D3 (146.83 Hz) | F#3 (185.00 Hz) | A3 (220.00 Hz) | D4 (293.66 Hz)
***D Standard Tuning:*** D2 (73.42 Hz) | G2 (98.00 Hz) | C3 (130.81 Hz) | F3 (174.61 Hz) | A3 (220.00 Hz) | D4 (293.66 Hz)
***Drop C:***  C2 (65.41 Hz) | G2 (98.00 Hz) | C3 (130.81 Hz) | F3 (174.61 Hz) | A3 (220.00 Hz) | D4 (293.66 Hz)
***Open E:*** E2 (82.41 Hz) | B2 (123.47 Hz) | E3 (164.81 Hz) | G#3 (207.65 Hz) | B3 (246.94 Hz) | E4 (329.63 Hz)
***All Fourths:*** E2 (82.41 Hz) | A2 (110.00 Hz) | D3 (146.83 Hz) | G3 (196.00 Hz) | C4 (261.63 Hz) | F4 (349.23 Hz)
***Double Drop D:*** D2 (73.42 Hz) | A2 (110.00 Hz) | D3 (146.83 Hz) | G3 (196.00 Hz) | B3 (246.94 Hz) | D4 (293.66 Hz)
***Open G Alt 1 (similar to Renaissance Lute):*** G2 (98.00 Hz) | B2 (123.47 Hz) | D3 (146.83 Hz) | G3 (196.00 Hz) | B3 (246.94 Hz) | D4 (293.66 Hz) / Alternative Note Set: E2 (82.41 Hz) | A2 (110.00 Hz) | D3 (146.83 Hz) | F#3 (185.00 Hz) | B3 (246.94 Hz) | E4 (329.63 Hz)

* **Standard Reference Frequency BVA:** Verifying that standard tuning scales accurately according to changes made to the base reference frequency using Boundary Value Analysis (BVA).

* **UI Component Visual Validation (Samsung S25 Only):** 
- Verifying that different selected tuners output and list the correct targeted notes.
- Checking that the user interface correctly displays individual tuning information text.

* **Notation Toggle Verification (Standard Tuning Only):** 
- Sharp to Flat notation shifting logic.
- Live frequency metrics display in Hz during tuning.
- Real-time cent offset numerical display.
- Highlighted active guitar string UI visual tracking.
- Solfège notation rendering.

* **Screen Orientation Layout Validation (All 3 Phones):** Testing that portrait versus landscape view changes preserve UI layouts under standard tuning conditions.

* **Physical Instrument Sound Environment Testing (Standard Tuning Only):**  Live performance microphone capture verified across four distinct physical guitar types:
- Steel string acoustic guitar
- Classical Guitar
- Electric Guitar (Amp powered off)
- Electric Guitar (Amp powered on, zero sound modifications or effects)


### 2.2 Out-of-Scope Features
* Testing any string profiles or instruments outside of standard 6-string guitars (e.g., 7-string guitars, bass, ukuleles).
* Automated API pitch generation testing scripts (restricted to physical manual execution via Szynalski generator).
* Premium checkout processes, server-side data synchronization, or user profile saving.

---

## 3. Physical Device & Environment Matrix
Testing maps features across specific physical hardware tiers and strict acoustic settings to ensure digital signal processing validation under real-world environments.


| Device Model | Hardware Tier | Target OS | Feature Execution Scope | Acoustic test environments |
| :--- | :--- | :--- | :--- | :--- |
| **Samsung Galaxy S25 FE** | Flagship (Current) | Android 16 | <ul><li>Full scope execution</li><li>Tuner note logic checks</li><li>UI layout text displays</li><li>Orientation testing</li><li>Notation toggles & Hz/Cent UI</li></ul> | <ul><li>Studio environment: Low ambient noise floor</li><li>High noise environment: Loud background chatter/interference</li></ul> |
| **Samsung Galaxy S21 FE** | Flagship (Legacy) | Android 16 | <ul><li>12 Prioritized tuning pitch accuracy</li><li>Reference frequency BVA</li><li>Orientation testing</li></ul> | <ul><li>Studio environment: Low ambient noice floor</li><li>High noice environment: Loud background chatter/interference</li></ul> |
| **Samsung Galaxy A53 5G** | Mid-Range | Android 16 | <ul><li>12 Prioritized tuning pitch accuracy</li><li>Reference frequency BVA</li><li>Orientation testing</li></ul> | <ul><li>Studio environment: Low ambient noice floor</li><li>High noice environment: Loud background chatter/interference</li></ul> |

---

## 4. Mobile Product Risks & Mitigations

### RISK-01: Signal Detection Failures in Loud Environments
* **Risk:** The microphone may fail to isolate standard 6-string instrument frequencies when working inside the high noise environment, preventing the app from calculating Hz values.
* **Mitigation:** Run dedicated parallel benchmarks using an electric guitar with an un-effected amp versus an acoustic guitar in the high noise space to determine pitch capture thresholds.

### RISK-02: Device-Specific Layout Breaks on the S25 Screen Profile
* **Risk:** Dynamic rendering bugs unique to the S25's high-resolution layout framework could freeze note data readouts or clip text displays during sharp/flat notation changes.
* **Mitigation:**  Isolate notation button-toggling loops directly on the S25 interface to verify that active string highlights and cent offsets scale smoothly.

### RISK-03: Aspect Ratio Corruption During Orientation Flipping
* **Risk:** Changing between portrait and landscape views on mid-range or legacy phones might crash the running frequency detection thread or distort string alignment UI assets.
* **Mitigation:** Force rapid orientation changes across all 3 physical phones while the external Szynalski tone generator streams continuous baseline frequencies.

---

## 5. Entry and Exit Criteria

### 5.1 Entry Criteria
1. The target Beta build is successfully installed on all three physical Samsung test units.
2. The manual Szynalski Online Tone Generator testing station is configured and functional.
3. Physical test guitars (Acoustic, Classical, Electric) are prepared and verified available for standard tuning validation.

### 5.2 Exit Criteria
1. Full manual execution of the 12 target tuning matrices is completed across all 3 devices.
2. S25-specific UI tests, notation toggles, and orientation checks have been validated.
3. Standard tuning microphone pickup has been evaluated across all 4 target physical guitar types in both studio and high noise contexts.
4. Zero critical layout or pitch detection functional blocks remain unlogged.

---

## 6. Suspension and Resumption Criteria
* **Suspension:** Testing will halt immediately if the application fails to initialize or freezes upon launching the microphone stream on any of the target physical devices.
* **Resumption:** Testing will resume as soon as a corrected version addressing the audio layer freeze is compiled, verified, and redeployed to the device test matrix.
