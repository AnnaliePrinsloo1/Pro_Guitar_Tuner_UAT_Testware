# Test Execution Log (Chronological Record)

## 1. Daily Execution Summary Tables

### Date: 2026-06-01 (UAT Testing Session 1)
* **Environment Baseline Noise Floor**: Verified at 20 dB via control node (Decibel Meter App v3.0.1 on Samsung S25 FE).
* **Build Under Test**: Pro Guitar Tuner App Beta (Version 6.0.9).


| Timestamp | Procedure / Charter ID | Tester Name | Platform / Env | Status (Pass/Fail/Block) | Linked Defect ID | Actual Results / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 10:10 AM | `PROC-PT-01` | A. Prinsloo | Samsung S25 FE | Fail | **BUG-UAT-01** | Some of the synthetic frequency matrix targets were not detected for standard tuning. |
| 10:40 AM | `PROC-PT-01` | A. Prinsloo | Samsung S21 FE | Fail | **BUG-UAT-01** | Some of the synthetic frequency matrix targets were not detected for standard tuning. |
| 11:10 AM | `PROC-PT-01` | A. Prinsloo | Samsung A53 5G | Fail | **BUG-UAT-01** | Some of the synthetic frequency matrix targets were not detected for standard tuning. |

### Date: 2026-06-02 (UAT Testing Session 2)
* **Build Under Test**: Pro Guitar Tuner App Beta (Version 6.0.9).

| Timestamp | Procedure / Charter ID | Tester Name | Platform / Env | Status (Pass/Fail/Block) | Linked Defect ID | Actual Results / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 11:00 AM | `PROC-UI-01` | A. Prinsloo | Samsung S25 FE | Pass | N/A | The Standard tuning layout notes and labels display with zero truncation. |
| 11:10 AM | `PROC-UI-02` | A. Prinsloo | Samsung S25 FE | Fail | **BUG-UAT-02** | The Standard tuning dashboard visual layout display correctly and with zero truncation on landscape view but truncates menu on portrait view when advert appears. |
| 11:20 PM | `PROC-UI-02` | A. Prinsloo | Samsung S21 FE | Fail | **BUG-UAT-02** | The Standard tuning dashboard visual layout display correctly and with zero truncation on landscape view but truncates menu on portrait view when advert appears. |
| 11:30 PM | `PROC-UI-02` | A. Prinsloo | Samsung A53 5G | Pass | N/A | The Standard tuning dashboard visual layout display correctly and with zero truncation. |

### Date: 2026-06-03 (UAT Testing Session 3)
* **Build Under Test**: Pro Guitar Tuner App Beta (Version 6.0.9).

| Timestamp | Procedure / Charter ID | Tester Name | Platform / Env | Status (Pass/Fail/Block) | Linked Defect ID | Actual Results / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 09:00 PM | `PROC-UI-03` | A. Prinsloo | Samsung S25 FE | Descoped | N/A | Half step down D# tuning setting only available on premium tier. |
| 09:10 PM | `PROC-UI-04` | A. Prinsloo | Samsung S25 FE | Descoped | N/A | Hz readout only available on prenium tier. |
| 09:20 PM | `PROC-UI-04` | A. Prinsloo | Samsung S25 FE | Descoped | N/A | Cent needle only available on prenium tier. |
| 09:30 PM | `PROC-UI-04` | A. Prinsloo | Samsung S25 FE | Pass | N/A | Active string highlights update in real-time. |
| 09:40 PM | `PROC-UI-04` | A. Prinsloo | Samsung S25 FE | Pass | N/A | Solfège Format displays correctly. |
| 09:50 PM | `CHARTER-UI-02` | A. Prinsloo | Samsung S25 FE | Descoped | N/A | The features are only available on the premium tier. |

---

### Date: 2026-06-05 (UAT Testing Session 4)
* **Environment Baseline Noise Floor**: Verified at 20 dB via control node for studio environment and at 80dB for high noise environment (Decibel Meter App v3.0.1 on Samsung S25 FE).
* **Build Under Test**: Pro Guitar Tuner App Beta (Version 6.0.9).


| Timestamp | Procedure / Charter ID | Tester Name | Platform / Env | Status (Pass/Fail/Block) | Linked Defect ID | Actual Results / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 10:00 AM | `PROC-INT-01` | A. Prinsloo | S25 FE / Studio | Pass | N/A | Physical Steel-String Acoustic and Nylon Classical picked up instantly. |
| 10:30 AM | `PROC-INT-01` | A. Prinsloo | S25 FE / Studio | Pass | N/A | Unamplified & amplified electric guitar picked up instantly. |
| 11:30 AM | `PROC-INT-01` | A. Prinsloo | S25 FE / Noise  | Pass | N/A | Software safely isolates steel acoustic & Classical Nylon guitar tones from chatter simulation. |
| 12:00 AM | `PROC-INT-01` | A. Prinsloo | S25 FE / Noise  | Pass | N/A | Software safely isolates unamplified & amplified electric guitar tones from chatter simulation. |
| 12:30 PM | `CHARTER-UI-01` | A. Prinsloo | Samsung S25 FE | Pass | N/A | Backgrounding app and restoring state preserves active tuning selection. |
| 13:00 PM | `CHARTER-UI-03` | A. Prinsloo | Samsung S25 FE | Pass | N/A | Low-Amplitude and Noisy Microphone Boundaries. |
