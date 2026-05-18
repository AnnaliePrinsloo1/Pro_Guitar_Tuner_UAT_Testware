# Pro_Guitar_Tuner_UAT_Testware
An end-to-end UAT testware showcase for the Pro Guitar Tuner app, structured strictly according to the ISTQB Foundation Level Syllabus v4.0.1 test process.

# Pro Guitar Tuner (Beta) - End-to-End User Acceptance Test (UAT) Run

[![ISTQB Certified](https://shields.io)](https://istqb.org)

This repository hosts the complete testware suite and execution logs for the production-readiness validation of the **Pro Guitar Tuner App (Beta version)**. 

The primary objective of this project is to manually verify the app's real-time pitch detection accuracy across 12 core 6-string tunings using an external frequency reference, while verifying boundary-value frequency adjustments, notation toggles, UI responsiveness across screen orientations and microphone reliability in varying acoustic environments using three test devices.The testing process utilizes a rigorous framework aligned with international **ISTQB Foundation Level (v4.0.1)** documentation and execution standards.

---

## Physical device test matrix
Testing is conducted strictly on physical Android devices to expose hardware-specific defects that emulators cannot replicate, such as microphone sensitivity variations, hardware audio routing latencies, and device-specific memory management profiles.

*   **Device 1 (Primary Flagship Tier):** Samsung Galaxy S25 FE | Model: `SM-S731B/DS` | Android 16
*   **Device 2 (Legacy Flagship Tier):** Samsung Galaxy S21 FE | Model: `SM-G990E/DS` | Android 16
*   **Device 3 (Mid-Range Tier):** Samsung Galaxy A53 5G | Model: `SM-A536E/DS` | Android 16

*Acoustic testing profiles cover both isolated quiet studio environments and high-ambient-noise environments using built-in microphone arrays .*
---

## Test process documentation structure
The testing artifact lifecycle is divided into chronological phases to guarantee full accountability and execution traceability:

```text
├── README.md                          # Test matrix, scope, and execution summary
├── 01_test_planning/
│   └── uat_test_plan.md               # Quality goals, device risks, entry/exit criteria
├── 02_test_analysis/
│   └── requirements_traceability.md   # RTM mapping app storefront features to test targets
├── 03_test_design/
│   └── test_cases_suite.md            # Target test cases designed via EP and BVA techniques
├── 04_test_implementation/
│   └── test_procedures.md             # Execution order setups and user testing workflows
├── 05_test_execution/
│   ├── execution_log.md               # Historical pass/fail run records per device model
│   └── defect_reports/                # Verified bug reports with embedded ADB Logcat outputs
└── 06_test_completion/
    └── completion_report.md           # Defect density, test metrics, and release advice
```

---

## Validation methodologies & Test quality metrics

*   **Reference pitch & Boundary Analysis:** Validated real-time pitch detection accuracy across 12 distinct 6-string guitar tunings using an external tone generator for **Equivalence Partitioning (EP)** and applied **Boundary Value Analysis (BVA)** to verify custom changes made to the standard reference frequency.
*   **UI & Configuration Resilience:** Verified interface responsiveness, notation changes (sharp/flat toggles and Solfège), and visual indicators (Hz frequency, cent offset, highlighted strings) across 3 test devices, including orientation stability (portrait vs. landscape) under standard tuning.
*  **Acoustic environment & hardware adaptability:** Evaluated microphone stream pickup across multiple physical guitar types (steel string acoustic, classical, electric with app off, and electric with clean amp on) by testing performance in a controlled studio environment versus a high-noise environment.
*  **Multi-device coverage** Maintained targeted test execution across 3 designated mobile devices, isolating deep UI component checks to specific hardware (e.g. Samsung S25) while scaling layout and environment tests across the entire device pool.
*   **Full Traceability:** Maintained a 100% trace link from Google Play Beta storefront requirements down to individual device defect logs via a comprehensive Requirements Traceability Matrix (RTM).

---

## Active test cycle insights

*   **Total Test Scenarios Executed:** 
*   **Hardware Coverage:** 
*   **Critical Defects Uncovered:** 
*   **Deployment Release Status:** 

---

## About the QA professional
I am an **ISTQB® Certified Freelance Software Tester** specializing in end-to-end **User Acceptance Testing (UAT)** and digital quality assurance. I partner with businesses to validate and optimize high-impact digital products before market launch, ensuring seamless user experiences and functional reliability across multiple platforms.

### Core Areas of Expertise:
*   **Mobile Application Testing:** Native Android app validation, physical device matrix testing, hardware-software interaction testing, and interruption handling.
*   **E-Commerce Platforms:** End-to-end checkout flow validation, payment gateway integration testing, shopping cart state persistence, and localized user journey verification.
*   **Web Application QA:** Cross-browser compatibility validation, responsive web design (RWD) testing, and functional regression testing.

### Let's Connect:
*   **LinkedIn:** [Annalie Prinsloo](https://www.linkedin.com/in/annalieprinsloo001/)
*   **Professional Email:** <annalieprinsloo1@gmail.com>
*   **ISTQB Verification ID:** [ZA010123GK0981040](https://scr.istqb.org/?name=Annalie+Prinsloo&number=ZA010123GK0981040&orderBy=relevancy&orderDirection=&dateStart=&dateEnd=&expiryStart=&expiryEnd=&certificationBody=&examProvider=&certificationLevel=&country=)
*   **Availability:** Open to contract, freelance QA opportunities.
