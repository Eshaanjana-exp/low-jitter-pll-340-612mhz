The PLL consists of the following major subsystems:

1. Phase Frequency Detector (PFD)
2. Charge Pump
3. Passive Loop Filter
4. Voltage Controlled Oscillator (VCO)
5. Frequency Divider
6. Closed Feedback Loop

---

# Block Diagram

<img width="474" height="158" alt="image" src="https://github.com/user-attachments/assets/e4edef47-726e-4f55-a962-db188a510a2f" />

# Working Principle

The PLL continuously compares the phase and frequency difference between the reference clock (`REF`) and feedback clock (`FB`) using the Phase Frequency Detector (PFD).

Depending on the phase error:

* `UP` pulses increase the control voltage (`VCTRL`)
* `DOWN` pulses decrease the control voltage (`VCTRL`)

The loop filter smooths the charge pump output and generates a stable control voltage for the VCO.

The VCO converts the control voltage into a high-frequency output clock.

The divider scales the VCO output frequency and feeds it back to the PFD for continuous correction.

The PLL reaches lock when:

* `FB` frequency matches `REF`
* phase error becomes minimal
* `VCTRL` stabilizes
* correction pulses become very narrow

---
