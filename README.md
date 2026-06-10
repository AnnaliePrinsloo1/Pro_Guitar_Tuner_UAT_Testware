# Pro_Guitar_Tuner_UAT_Testware
An end-to-end UAT testware showcase for the Pro Guitar Tuner app, structured strictly according to the ISTQB Foundation Level Syllabus v4.0.1 test process.

# Pro Guitar Tuner (Beta) - End-to-End User Acceptance Test (UAT) Run

[![ISTQB Certified Tester](https://shields.io+)](https://scr.istqb.org/?name=Annalie+Prinsloo&number=ZA010123GK0981040&orderBy=relevancy)


This repository hosts the complete testware suite and execution logs for the production-readiness validation of the **Pro Guitar Tuner App (Beta version)**. 

The primary objective of this project was to manually verify the app's real-time pitch detection accuracy across 12 core 6-string tunings using an external frequency reference, while verifying boundary-value frequency adjustments, notation toggles, UI responsiveness across screen orientations and microphone reliability in varying acoustic environments using three test devices. The testing process utilizes a rigorous framework aligned with international **ISTQB Foundation Level (v4.0.1)** documentation and execution standards.

Note: Pitch detection was only performed for Standard Tuning and the other requirements descoped due to the fact that it was only available on the prenium tier.

---

## Physical device test matrix
Testing was conducted strictly on physical Android devices to expose hardware-specific defects that emulators cannot replicate, such as microphone sensitivity variations, hardware audio routing latencies, and device-specific memory management profiles.

*   **Device 1 (Primary Flagship Tier):** Samsung Galaxy S25 FE | Model: `SM-S731B/DS` | Android 16
*   **Device 2 (Legacy Flagship Tier):** Samsung Galaxy S21 FE | Model: `SM-G990E/DS` | Android 16
*   **Device 3 (Mid-Range Tier):** Samsung Galaxy A53 5G | Model: `SM-A536E/DS` | Android 16

*Acoustic testing profiles covered both isolated quiet studio environments and high-ambient-noise environments using built-in microphone arrays .*
---

## Test process documentation structure
The testing artifact lifecycle was divided into chronological phases to guarantee full accountability and execution traceability:

```text
├── README.md                          
├── 01_Test_planning/
│   └── Pro_Guitar_tuner_Test_Plan_v1.2.md             
├── 02_Test_analysis/
│   └── Pro_Guitar_Tuner_RTM.md
│   └── Pro_Guitar_Tuner_Test_Conditions.md  
├── 03_Test_design/
│   └── Pro_Guitar_Tuner_Test_Cases_Suite.md            
├── 04_Test_implementation/
│   └── Pro_Guitar_Tuner_Data_Setup.md
│   └── Pro_Guitar_Tuner_Test_Carters.md
│   └── Pro_Guitar_Tuner_Test_Procedures.md             
├── 05_Test_execution/
│   ├── Pro_Guitar_Tuner_Execution_Log.md
│   ├── Pro_Guitar_Tuner_Defect_Report_BUG-UAT-01.md
│   ├── Pro_Guitar_Tuner_Defect_Report_BUG-UAT-02.md
│   ├── S21_GUI_Truncation.jpg
│   ├── S25_GUI_Truncation.jpg       
└── 06_Test_completion/
    └── Pro_Guitar_Tuner_Test_Report_TSR-UAT-01.md          
```

---

## Validation methodologies & Test quality metrics

*   **Reference pitch & Boundary Analysis:** Validated real-time pitch detection accuracy for standard tuning for 6-string guitar tunings using an external tone generator for **Equivalence Partitioning (EP)** and applied **Boundary Value Analysis (BVA)** to verify custom changes made to the standard reference frequency.
*   **UI & Configuration Resilience:** Verified interface responsiveness, notation changes (sharp/flat toggles (descoped) and Solfège), and visual indicators (Hz frequency (descoped), cent offset (descoped), highlighted strings) across 3 test devices, including orientation stability (portrait vs. landscape) under standard tuning.
*  **Acoustic environment & hardware adaptability:** Evaluated microphone stream pickup across multiple physical guitar types (steel string acoustic, classical, electric with app off, and electric with clean amp on) by testing performance in a controlled studio environment versus a high-noise environment.
*  **Multi-device coverage** Maintained targeted test execution across 3 designated mobile devices, isolating deep UI component checks to specific hardware (e.g. Samsung S25) while scaling layout and environment tests across the entire device pool.
*   **Full Traceability:** Maintained a 100% trace link from Google Play Beta storefront requirements down to individual device defect logs via a comprehensive Requirements Traceability Matrix (RTM).

---

## Active test cycle insights

*   **Total Test Scenarios Executed:** 14
*   **Critical Defects Uncovered:** 2
*   **Deployment Release Status:** Pending Release

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
