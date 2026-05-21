# Implemented PLL Blocks

## 1. Phase Frequency Detector (PFD)

### Purpose

Detects phase and frequency differences between REF and FB clocks.

### Inputs

* REF
* FB

### Outputs

* UP
* DOWN

### Behavioral Model

```text
UP   = if(V(ref)>0.9 & V(fb)<0.9, 1.8, 0)
DOWN = if(V(fb)>0.9 & V(ref)<0.9, 1.8, 0)
```

---

## 2. Charge Pump

### Purpose

Converts UP/DOWN logic pulses into current pulses.

### Operation

* UP pulse → injects current
* DOWN pulse → removes current

### Behavioral Current Sources

```text
I = 0.1u * V(up)/1.8
I = -0.1u * V(down)/1.8
```

---

## 3. Loop Filter

### Purpose

Filters charge pump ripple and generates stable VCTRL.

### Components

| Component | Value  |
| --------- | ------ |
| R1        | 50 kΩ  |
| C1        | 100 nF |
| C2        | 10 nF  |

### Importance

The loop filter significantly reduces ripple and jitter by smoothing the control voltage.

---

## 4. Voltage Controlled Oscillator (VCO)

### Purpose

Generates frequency proportional to VCTRL.

### Frequency Equation

```text
f(VCTRL) = 340 MHz + 151 MHz × VCTRL
```

### Behavioral VCO

```text
V = 0.9 + 0.9*sin(2*pi*(340Meg + 151Meg*V(vctrl))*time)
```

---

## 5. Divider

### Purpose

Scales down the VCO output for feedback comparison.

### Divider Ratio

```text
N = 50
```

### Feedback Frequency

```text
Ffb = Fvco / N
```

---
