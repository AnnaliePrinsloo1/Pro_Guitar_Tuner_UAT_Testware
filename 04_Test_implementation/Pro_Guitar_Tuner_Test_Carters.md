# Exploratory Testing Charters (UAT)

## 1. Purpose and Methodology
These charters provide a structured framework for unscripted, exploratory user testing sessions during the Pro Guitar Tuner App Beta lifecycle. While scripted procedures ensure specific math and layout calculations pass, exploratory charters allow testers to act like real musicians—actively trying to break the system, uncover hidden stability flaws, and evaluate real-world usability constraints. 

Each charter is strictly time-boxed and focused on a specific high-risk user workflow or historical problem area highlighted in user feedback.

---

## 2. Test Charters Inventory

### CHARTER-UI-01: Rapid Rotation & Layout Interruptions
* **Actor / User Persona**: Active Live Performer / Gigging Musician
* **Target Device**: Samsung Galaxy S25 FE, Samsung Galaxy S21 FE, Samsung Galaxy A53 5G
* **Timebox / Duration**: 45 Minutes
* **Mission (What are we exploring?)**: 
  Explore the behavior of the main tuning dashboard when subjected to rapid physical position adjustments and screen orientation shifts during active tuning scenarios. Focus heavily on catching any application crashes, frozen meters, or graphical glitches.
* **Tactics & Core Areas to Interrogate**:
  * Pluck a physical guitar string (or play a continuous loop from the tone generator) and rapidly rotate the phone 180 degrees multiple times.
  * Switch between portrait and landscape modes while actively navigating inside deep configuration sub-menus.
  * Minimize the app during an active tune, open a background application, and quickly maximize the app again to verify state retention and layout consistency.
* **Findings and Observations Summary**: Passed - App recovered with screen rotations and minimize and maximize actions.

---

### CHARTER-UI-02: Rapid Notation and Custom Option Stressing
* **Actor / User Persona**: Music Theorist / Multi-Instrumentalist
* **Target Device**: Samsung Galaxy S25 FE Only
* **Timebox / Duration**: 30 Minutes
* **Mission (What are we exploring?)**: 
  Stress-test the application’s toggle logic by rapidly flipping back and forth between different visual and notation layouts across multiple tuning profiles. This targets the historical user complaint where the app would struggle to apply or save structural defaults.
* **Tactics & Core Areas to Interrogate**:
  * Select an advanced tuning profile (e.g., All Fourths), flip notation from Sharp to Flat, switch to Solfège format, and then change back to Standard tuning in a rapid, continuous sequence.
  * Attempt to find "dead zones" or lag spikes where the UI text labels fail to update or display overlapping text strings.
  * Turn all metric overlays (Hz panel, Cent offset needle, Highlighted strings) on and off rapidly to see if the interface breaks under heavy render requests.
* **Findings and Observations Summary**: Descoped - These features are only available on the prenium tier and cannot be accessed or tested on the free version of the app.

---

### CHARTER-INT-01: Low-Amplitude and Noisy Microphone Boundaries
* **Actor / User Persona**: Guitar Repair Technician working in a busy shop environment
* **Target Device**: Samsung Galaxy S25 FE Only
* **Timebox / Duration**: 60 Minutes
* **Mission (What are we exploring?)**: 
  Investigate the physical limits of the pitch detection algorithm under challenging acoustic conditions using real 6-string guitars. Focus explicitly on low-amplitude sounds and ambient interference blocks.
* **Tactics & Core Areas to Interrogate**:
  * Take the **unamplified solid-body electric guitar** and play extremely soft, gentle fingerstyle plucks near the bottom of the neck to see if the internal mic can pick up the faint string snap.
  * Introduce controlled, realistic distraction noise (such as loud background music or simulated crowded room chatter) and tune the **classical nylon-string guitar** to see if the pitch detection engine isolates the close-range string frequency or jumps around chaotically.
  * Intentionally detune a string extremely far away from its target pitch to evaluate how responsively the needle indicator helps a user bring the pitch back without jumping to an adjacent string row.
* **Findings and Observations Summary**: Passed - Mic picked up faint sting plucs and picked up close ranged string plucs in noisy environments. App helps to recover to retune an untuned string with help of guide window below main tuner display.
