# Test Conditions Definition

## 1. Purpose and Methodology
Test conditions in this document define exactly **what** must be verified during the User Acceptance Testing (UAT) phase for the Pro Guitar Tuner App Beta (Version 6.0.9). These conditions are directly derived from the core functional scope, historical end-user review pain points (user stories), and the technical parameters established in the master Test Plan. 

By analyzing the application specifications alongside user feedback, specific testing focus areas were extracted to target frequency accuracy limits, user interface layout stability under rotation, dynamic notation updates, and physical hardware microphone compatibility across different acoustic environments.

## 2. Test Conditions Inventory


| Condition ID | Source Requirement / Feature | Test Condition (What to Test) | Priority |
| :--- | :--- | :--- | :--- |
| **TC-PT-01** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Standard Tuning" using pure sound waves. | High |
| **TC-PT-02** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Drop D" tuning using pure sound waves. | High |
| **TC-PT-03** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Half-step down D#" tuning using pure sound waves. | High |
| **TC-PT-04** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "DADGAD" tuning using pure sound waves. | Medium |
| **TC-PT-05** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Open G" tuning using pure sound waves. | Medium |
| **TC-PT-06** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Open D" tuning using pure sound waves. | Medium |
| **TC-PT-07** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "D Standard" tuning using pure sound waves. | High |
| **TC-PT-08** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Drop C" tuning using pure sound waves. | High |
| **TC-PT-09** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Open E" tuning using pure sound waves. | Low |
| **TC-PT-10** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "All Fourths" tuning using pure sound waves. | Low |
| **TC-PT-11** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Double Drop D" tuning using pure sound waves. | Low |
| **TC-PT-12** | `UAT-PT-01` (Synthetic Frequency Matrix) | Verify that the application algorithm accurately detects and identifies the 6 specific pitch frequencies for "Open G Alt 1" tuning using pure sound waves. | Low |
| **TC-UI-01** | `UAT-UI-01` (Note Profile Validation) | Verify that the target note naming conventions (e.g., E2, A2, D3, G3, B3 & E4) displayed on-screen exactly match the Standard tuning profile. | High |
| **TC-UI-02** | `UAT-UI-02` (Dashboard Layout) | Verify that text, alignment, and graphic elements on the dashboard remain clean, un-truncated, and readable when selecting the Standard tuning profile. | Medium |
| **TC-UI-03** | `UAT-UI-03` (Orientation Shift) | Verify that the active standard tuning dashboard scales smoothly and preserves text readability when rotated from portrait to landscape view. | High |
| **TC-UI-04** | `UAT-UI-03` (Orientation Shift) | Verify that rotating the device orientation does not cause application lockups, freezes, or calibration resets during active tuning. | High |
| **TC-UI-05** | `UAT-UI-04` (Accidental Notation) | Verify that toggling the flat (♭) format instantly translates sharp notes (e.g., D#2 shifts visually to E♭2) across all relevant tuning configurations. | Medium |
| **TC-UI-06** | `UAT-UI-05` (Dashboard Overlays) | Verify that turning on the numerical metric displays live, fluctuating frequency values in Hertz (Hz) matching the input sound. | High |
| **TC-UI-07** | `UAT-UI-05` (Dashboard Overlays) | Verify that the micro-increment Cent offset gauge displays visual indicators for sharp or flat deviations from the target note. | High |
| **TC-UI-08** | `UAT-UI-05` (Dashboard Overlays) | Verify that the display highlights the correct active graphic guitar string whenever a matching frequency is caught by the microphone. | High |
| **TC-UI-09** | `UAT-UI-05` (Dashboard Overlays) | Verify that the application converts traditional letter note notation into accurate Solfège naming formats (Do, Re, Mi) when the toggle is on. | Low |
| **TC-INT-01**| `UAT-INT-01` (Acoustic Capture) | Verify that a steel-string acoustic 6-string guitar can be picked up and processed cleanly in both a quiet studio and a high-noise environment. | High |
| **TC-INT-02**| `UAT-INT-01` (Acoustic Capture) | Verify that a nylon-string classical 6-string guitar can be picked up and processed cleanly in both a quiet studio and a high-noise environment. | High |
| **TC-INT-03**| `UAT-INT-01` (Acoustic Capture) | Verify that an electric 6-string guitar with the amplifier turned off can be picked up and processed cleanly in both testing environments. | Medium |
| **TC-INT-04**| `UAT-INT-01` (Acoustic Capture) | Verify that an electric 6-string guitar running a raw, unmodified clean tone through an active amplifier can be processed cleanly in both environments. | High |
