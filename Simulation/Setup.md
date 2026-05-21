---

# Simulation Setup

| Parameter         | Value         |
| ----------------- | ------------- |
| Simulation Type   | Transient     |
| Simulation Time   | 20 µs         |
| Maximum Timestep  | 1 ps          |
| Initial Condition | V(vctrl)=0.9V |

### LTspice Command

```text
.tran 0 20u 0 1p
.ic V(vctrl)=0.9
```

---
