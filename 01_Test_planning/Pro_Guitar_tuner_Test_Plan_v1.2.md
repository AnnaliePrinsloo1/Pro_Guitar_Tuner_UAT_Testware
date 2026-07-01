# User Acceptance Test Plan: Pro Guitar Tuner App Beta

Identifier: TP-APP-03
Test Level: User Acceptance Testing (UAT)
Current Status: **Completed**
Version: v1.2
Date: 2026-05-29
Author: Annalie Prinsloo

## 1. Document Control
### 1.1 Revision History


| Version | Date | Author | Description of Changes |
| :--- | :--- | :--- | :--- |
| 1.1 | 2026-05-22 | Annalie Prinsloo | Baseline UAT Test Plan |
| 1.2 | 2026-05-29 | Annalie Prinsloo | UAT Test Plan structure updated for Beta Version 6.0.9 based on ISTQB CTFL 4.0 and ISO/IEC/IEEE 29119-3. |


### 1.2 References
* Pro Guitar Tuner App Beta Specifications (Version 6.0.9, Updated Dec 2, 2025)
* ISTQB Foundation Level Syllabus (CTFL 4.0)
* ISO/IEC/IEEE 29119-3 Standard for Software Testing Documentation
* Online Tone Generator (Szynalski) via https://www.szynalski.com/tone-generator/
* Decibel Meter Mobile Application (Version 3.0.1)

---

## 2. Context & Scope
### 2.1 Context of Testing (System Under Test)
The System Under Test (SUT) is the **Pro Guitar Tuner App (Beta Version 6.0.9)** for Android. This User Acceptance Testing (UAT) phase evaluates real-world tuning accuracy, user interface behavior, notation scaling, and physical microphone sensitivity under varying environmental noise floors before public deployment.

### 2.2 Features to be Tested (In-Scope)
* **`UAT-PT-01` (Pitch Accuracy Synthenisation Frequency Matrix)**: Verification of pitch calculations for 12 standardized tunings using synthesized wave frequencies on all 3 target devices.
* **`UAT-UI-01` (Tuning Note Profile Validation)**: Verification that the correct expected notes display cleanly for the Standard tuning profile (Restricted to Samsung Galaxy S25 FE).
* **`UAT-UI-02` (Dashboard Visual Layout Validation)**: Verification of layout design, asset placement, and structural UI integrity the Standard tuning profile (Restricted to Samsung Galaxy S25 FE).
* **`UAT-UI-03` (Screen Orientation Responsive Layout)**: Verification of layout scaling, stability, and text retention when changing between Portrait and Landscape views in Standard Tuning (Executed on all 3 target devices).
* **`UAT-UI-04` (Accidental Notation Toggle Processing)**: Verification that note values dynamically update correctly when toggled between Sharp (#) and Flat (♭) states (Restricted to Samsung Galaxy S25 FE).
* **`UAT-UI-05` (Tuning Metric Overlay Configuration)**: Validation of key UI indicators in Standard Tuning when individual dashboard toggles are adjusted (Restricted to Samsung Galaxy S25 FE):
  * Real-time frequency display in Hertz (Hz).
  * Micro-increment Cent offset gauge.
  * Active/Highlighted graphic guitar string indicator.
  * Solfège notation format display conversion.
* **`UAT-INT-01` (Acoustic Environment Instrument Capture)**: Empirical execution checks utilizing 4 specific physical 6-string guitar configurations across two distinct acoustic environments (Studio vs High Noise) in Standard Tuning only.


### 2.3 Features Not to be Tested (Out-of-Scope)
* **Paid Platform / Paywall Mechanisms**: Testing the \$9.26 premium transaction loop, ad network configurations, ad dismissal close-button hitboxes, or monetization pathways is completely out of scope.
* **Alternative Multi-String Formats**: Any physical testing utilizing instruments with atypical string counts (e.g., 7-string guitars, 4-string basses, mandolins, ukuleles) is strictly excluded.
* **Unlisted Physical Hardware**: Any testing on physical devices or operating system variants outside the 3 specified testing phones.

### 2.4 Assumptions, Constraints, and Dependencies
* **Assumptions**: 
  * The T.P. Szynalski Online Tone Generator provides an accurate, stable reference standard for sinusoidal pitch checking.
* **Constraints**: 
  * Advanced UI and component testing (`UAT-UI-01`, `UAT-UI-02`, `UAT-UI-04`, and `UAT-UI-05`) are physically restricted to the Samsung Galaxy S25 FE hardware profile.
  * Physical instrument testing is limited exclusively to 6-string instrument configurations.
* **Dependencies**: 
  * Maintenance of a strict 10 dB to 30 dB sound environment monitored by the Decibel Meter App (v3.0.1) on the Samsung S25 FE for baseline controls and for the studio environment.
  * Maintenance of 70 dB to 90dB for noisy environments monitored by the Decibel Meter App (v3.0.1) on the Samsung S25 FE.

---

## 3. Test Strategy & Approach
### 3.1 Test Levels and Test Types
* **Test Level**: User Acceptance Testing (UAT) / Beta Phase.
* **Test Types**: 
  * **Functional Testing**: Validating accurate frequency identification, interface rendering correctness, notation state persistence, and screen re-orientation handling.
  * **Environmental Accessibility Testing**: Evaluating microphone detection thresholds across quiet and noisy environments.

### 3.2 Techniques for Test Design
* **Specification-Based Techniques**: Equivalence Partitioning applied to the target frequency spectrum and explicit Use-Case validation of real musician setup paths.

### 3.3 Test Automation Approach
* Completely manual execution. The testing requires human instrumentation of physical guitars and manual verification of laptop tone generator output.

---

## 4. Test Completion & Operational Criteria
### 4.1 Entry Criteria
* Pro Guitar Tuner App Beta (Version 6.0.9) is installed successfully across all 3 test devices.
* Ambient room noise is verified between 10 dB and 30 dB via Decibel Meter App 3.0.1 on the Samsung S25 FE for baseline checks.
* The 4 physical 6-string guitar assets are present, functional, and ready for deployment.

### 4.2 Exit Criteria (Acceptance Criteria)
* **Acoustic Accuracy**: 100% successful detection of target reference frequencies across all 12 tunings on all 3 phones.
* **UI Precision**: Zero display anomalies, misalignments, or incorrect note names visible on the Samsung S25 FE for the Standard tuning profile.
* **Orientation Security**: The application scales cleanly between portrait and landscape modes across all devices without losing calibration or freezing.
* **Dashboard Indicator Integrity**: Perfect visual alignment of Hz readouts, cent adjustments, highlighted strings, and Solfège variations when toggled on the Samsung S25 FE.
* **Microphone Resilience**: Reliable pitch capture across all 4 target physical 6-string guitar styles in both studio and noisy environments for standard tuning.

### 4.3 Suspension and Resumption Criteria
* **Suspension Criteria**: If background sound metrics exceed 30 dB during controlled synth-tone capture, or if an app crash occurs during device orientation changes.
* **Resumption Criteria**: Testing will resume once ambient noise levels settle back to the 10-30 dB range, or when a stable build fix is deployed.

---

## 5. Logistics, Resources & Schedule
### 5.1 Test Environment and Tools Requirements
* **Primary Audio Output**: Laptop workspace executing reference audio via the Szynalski platform.
* **Acoustic Environment Control Node**: Decibel Meter App (Version 3.0.1) active on the Samsung Galaxy S25 FE.
* **Physical Testing Asset Registry**:
  1. Steel-string acoustic guitar (6-string)
  2. Nylon-string classical guitar (6-string)
  3. Electric guitar (Unamplified/Amp off)
  4. Electric guitar connected to amplifier (Output set to an unmodified, raw clean tone)

### 5.2 Roles, Responsibilities, and Staffing
* **UAT Project Lead & Execution Specialist**: Annalie Prinsloo
  * *Responsibilities*: Calibrating the noise floor, running tone checks, handling physical guitars, capturing display anomalies, and logging defects.

### 5.3 Work Breakdown and Estimates


| Task Item | Target Resource | Estimated Effort |
| :--- | :--- | :--- |
| Environment Setup & Noise Floor Verification | Annalie Prinsloo | 0.5 Hours |
| `UAT-PT-01`: Synthetic 12-Tuning Reference Run (3 Devices) | Annalie Prinsloo | 2.0 Hours |
| `UAT-UI-01`, `UAT-UI-02` & `UAT-UI-04`: UI Content & Notation (S25 Only) | Annalie Prinsloo | 3.0 Hours |
| `UAT-UI-03`: Portrait vs Landscape Rotation Stress Suite (3 Devices) | Annalie Prinsloo | 1.0 Hours |
| `UAT-UI-05`: Dashboard Component Toggle Analysis (S25 Only) | Annalie Prinsloo | 1.0 Hour |
| `UAT-INT-01`: Physical 4-Guitar Acoustic Environment Matrix | Annalie Prinsloo | 2.0 Hours |

### 5.4 Milestones and Schedule
* **Milestone 1**: Laboratory Environment Acoustic Calibration Sign-off — Day 1 (08:30)
* **Milestone 2**: Synthetic Freq Sweep (`UAT-PT-01`) Complete — Day 1 (10:10)
* **Milestone 3**: UI, Rotation, and Metric Dashboard Tests (`UAT-UI-01` to `UAT-UI-03`) Complete — Day 2 (11:00)
* **Milestone 4**: UI, Rotation, and Metric Dashboard Tests (`UAT-UI-04` to `UAT-UI-05`) Complete — Day 3 (09:00)
* **Milestone 5**: Empirical Instrument Trials (`UAT-INT-01`) Complete — Day 4 (10:00)
* **Milestone 6**: Final UAT Documentation Complete & Signed Off — Day 5 (16:00)

---

## 6. Communication & Risk Management
### 6.1 Communication Protocols and Status Reporting
* Testing results, layout issues, or frequency tracking failures will be captured in Markdown and delivered to development teams at the close of each testing window.

### 6.2 Product Risks (Quality Risks)


| Risk ID | Risk Description | Impact level | Mitigation Action |
| :--- | :--- | :--- | :--- |
| **PR-01** | The application fails to process real-world physical guitar audio frequencies while passing ideal synthetic tone tests (`UAT-INT-01`). | High | Test early with the unamplified electric guitar to identify baseline physical microphone pickup issues. |
| **PR-02** | The UI layout breaks, truncates text, or crashes when transitioning between landscape and portrait views (`UAT-UI-03`). | Medium | Run rapid back-and-forth rotation tests on all 3 target devices to check for memory leaks or display errors. |
| **PR-03** | High ambient background chatter completely blocks standard tuning verification in the noisy environment test step (`UAT-INT-01`). | Medium | Use a clear, step-by-step scaling approach for the background noise to find the exact point the tuner fails. |

### 6.3 Project Risks (Management Risks)


| Risk ID | Risk Description | Impact level | Mitigation Action |
| :--- | :--- | :--- | :--- |
| **OR-01** | External environment noise leaks into the lab, spiking past the 30 dB cap during synthetic frequency checks. | Medium | Conduct critical synthetic tone matching sessions during low-traffic, off-peak laboratory hours. |

---

## Appendix A: Hardware Execution Scope Matrix

| Device model | Harware Tier | Target OS | Test Suite Execution Scope | Accoustic Environments |
| :--- | :--- | :--- | :--- | :--- |
| Samsung Galaxy S25 FE | Flagship (Current) | Android 16 | <ul><li>`UAT-PT-01`: 12 Tunings Pitch Checks </li><li>`UAT-UI-01`: Tuning Note Accuracy Checks </li><li>`UAT-UI-02`: General UI Display Checks </li><li>`UAT-UI-03`: Screen Orientation Checks </li><li></li><li>`UAT-UI-04`: Sharp/Flat Notation Toggles </li><li>`UAT-UI-05`: Hz/Cent/String/Solfège Toggles </li><li>`UAT-INT-01`: Physical 4-Guitar Testing </li></ul> | Studio Floor (10–30 dB)High Noise Environment |
| Samsung Galaxy S21 FE | Flagship (Legacy) | Android 16 | <ul><li>`UAT-PT-01`: 12 Tunings Pitch Checks </li><li>`UAT-UI-03`: Screen Orientation Checks </li></ul> | Studio Floor (10–30 dB) | 
| Samsung Galaxy A53 5G | Mid-Range | Android 16 | <ul><li>`UAT-PT-01`: 12 Tunings Pitch Checks </li><li>`UAT-UI-03`: Screen Orientation Checks </li></ul> | Studio Floor (10–30 dB) |
