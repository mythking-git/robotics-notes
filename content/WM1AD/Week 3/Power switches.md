---
title: Power switches
tags: [WM1AD, week-3]
---
## The idea
To control a motor you need a switch that turns power on and off, often thousands of times a second. A **relay** does it mechanically. **Transistors** do it electronically: a small control signal on one leg lets a large current flow through the other two. The key difference between transistor types is **what the control signal is**, a current or a voltage.

## The transistors
**BJT (bipolar junction transistor): current-controlled.** Legs: **base (B), collector (C), emitter (E)**. A small base current $I_B$ lets a large collector current flow, roughly $I_C = \beta I_B$. The drawback is that the base needs current *all the time* it's on, which wastes power. NPN and PNP types are biased opposite ways round.

**MOSFET: voltage-controlled.** Legs: **gate (G), drain (D), source (S)**. The gate is insulated from the channel by a thin layer of silicon dioxide, so almost **no gate current** flows. Raise the gate–source voltage $V_{GS}$ above the threshold $V_{GS(th)}$ and current flows drain → source. Fully on, it behaves like a small resistor, $R_{DS(on)}$.

**IGBT (insulated gate bipolar transistor): a hybrid.** It has a MOSFET's insulated, voltage-driven gate and a BJT's high-power output stage. Same structure as a MOSFET plus an extra P layer.

## Comparison
| Switch | Controlled by | Strengths | Weaknesses | Typical use |
|---|---|---|---|---|
| Relay | Coil current moves a contact | Cheap, takes surges, true isolation, cool, several poles | Slow, wears out, sparks, vibration-sensitive | Occasional mains switching |
| SSR (solid-state relay) | Small input signal | Long life, fast, silent, no arcing, tiny control power | Gets hot, costs more, leaks a little current, surge-sensitive | Frequent switching, heaters |
| BJT | Base **current** | Simple, cheap | Needs continuous drive current, slower | Small signals |
| **MOSFET** | Gate **voltage** | Very fast, easy to drive | $R_{DS(on)}$ rises in high-voltage parts | **Robots and motor drives, below ~700 V** |
| IGBT | Gate **voltage** | High voltage and current | Slower switching | **Above ~1000 V**: trains, grid, large inverters |

> [!tip] Rule of thumb
> MOSFET below about 700 V, IGBT above about 1000 V. In between, pick whichever best fits the size, efficiency and cost.

## Reading a MOSFET datasheet
| Value | Section | What it tells you | IRFP140 | IRFP250 |
|---|---|---|---|---|
| $V_{DSS}$ | Absolute max | Most voltage it can block when off | 100 V | 200 V |
| $I_D$ | Absolute max | Most continuous current (falls when hot) | 31 A | 30 A |
| $R_{DS(on)}$ | Static | Resistance when fully on, for [[MOSFET power loss\|conduction loss]] | 0.077 Ω | 0.075 Ω |
| $t_{d(on)}, t_r$ | Dynamic | Turn-on delay and rise time | 11, 44 ns | 14, 43 ns |
| $t_{d(off)}, t_f$ | Dynamic | Turn-off delay and fall time | 53, 43 ns | 41, 33 ns |
| $R_{thJC}, R_{thCS}, R_{thJA}$ | Thermal | For [[Thermal design and heatsinks\|heatsink sizing]] | 0.83, 0.24, 40 °C/W | 0.7, 0.24, 40 °C/W |

## Check yourself
> [!question]- 1. Why does a MOSFET need almost no drive power once it's on?
> Its gate is insulated, so it only needs a voltage, with no continuous current. A BJT's base needs current the whole time.

> [!question]- 2. You need to switch 48 V at 20 A, 20 000 times a second. Relay, BJT, MOSFET or IGBT?
> A MOSFET: low voltage, fast switching. A relay is far too slow, and an IGBT is aimed at much higher voltages.
