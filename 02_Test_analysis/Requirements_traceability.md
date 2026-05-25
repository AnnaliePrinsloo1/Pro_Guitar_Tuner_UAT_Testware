# Test Analysis: User Stories & Requirements Traceability Matrix (RTM)

**Project Name:** Pro Guitar Tuner App Validation  
**Test Basis:** App Store Feature Specifications & User Experience Benchmarks  
**Methodology Alignment:** ISTQB® Foundation Level v4.0.1 (Section 2.1.2 & 4.1)

---

## 1. User Stories (The Test Basis)
These user stories represent the business requirements and target user expectations for the core features of the Pro Guitar Tuner application.

### US-01: Real-Time Chromatic Pitch Detection
* **As a:** Guitarist tuning my instrument in various environments  
* **I want:** The app to capture my guitar's string vibrations instantly via my device mic and show the exact frequency in Hertz (Hz)  
* **So that:** I can know exactly how far out of tune my instrument is.
* **Acceptance Criteria:**
  * Must display frequency numbers instantly with low acoustic latency.
  * Must filter out minor room hums or static sounds.

### US-02: Visual Tuning Guidance (The Interface)
* **As a:** Musician tuning quickly on stage or during practice  
* **I want:** A highly visible central dial needle that turns green when flat or sharp notes reach 0 cents variance  
* **So that:** I can tune my guitar visually without needing to read small text numbers.
* **Acceptance Criteria:**
  * Needle moves smoothly across the dial without stuttering.
  * Screen colors switch dynamically: **Red** for Flat/Sharp, **Solid Green** when perfectly in-tune.

### US-03: Alternate Tuning Selection
* **As a:** Creative guitar player using varied musical styles  
* **I want:** To change the target tuning profile from Standard (E-A-D-G-B-E) to alternate layouts like Drop D or Half-Step Down  
* **So that:** I do not have to calculate alternative note frequencies manually.
* **Acceptance Criteria:**
  * Changing profiles alters the target note reference notes instantly on the dashboard.

### US-04: System Interruption Resilience
* **As a:** Mobile user operating on an active personal smartphone  
* **I want:** The app to handle background app switching or phone call interruptions gracefully  
* **So that:** The microphone lock does not crash the app or freeze my operating system.
* **Acceptance Criteria:**
  * App must release the microphone stream immediately when minimized.
  * App must reconnect to the microphone stream cleanly upon user return.

---

## 2. Requirements Traceability Matrix (RTM)
This matrix ensures that every technical requirement derived from our user stories and overarching test plan is fully covered by specific, testable conditions across our physical device matrix.


| Req ID | User Story ID | Requirement Category | Requirement description | Linked Test Case (ID) | Status / Coverage |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **REQ_TUN_01** | US-01, US-03 | Pitch Detection | Validate real-time frequency capture for 12 prioritized 6-string guitar tunings using an external frequency reference. | TC_TUN_001, TC_TUN_002 | Covered |
| **REQ_TUN_02** | US-01 | Pitch Detection | Execute standard reference frequency scaling verification using Boundary Value Analysis (BVA). | TC_TUN_003 | Covered |
| **REQ_TUN_03** | US-01 | Pitch Detection | Filter out minor room hums, ambient static, and environmental noise floor interference. | TC_MIC_002, TC_NEG_001 | Covered |
| **REQ_UI_01** | US-02, US-03 | User Interface | Verify correct target note readouts and information text displays for selected tunings on the Samsung S25 profile. | TC_UI_001 | Covered |
| **REQ_UI_02** | US-02 | User Interface | Validate Sharp to Flat notation shifting logic on standard tuning. | TC_UI_002 | Covered |
| **REQ_UI_03** | US-01, US-02 | User Interface | Verify live frequency metric display in Hz during instrument tuning. | TC_UI_003 | Covered |
| **REQ_UI_04** | US-02 | User Interface | Verify real-time numerical cent offset display within the UI. | TC_UI_004 | Covered |
| **REQ_UI_05** | US-02 | User Interface | Track highlighted active guitar string components visually on the screen. | TC_UI_005 | Covered |
| **REQ_UI_06** | US-02 | User Interface | Validate Solfège notation rendering under standard tuning conditions. | TC_UI_006 | Covered |
| **REQ_UI_07** | US-02 | User Interface | Render a central tuning dial needle that moves smoothly without stuttering or frame drops. | TC_UI_007 | Covered |
| **REQ_UI_08** | US-02 | User Interface | Switch UI colors dynamically: Red for out-of-tune (Flat/Sharp) and Solid Green at 0 cents variance. | TC_UI_008 | Covered |
| **REQ_PROF_01** | US-03 | Tuning Profiles | Alter target dashboard reference notes instantly when switching tuning profiles (e.g., Standard to Drop D). | TC_PROF_001 | Covered |
| **REQ_LAY_01** | N/A (UAT Plan) | Layout Integrity | Validate layout preservation during portrait and landscape view changes across all 3 test devices. | TC_LAY_001 | Covered |
| **REQ_MIC_01** | US-01 | Hardware Interface | Capture live physical instrument performance via microphone across 4 distinct guitar types in standard tuning. | TC_MIC_001 | Covered |
| **REQ_SYS_01** | US-04 | System Integration | Release the device microphone hardware stream immediately when the application is minimized. | TC_SYS_001 | Covered |
| **REQ_SYS_02** | US-04 | System Integration | Reconnect and initialize the microphone stream cleanly upon returning from a background interruption. | TC_SYS_002 | Covered |

# 3. Verification metrics summary
- **Total requirements defined:** 16
- **Requirements derived from User Stories (US-01 to US-04):** 15
- **Requirements derived from Test Plan (Layout/UAT Scope):** 1
- **Total requirements covered:** 16
- **Test coverage percentage:** 100%
- **Unmapped requirements:** 0

# 4.  Physical Instrument Traceability Map
This map directly links your four specific physical guitar test assets to the software requirements they validate during the live acoustic environment testing phase.

[ Physical Guitar Asset ] ────────────────────────► [ Validated Requirement ID ]
├── 1. Steel String Acoustic Guitar ───────────────► REQ_MIC_01 (Live standard tuning capture)
│                                                   └── REQ_TUN_03 (Low volume pickup / ambient filtering)
│
├── 2. Classical Guitar (Nylon Strings) ───────────► REQ_MIC_01 (Live standard tuning capture)
│                                                   └── REQ_TUN_03 (Fading acoustic resonance capture)
│
├── 3. Electric Guitar (Amp Powered Off) ──────────► REQ_MIC_01 (Live standard tuning capture)
│                                                   └── REQ_TUN_03 (Extreme low signal level boundary)
│
└── 4. Electric Guitar (Amp On, Clean Signal) ────► REQ_MIC_01 (Live standard tuning capture)
                                                    └── REQ_TUN_03 (Signal isolation against background amp hum)

# 5.  Environmental Mapping Matrix
| Physical Guitar Type | Primary Acoustic Context | Target Requirement Mapping | Testing Purpose / Focus |
| :--- | :--- | :--- | :--- |
| **Steel String Acoustic** | Studio & High Noise | REQ_MIC_01, REQ_TUN_03 | High projection baseline signal testing. |
| **Classical Guitar** | Studio & High Noise | REQ_MIC_01, REQ_TUN_03 | Soft attack and rapid decay resonance tracking. |
| **Electric Guitar (Amp Off)** | Studio Floor | REQ_MIC_01, REQ_TUN_03 | Absolute minimum signal input threshold checking. |
| **Electric Guitar (Amp On)** | Studio & High Noise | REQ_MIC_01, REQ_TUN_03 | Frequency isolation from clean speaker outputs. |


## 6. Hardware-Specific Coverage Mapping
To address our **Test Plan risks**, these test conditions are mapped to specific physical devices during execution:
* **REQ_UI_07 / TC_UI_007 (Needle Smoothness):** Strictly analyzed on the mid-range **Samsung Galaxy A53** to detect GPU rendering performance frames drops under dynamic UI conditions.
* **REQ_TUN_03 / TC_MIC_002 & TC_NEG_001 (Low Volume Pick-up):** Extensively validated on the legacy **Samsung Galaxy S21 FE** to check older microphone hardware sensitivity and ambient static filtering thresholds.
* **REQ_SYS_01 & REQ_SYS_02 / TC_SYS_001 & TC_SYS_002 (Interrupt Handling):** Validated on the **Samsung Galaxy S25 FE** running Android 16 to ensure absolute compatibility with modern OS privacy policies and seamless microphone hardware stream release/reinitialization.
