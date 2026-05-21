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
