---
title: Week 3 formula sheet
tags: [WM1AD, week-3, formula-sheet]
---
| Want | Formula | Guide |
|---|---|---|
| Peak from RMS | $V_{pk} = \sqrt2\,V_{RMS}$ | [[AC values]] |
| Average | $V_{avg} = 0.637\,V_{pk} = 0.9\,V_{RMS}$ | [[AC values]] |
| Bridge heat | $P_{D(FB)} = 1.8\,V_F\,I_{D,RMS}$ | [[Bridge rectifiers]] |
| Capacitor peak | $V_{C,max} = V_{pk} - 2V_F$ | [[Bridge rectifiers]] |
| Ripple | $\Delta V = I / (2F_{grid}C)$ | [[Bridge rectifiers]] |
| PWM average | $V_{avg} = D\,V_{DD}$, $D = t_{on}/T$, $T = 1/F$ | [[PWM]] |
| Conduction loss | $P_{cond} = R_{DS(on)}I_D^2$ | [[MOSFET power loss]] |
| Switching energy | $E_{ON} = \tfrac{V_{DD}I_D}{2}(t_{d(on)} + t_r)$, $E_{OFF} = \tfrac{V_{DD}I_D}{2}(t_{d(off)} + t_f)$ | [[MOSFET power loss]] |
| Switching loss | $P_{SW} = (E_{ON} + E_{OFF})F_{SW}$ | [[MOSFET power loss]] |
| Total MOSFET loss | $P_{MOSFET} = P_{cond} + P_{SW}$ | [[MOSFET power loss]] |
| Junction temperature | $T_J = T_{amb} + P(R_{th1} + R_{th2} + R_{th3})$ | [[Thermal design and heatsinks]] |
| No heatsink | $T_J = T_{amb} + P\,R_{thJA}$ | [[Thermal design and heatsinks]] |
| Heatsink needed | $R_{th3} = (T_J - T_{amb})/P - (R_{th1} + R_{th2})$ | [[Thermal design and heatsinks]] |
| Safety margin | $100 - (T_J/175) \times 100$, aim for ≥ 30% | [[Thermal design and heatsinks]] |
| Buck | $V_{out} = D\,V_{in}$ | [[DC-DC converters]] |
| Boost | $V_{out} = V_{in}/(1-D)$ | [[DC-DC converters]] |
| Buck inductor | $L = V_{out}(1-D)/(F_{SW}\Delta I_L)$ | [[DC-DC converters]] |
| Buck capacitor | $C \ge \Delta I_L/(8F_{SW}\Delta V)$ | [[DC-DC converters]] |
| Three-phase drive | $I_{phase} = P_{out}/(\sqrt3\,V_L\cos\varphi\,\eta)$, $I_{D,RMS} = I_{phase}/\sqrt2$, $V_L = V_{DC}/\sqrt2$ | [[Motor drives]] |

## Limits worth memorising
- UK mains: 230 V RMS, 325 V peak, 50 Hz
- Silicon: 175 °C absolute max, design to ≤ 120 °C, margin ≥ 30%
- MOSFET below ~700 V, IGBT above ~1000 V
