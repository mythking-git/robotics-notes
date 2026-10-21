---
title: WM1AD formula sheet
tags: [WM1AD, formula-sheet]
---
## Week 1: circuit fundamentals
| Want | Formula | Guide |
|---|---|---|
| Charge | $Q = It$ | [[Electrical quantities]] |
| Ohm's law | $V = IR$ | [[Electrical quantities]] |
| Resistance of a conductor | $R = \rho L / A$ | [[Electrical quantities]] |
| Power | $P = VI = I^2R = V^2/R$ | [[Electrical quantities]] |
| Energy | $E = Pt$ (J = W s; kWh = kW × h) | [[Electrical quantities]] |
| Efficiency | $\eta = P_{out}/P_{in}$; stages multiply | [[Electrical quantities]] |
| KCL / KVL | $\sum I = 0$ at a node · $\sum V = 0$ round a loop | [[Kirchhoff's laws]] |
| Series / parallel | $R_1 + R_2$ · $R_1R_2/(R_1 + R_2)$ | [[Kirchhoff's laws]] |
| Voltage divider | $V_2 = V R_2/(R_1 + R_2)$ | [[Kirchhoff's laws]] |
| Power balance | $\sum I^2R = \sum VI$ | [[Kirchhoff's laws]] |
| Bridge balance | $R_1/R_2 = R_3/R_4$ | [[Wheatstone bridge and thermistors]] |
| Thermistor | $R = R_0\exp[B(1/T - 1/T_0)]$, T in K | [[Wheatstone bridge and thermistors]] |

## Week 2: matrices, mesh analysis and transients
| Want | Formula | Guide |
|---|---|---|
| 2×2 determinant | $ad - bc$ | [[Matrices and Cramer's rule]] |
| Cramer's rule | $x_k = \Delta_k/\Delta$ | [[Matrices and Cramer's rule]] |
| Mesh matrix | diagonal = total R round mesh; off-diagonal = −shared R | [[Mesh analysis]] |
| Time constant | $\tau = RC$ | [[RC transients]] |
| Charging | $u_C = V(1 - e^{-t/\tau})$, $i = (V/R)e^{-t/\tau}$ | [[RC transients]] |
| Discharging | $u_C = V_0e^{-t/\tau}$ | [[RC transients]] |
| Stored energy | $E = \tfrac12CV^2$ | [[RC transients]] |
| Capacitors | parallel add; series $1/C = 1/C_1 + 1/C_2$ | [[RC transients]] |

## Week 3: power electronics
| Want | Formula | Guide |
|---|---|---|
| Peak from RMS | $V_{pk} = \sqrt2\,V_{RMS}$ | [[AC values]] |
| Average | $V_{avg} = 0.637\,V_{pk} = 0.9\,V_{RMS}$ | [[AC values]] |
| Bridge heat | $P_{D(FB)} = 1.8\,V_F\,I_{D,RMS}$ | [[Bridge rectifiers]] |
| Capacitor peak | $V_{C,max} = V_{pk} - 2V_F$ | [[Bridge rectifiers]] |
| Ripple | $\Delta V = I/(2F_{grid}C)$ | [[Bridge rectifiers]] |
| PWM average | $V_{avg} = DV_{DD}$, $D = t_{on}/T$ | [[PWM]] |
| Conduction loss | $P_{cond} = R_{DS(on)}I_D^2$ | [[MOSFET power loss]] |
| Switching energy | $E_{ON} = \tfrac{V_{DD}I_D}{2}(t_{d(on)} + t_r)$, $E_{OFF} = \tfrac{V_{DD}I_D}{2}(t_{d(off)} + t_f)$ | [[MOSFET power loss]] |
| Switching loss | $P_{SW} = (E_{ON} + E_{OFF})F_{SW}$ | [[MOSFET power loss]] |
| Junction temperature | $T_J = T_{amb} + P(R_{th1} + R_{th2} + R_{th3})$ | [[Thermal design and heatsinks]] |
| Heatsink needed | $R_{th3} = (T_J - T_{amb})/P - (R_{th1} + R_{th2})$ | [[Thermal design and heatsinks]] |
| Safety margin | $100 - (T_J/175) \times 100$, aim ≥ 30% | [[Thermal design and heatsinks]] |
| Buck / boost | $V_{out} = DV_{in}$ · $V_{out} = V_{in}/(1 - D)$ | [[DC-DC converters]] |
| Buck L and C | $L = V_{out}(1 - D)/(F_{SW}\Delta I_L)$ · $C \ge \Delta I_L/(8F_{SW}\Delta V)$ | [[DC-DC converters]] |
| Three-phase drive | $I_{phase} = P_{out}/(\sqrt3V_L\cos\varphi\,\eta)$ · $I_{D,RMS} = I_{phase}/\sqrt2$ · $V_L = V_{DC}/\sqrt2$ | [[Motor drives]] |

## Numbers worth knowing
- UK mains: 230 V RMS, 325 V peak, 50 Hz
- RC: 63% at 1τ, ~100% at 5τ
- Silicon: 175 °C absolute max; design to ≤ 120 °C
- MOSFET below ~700 V; IGBT above ~1000 V
